---
title: Migração de caixa de correio entre locatários
description: Como mover caixas de correio entre os locatários do Microsoft 365 ou do Office 365.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: a2065ac324acd0a4d5980bceb97f9f6b8ad73058
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002240"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migração de caixa de correio de locatário cruzado (versão prévia)

Anteriormente, quando um locatário do Exchange Online precisava mover caixas de correio para outro locatário no mesmo serviço do Exchange Online, ele teria que externamente-las completamente para o local e, em seguida, integrá-las a um novo locatário. Com o novo recurso de migração de caixa de correio de vários locatários, os administradores de locatários nos locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências de infra-estrutura mínimas em seus sistemas locais. Isso remove a necessidade de externamente e caixas de correio integradas.

Normalmente, durante mesclagens ou divestitures, você precisa da capacidade de mover os usuários e o conteúdo para um novo locatário. Quando o administrador de locatário de destino executa a movimentação, ela é chamada de movimentação de recepção, semelhante às migrações de integração local para a nuvem.

As movimentações de caixa de correio do Exchange entre locatários são totalmente autoatendidas por administradores de locatários, usando interfaces conhecidas que podem ser inseridas em scripts nos fluxos de trabalho maiores necessários para fazer a transição de usuários para sua nova organização. Os administradores podem usar o `New-MigrationBatch` cmdlet, disponível por meio da função de gerenciamento mover caixas de correio, para executar movimentações entre locatários. O processo de movimentação inclui verificações de autorização de locatário durante a sincronização e a finalização da caixa de correio. 
 
Os usuários que estão migrando devem estar presentes no sistema de locatário do Exchange Online como MailUsers, marcados com atributos específicos para habilitar movimentações entre locatários. O sistema falhará em movimentações para usuários que não estejam configurados corretamente no locatário de destino. 

Quando as movimentações são concluídas, a caixa de correio do sistema de origem é convertida em MailUser e o targetAddress (mostrado como ExternalEmailAddress no Exchange) é marcado com o endereço de roteamento para o locatário de destino. Esse processo deixa o MailUser herdado no locatário de origem e permite um período de coexistência e roteamento de email. Quando o processo de negócios permitir, o locatário de origem poderá remover o MailUser de origem ou convertê-lo em um contato de email. 

Há suporte para as migrações de caixa de correio do Exchange entre locatários em locatários apenas híbridos ou em nuvem, ou qualquer combinação dos dois.

Este artigo descreve o processo de movimentações de caixa de correio de locatários cruzados e fornece orientação sobre como preparar locatários de origem e de destino para a movimentação de conteúdo. 

## <a name="preparing-source-and-target-tenants"></a>Preparar locatários de origem e de destino

O recurso de migração de caixa de correio do Exchange de locatário cruzado requer autorização e escopo para migrações entre os locatários. Usando as soluções de armazenamento de aplicativo empresarial e de repositório de chaves do Azure, os administradores de locatários agora são habilitados para gerenciar a autorização e o escopo de migrações de caixa de correio do Exchange Online de um locatário para outro. As movimentações de caixa de correio de vários locatários dão suporte a um modelo de convite e consentimento para estabelecer um aplicativo do Azure Active Directory (Azure AD) usado para autenticação entre um par de locatários. Também são necessários componentes adicionais, como um relacionamento de organização e um ponto de extremidade de migração.

Esta seção não inclui as etapas específicas necessárias para preparar os objetos de usuário do MailUser no diretório de destino, nem inclui o comando de exemplo para enviar um lote de migração. Consulte [preparar objetos de usuário de destino para migração](#prepare-target-user-objects-for-migration) para essas informações.

## <a name="prerequisites"></a>Pré-requisitos

O recurso de movimentação de caixa de correio de vários locatários requer o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) para estabelecer um aplicativo do Azure específico de par de locatários para armazenar e acessar com segurança o certificado/segredo usado para autenticar e autorizar a migração de caixa de correio de um locatário para outro, removendo quaisquer requisitos para compartilhar certificados/segredos entre os locatários. 

Antes de começar, verifique se você tem as permissões necessárias para executar os scripts de implantação a fim de configurar o Azure Key Vault, mover o aplicativo de caixa de correio, o ponto de extremidade de migração do EXO e o relacionamento de organização do EXO. Normalmente, o administrador global tem permissão para executar todas as etapas de configuração.

Além disso, os grupos de segurança habilitados para email no locatário de origem são necessários antes de executar a instalação. Esses grupos são usados para escopo a lista de caixas de correio que podem ser movidas de um locatário de origem (ou às vezes chamado de recurso) para o locatário de destino. Isso permite que o administrador do locatário de origem restrinja ou escopo o conjunto específico de caixas de correio que precisam ser movidas, impedindo que usuários indesejados sejam migrados. Não há suporte para grupos aninhados.

Você também precisará se comunicar com sua empresa parceira confiável (com a qual você vai mover as caixas de correio) para obter sua ID de locatário do Microsoft 365. Esta ID de locatário é usada no campo relação de organização `DomainName` .

Para obter a ID do locatário de uma assinatura, entre no centro de administração do Microsoft 365 e vá para [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Clique no ícone Copiar da propriedade ID do locatário para copiá-lo para a área de transferência.

Veja como funciona o processo.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparação do locatário para migração de caixa de correio.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a>Preparar locatários

Em um nível alto, as seguintes ações de configuração ocorrerão durante a execução dos scripts de instalação.

Prepare o locatário de destino:

1. Se um grupo de recursos do Azure existente não for fornecido, será criado um novo (SCRIPT).
2. Se um cofre de chaves existente não for fornecido, será criado um novo (SCRIPT).
3. Uma nova política de acesso é criada para o aplicativo de migração de caixa de correio (SCRIPT) do Office 365 do Exchange Online.
4. Um novo certificado é criado (ou existente, se especificado) para manter o segredo para o aplicativo de migração (SCRIPT).
5. Um novo aplicativo do Azure AD é criado (SCRIPT).
6. O certificado/segredo é carregado no aplicativo de migração (SCRIPT).
7. As permissões de migração de caixa de correio são atribuídas ao aplicativo (SCRIPT).
8. O script de implantação pausa até que o administrador de destino seja enviado a seu próprio aplicativo (SCRIPT).
9. O administrador do locatário de destino é enviado às permissões concedidas ao aplicativo (MANUAL).
10. Um relacionamento de organização é criado para o locatário de destino (SCRIPT).
11. Um ponto de extremidade de migração é criado para extrair caixas de correio para o locatário (SCRIPT) de destino.

Prepare o locatário de origem:

1. O administrador do locatário de origem aceita o consentimento para o convite do aplicativo de migração de caixa de correio do locatário de destino (MANUAL).
2. O administrador do locatário de origem cria um grupo de segurança habilitado para email em seus locatários para conter a lista de caixas de correio que podem ser movidas pelo aplicativo de migração (MANUAL).
3. Um relacionamento de organização é criado para o locatário de destino especificar o aplicativo de migração de caixa de correio deve ser usado para verificação de OAuth para aceitar a solicitação de movimentação (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Instruções passo a passo para o administrador de locatários de destino

1. Baixe o script de SetupCrossTenantRelationshipForTargetTenant.ps1 para a configuração de locatário de destino do [repositório do GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Salve o script (SetupCrossTenantRelationshipForTargetTenant.ps1) no computador no qual você executará o script.
3. Crie uma conexão do PowerShell remoto para o locatário de destino do Exchange Online. Novamente, verifique se você tem as permissões necessárias para executar os scripts de implantação a fim de configurar o armazenamento do Azure Key Vault e o certificado, mover o aplicativo de caixa de correio, o ponto de extremidade de migração do EXO e o relacionamento de organização do EXO.
4. Altere o diretório de pasta de arquivo para o local do script ou verifique se o script está atualmente salvo no local em sua sessão remota do PowerShell.
5. Execute o script com os seguintes parâmetros e valores.

    | Parâmetro | Valor | Obrigatório ou opcional
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | Domínio do locatário de origem, como a Fabrikam \. onmicrosoft.com. | Obrigatório |
    | -ResourceTenantAdminEmail                   | Endereço de email do administrador do locatário de origem. Este é o administrador do locatário de origem que será consentido no uso do aplicativo de migração de caixa de correio enviado do administrador de destino. Esse é o administrador que receberá o convite de email para o aplicativo. | Obrigatório |
    | -TargetTenantDomain                         | Domínio de locatário de destino, como contoso \. onmicrosoft.com. | Obrigatório |
    | -ResourceTenantId                           | ID da organização do locatário de origem (GUID). | Obrigatório |
    | -SubscriptionId                             | A assinatura do Azure a ser usada para criar recursos. | Obrigatório |
    | -O resourcegroup                              | Nome do grupo de recursos do Azure que contém ou conterá o cofre de chaves. | Obrigatório |
    | -Keyvaultname                               | Instância do Azure Key Vault que armazenará seu certificado/segredo de aplicativo de migração de caixa de correio. | Obrigatório |
    | -CertificateName                            | Nome do certificado ao gerar ou pesquisar o certificado no cofre de chaves. | Obrigatório |
    | -CertificateSubject                         | Nome do requerente do certificado do Azure Key Vault, como CN = contoso_fabrikam. | Obrigatório |
    | -ExistingApplicationId                      | Aplicativo de migração de email a ser usado se um já tiver sido criado. | Opcional |
    | -AzureAppPermissions                        | As permissões exigidas para o aplicativo de migração de caixa de correio, como o Exchange ou o MSGraph (Exchange para mover caixas de correio, MSGraph para usar este aplicativo para enviar um convite de link de consentimento para o locatário de recursos). | Obrigatório |
    | -UseAppAndCertGeneratedForSendingInvitation | Parâmetro para usar o aplicativo criado para migração a ser usado para enviar o convite de consentimento para o administrador do locatário de origem. Se não estiver presente, solicitará as credenciais do administrador de destino para se conectar ao Gerenciador de convites do Azure e enviará o convite como administrador de destino. | Opcional |
    | -KeyVaultAuditStorageAccountName            | A conta de armazenamento onde os logs de auditoria do Key Vault serão armazenados. | Opcional |
    | -KeyVaultAuditStorageResourceGroup          | O grupo de recursos que contém a conta de armazenamento para armazenar logs de auditoria de compartimento de chave. | Opcional |
    ||||

6. O script fará uma pausa e solicitará que você aceite ou concorde com o aplicativo de migração de caixa de correio do Exchange que foi criado durante esse processo. Veja um exemplo.

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ``` 

7. Uma URL será exibida na sessão remota do PowerShell. Copie o link fornecido para o consentimento do locatário e cole-o em um navegador da Web.

8. Entre com suas credenciais de administrador global. Quando a tela a seguir for apresentada, selecione **aceitar**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Caixa de diálogo aceitar permissões":::
    
9. Volte para a sessão remota do PowerShell e pressione ENTER para continuar.

10. O script irá configurar os objetos de instalação restantes. Veja um exemplo.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

A configuração do administrador de destino está concluída!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Instruções passo a passo para o administrador de locatários de origem

1.  Entre na sua caixa de correio como-ResourceTenantAdminEmail especificado pelo administrador de destino durante a configuração. Localize o convite de email do locatário de destino e, em seguida, **Selecione o botão introdução.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Caixa de diálogo foi convidado":::

2. Selecione **aceitar** para aceitar o convite.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Caixa de diálogo para aceitar permissões":::

   > [!NOTE]
   > Se você não receber esse email ou não conseguir encontrá-lo, o administrador do locatário de destino foi fornecido como uma URL direta que pode ser concedida para que você aceite o convite. A URL deve estar na transcrição da sessão do PowerShell remoto do administrador de locatários de destino.

3. No centro de administração do Microsoft 365 ou em uma sessão remota do PowerShell, crie um ou mais grupos de segurança habilitados para email para controlar a lista de caixas de correio permitidas pelo locatário de destino para pull (mover) do locatário de origem para o locatário de destino. Você não precisa preencher este grupo com antecedência, mas pelo menos um grupo deve ser fornecido para executar as etapas de configuração (script). Não há suporte para grupos aninhados. 

4. Baixe o script de SetupCrossTenantRelationshipForTargetResource.ps1 para a configuração de locatário de origem do repositório do GitHub [aqui](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 

5. Crie uma conexão do PowerShell remoto para o locatário de origem com suas permissões de administrador do Exchange. As permissões de administrador global não são necessárias para configurar o locatário de origem, somente o locatário de destino por causa do processo de criação de aplicativos do Azure.

6. Altere o diretório para o local do script ou verifique se o script está salvo atualmente no local em sua sessão remota do PowerShell.

7. Execute o script com os seguintes parâmetros e valores necessários.

    | Parâmetro | Valor |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Grupo de segurança habilitado para email criado pelo locatário de origem para as identidades/caixas de correio que estão no escopo para a migração. |
    | -ResourceTenantDomain | Nome do domínio do locatário de origem, como a Fabrikam \. onmicrosoft.com. |
    | -TargetTenantDomain | Nome do domínio do locatário de destino, como contoso \. onmicrosoft.com. |
    | -ApplicationId | ID de aplicativo do Azure (GUID) do aplicativo usado para migração. ID de aplicativo disponível por meio de seu portal do Azure (Azure AD, aplicativos corporativos, nome do aplicativo, ID do aplicativo) ou incluído em seu email de convite.  |
    | -TargetTenantId | ID do locatário do locatário de destino. Por exemplo, a ID de locatário do Azure AD do \. locatário onmicrosoft.com da contoso. |
    |||
    
    Veja um exemplo.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

A configuração do administrador de origem já está concluída!

### <a name="verify-setup"></a>Verificar configuração

Verifique se as relações de organização em locatários de origem e de destino e ponto de extremidade de migração no destino foram criadas com êxito.

#### <a name="target-tenant"></a>Locatário de destino

**Relação de organização**

Verifique se o objeto relationship da organização foi criado e configurado com este comando.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Veja um exemplo:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Ponto de extremidade de migração**

Verifique se o objeto de ponto de extremidade de migração foi criado e configurado com este comando.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Veja um exemplo.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Locatário de origem

**Relação de organização**

Verifique se o objeto relationship da organização foi criado e configurado com este comando.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
Veja um exemplo.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Mover caixas de correio de volta para a fonte original

Se for necessária uma caixa de correio de volta para o locatário de origem original, o mesmo conjunto de etapas e scripts precisará ser executado nos novos locatários de destino e de origem. O objeto de relação de organização existente será atualizado ou acrescentado, não recriado.

## <a name="prepare-target-user-objects-for-migration"></a>Preparar objetos de usuário de destino para migração

Os usuários que estão migrando devem estar presentes no locatário de destino e no sistema do Exchange Online (como MailUsers) marcados com atributos específicos para habilitar movimentações entre locatários. O sistema falhará em movimentações para usuários que não estejam configurados corretamente no locatário de destino. A seção a seguir detalha os requisitos do objeto MailUser para o locatário de destino.

### <a name="prerequisites"></a>Pré-requisitos
  
Você deve garantir que os seguintes objetos e atributos estejam definidos na organização de destino.  

1. Para qualquer caixa de correio que se move de uma organização de origem, você deve provisionar um objeto MailUser na organização de destino: 
   - O MailUser de destino deve ter esses atributos da caixa de correio de origem ou atribuídos ao novo objeto de usuário:
      - ExchangeGUID (fluxo direto da origem para o destino) – o GUID da caixa de correio deve corresponder. O processo de movimentação não continuará se não estiver presente no objeto de destino. 
      - ArchiveGUID (fluxo direto da origem para o destino) – o GUID de arquivo morto deve corresponder. O processo de movimentação não continuará se não estiver presente no objeto de destino. (Isso só será necessário se a caixa de correio de origem estiver habilitada para arquivo). 
      - LegacyExchangeDN (fluxo como proxyAddress, "X500: <LegacyExchangeDN> ") – o legacyExchangeDN deve estar presente no destino MailUser como X500: ProxyAddress. Os processos de movimentação não continuarão se não estiverem presentes no objeto de destino. 
      - UserPrincipalName – o UPN será alinhado à nova empresa de identidade ou de destino do usuário (por exemplo, user@northwindtraders.onmicrosoft.com). 
      - SMTPAddress primário – o endereço SMTP principal será alinhado à nova empresa do usuário (por exemplo, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser fará referência à caixa de correio do usuário atual hospedada no locatário de origem (por exemplo, user@contoso.onmicrosoft.com). Ao atribuir esse valor, verifique se você também está atribuindo PrimarySMTPAddress ou se esse valor definirá o PrimarySMTPAddress, que causará falhas de movimentação. 
      - Não é possível adicionar endereços de proxy SMTP herdados da caixa de correio de origem ao MailUser de destino. Por exemplo, você não pode manter contoso.com no MEU nos objetos de locatário do fabrikam.onmicrosoft.com). Os domínios são associados somente a um locatário do Azure AD ou do Exchange Online.
 
    Exemplo de objeto MailUser de **destino** :
 
    | Atributo             | Valor                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | LaraN                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = First Organization/ou = grupo administrativo do Exchange                                                                   |
    |                       | (FYDIBOHF23SPDLT)/cn = Recipients/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | X500:/o = First Organization/ou = grupo administrativo do Exchange (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | SMTP: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@northwind.com                                                                                           |
    |||

   Exemplo de objeto de caixa de correio de **origem** :

   | Atributo             | Valor                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = First Organization/ou = grupo administrativo do Exchange                   |
   |                       | (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | SMTP: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - Atributos adicionais podem ser incluídos na gravação híbrida do Exchange. Caso contrário, elas deverão ser incluídas. 
   - msExchBlockedSendersHash – grava novamente os dados do remetente seguro online e bloqueados de clientes para o Active Directory local.
   - msExchSafeRecipientsHash – grava novamente os dados do remetente seguro online e bloqueados de clientes para o Active Directory local.
   - msExchSafeSendersHash – grava novamente os dados do remetente seguro online e bloqueados de clientes para o Active Directory local.

2. Se a caixa de correio de origem estiver no LitigationHold e o tamanho dos itens recuperáveis da caixa de correio de origem for maior do que o padrão de nosso banco de dados (30 GB), as movimentações não continuarão, pois a cota de destino é menor do que o tamanho Você pode atualizar o objeto MailUser de destino para fazer a transição dos sinalizadores de caixa de correio ELC do ambiente de origem para o destino, o que dispara o sistema de destino para expandir a cota do MailUser para 100 GB, permitindo assim a movimentação para o destino. Essas instruções funcionarão apenas para a identidade híbrida executando o Azure AD Connect, pois os comandos a serem carimbados não são expostos aos administradores de locatários.

    >[!Note]
    > EXEMPLO – COMO ESTÁ, SEM GARANTIA<br/>Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o Active Directory local de destino (para carimbar o objeto ADUser). Se a origem tiver litígio ou recuperação de item único habilitada, defina isso na conta de destino.  Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. Os locatários de destino não híbridos podem modificar a cota na pasta itens recuperáveis para o MailUsers antes da migração executando o seguinte comando para habilitar a retenção de litígio no objeto MailUser e aumentar a cota para 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Observação isso não funcionará para locatários no híbrido.

4. Os usuários na organização de destino devem ser licenciados com assinaturas apropriadas do Exchange Online aplicáveis à organização. Você pode aplicar uma licença com antecedência de uma movimentação de caixa de correio, mas somente depois que o destino MailUser estiver configurado corretamente com o ExchangeGUID e endereços de proxy. A aplicação de uma licença antes da aplicação de ExchangeGUID resultará em uma nova caixa de correio configurada na organização de destino. 

    > [!Note]
    > Quando você aplica uma licença a uma caixa de correio ou a um objeto MailUser, todos os tipos de SMTP proxyAddresses são depurados para garantir que somente os domínios verificados estão incluídos na matriz EmailAddress do Exchange. 

5. Você deve garantir que o MailUser de destino não tenha ExchangeGuid anterior que não corresponda à ExchangeGuid de origem. Isso pode ocorrer se o MEU de destino tiver sido licenciado anteriormente para o Exchange Online e configurado uma caixa de correio. Se o MailUser de destino tiver sido licenciado anteriormente para ou tivesse um ExchangeGuid que não corresponde ao ExchangeGuid de origem, você precisará executar uma limpeza do MEU de nuvem. Para essas MEUs de nuvem, você pode executar o `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` comando. 

    > [!Caution]
    > Esse processo é irreversível. Se o objeto tiver uma caixa de correio do softDeleted, ele não poderá ser restaurado após esse ponto. Depois de desmarcada, no entanto, você pode sincronizar o ExchangeGuid correto para o objeto de destino e Sra conectará a caixa de correio de origem à caixa de correio de destino recém-criada. (Faça referência ao blog EHLO no novo parâmetro.) 
 
    Encontre objetos que foram previamente caixas de correio usando esse comando.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    Veja um exemplo. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    Limpe a caixa de correio excluída por software usando este comando.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    Veja um exemplo.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>Executar migrações de caixa de correio

As migrações de caixa de correio do Exchange entre locatários são enviadas como lotes de migração iniciados a partir do locatário de destino. Isso é semelhante à forma como os lotes de migração de integração funcionam ao migrar do Exchange no local para o Microsoft 365. 

### <a name="create-migration-batches"></a>Criar lotes de migração

Veja um exemplo de cmdlet de migração de exemplo para Iniciando off moves.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> O endereço de email no arquivo CSV deve ser aquele especificado no locatário de destino, não no locatário de origem.

O envio em lote de migração também é compatível com o novo centro de administração do Exchange ao selecionar a opção de locatário cruzado.
 
#### <a name="update-on-premises-mailusers"></a>Atualizar o MailUsers local

Depois que a caixa de correio é movida da origem para o destino, você deve garantir que os usuários de email locais, tanto de origem quanto de destino, sejam atualizados com o novo targetAddress. Nos exemplos, o targetDeliveryDomain usado na movimentação é **contoso \. onmicrosoft.com**. Atualize os usuários de email com este targetAddress.
 
## <a name="frequently-asked-questions"></a>Perguntas frequentes
 
**Precisamos atualizar o RemoteMailboxes na origem no local após a movimentação?**
 
Sim, você deve atualizar o targetAddress (RemoteRoutingAddress/ExternalEmailAddress) dos usuários do local de origem quando a caixa de correio do locatário de origem for movida para o locatário de destino.  Embora o roteamento de email possa seguir as indicações entre vários usuários de email com targetAddresses diferentes, pesquisas de disponibilidade para usuários de email devem direcionar o local do usuário de caixa de correio. Pesquisas de disponibilidade não causarão vários redirecionamentos. 
 
**O conteúdo da pasta de chat do teams migram vários locatários?** 

Não, o conteúdo da pasta de chat do Teams não migra o locatário cruzado. 
 
**Como posso ver apenas as movimentações que são movimentações entre locatários, e não minha integração e remoções de remoção?**

Use o `-flags` parâmetro. Veja um exemplo.

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**Você pode fornecer scripts de exemplo para copiar atributos usados no teste?**

> [!Note]
> EXEMPLO – COMO ESTÁ, SEM GARANTIA<br/>Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e os serviços de domínio do Active Directory local de destino (para carimbar o objeto ADUser). Se a origem tiver litígio ou recuperação de item único habilitada, defina isso na conta de destino.  Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**Como podemos acessar o Outlook no dia 1 após a movimentação da caixa de correio de uso?**

Como apenas um locatário pode ser proprietário de um domínio, o primeiro SMTPAddress primário não será associado ao usuário no locatário de destino quando a movimentação da caixa de correio for concluída; Apenas os domínios associados ao novo locatário. O Outlook usa o novo UPN Users para autenticar o serviço e o perfil do Outlook espera localizar o SMTPAddress primário herdado para corresponder à caixa de correio no sistema de destino. Como o endereço herdado não está no sistema de destino, o perfil do Outlook não se conectará para localizar a caixa de correio recentemente movida. 

Para essa implantação inicial, os usuários precisarão reconstruir o perfil com o novo endereço SMTP principal e o próprio UPN e sincronizar novamente o conteúdo do OST. 

> [!Note]
> Planeje conforme o lote de usuários para conclusão. Você precisa considerar a capacidade e a utilização da rede quando os perfis de cliente do Outlook são criados e os arquivos OST e OAB subsequentes são baixados para os clientes. 
 
**O que as funções RBAC do Exchange precisam ser membro para configurar ou concluir uma movimentação entre vários locatários?**
 
Há uma matriz de funções com base na pressuposição de tarefas delegadas ao executar uma movimentação de caixa de correio. No momento, são necessárias duas funções:  

- A primeira função é para uma tarefa de configuração única que estabelece a autorização de mover o conteúdo para dentro ou para fora do seu limite de locatário/organização. Como a transferência de dados do controle organizacional é uma preocupação crucial para todas as empresas, decidimos com a maior função atribuída do administrador da organização (OrgAdmin). Essa função deve alterar ou configurar um novo OrganizationRelationship que define o-MailboxMoveCapability com a organização remota. Somente o OrgAdmin pode alterar a configuração MailboxMoveCapability, enquanto outros atributos no OrganizationRelationhip podem ser gerenciados pelo administrador de compartilhamento federado. 
 
- A função de execução dos comandos de movimentação real pode ser delegada a uma função de nível inferior. A função das caixas de correio de movimentação é atribuída à capacidade de mover caixas de correio para dentro ou para fora da organização usando o `-RemoteTenant` parâmetro.  

**Como direcionarmos qual endereço SMTP está selecionado para o targetAddress (TargetDeliveryDomain) na caixa de correio convertida (para a conversão MailUser)?**
 
As movimentações de caixa de correio do Exchange usando o Sra targetAddress na caixa de correio de origem original ao converter em um MailUser correspondendo a um endereço de email (proxyAddress) no objeto de destino. O processo usa o valor-TargetDeliveryDomain passado para o comando move e, em seguida, verifica se há um proxy correspondente para esse domínio no lado de destino. Quando encontramos uma correspondência, a proxyAddress correspondente é usada para definir o ExternalEmailAddress (targetAddress) no objeto Mailbox convertido (agora MailUser).
 
**Como a transição de permissões de caixa de correio?**

As permissões de caixa de correio incluem enviar em nome de e acesso à caixa de correio: 

- Enviar em nome de (AD: publicDelegates) armazena o DN dos destinatários com acesso à caixa de correio de um usuário como um representante. Esse valor é armazenado no Active Directory e, no momento, não é movido como parte da transição da caixa de correio. Se a caixa de correio de origem tiver publicDelegates definido, será necessário recarimbar o publicDelegates na caixa de correio de destino quando a conversão de MEU para caixa de correio for concluída no ambiente de destino usando o `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` comando. 
 
- As permissões de caixa de correio armazenadas na caixa de correio serão movidas com a caixa de correio quando a entidade de segurança e o representante forem movidos para o sistema de destino. Por exemplo, o usuário TestUser_7 é concedido FullAccess à caixa de correio TestUser_8 no locatário SourceCompany.onmicrosoft.com. Após a movimentação da caixa de correio ser concluída para o TargetCompany.onmicrosoft.com, as mesmas permissões são configuradas no diretório de destino. Exemplos usando *Get-MailboxPermission* para TestUser_7 nos locatários de origem e de destino são mostrados abaixo. Os cmdlets do Exchange são prefixados com a origem e o destino de acordo. 
 
Veja um exemplo da saída da permissão de caixa de correio antes de mover. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Veja um exemplo da saída da permissão de caixa de correio após a movimentação. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Não há suporte para permissões de caixa de correio e calendário entre locatários. Você deve organizar entidades e representantes em lotes de movimentação consolidada para que essas caixas de correio conectadas sejam transformadas ao mesmo tempo do locatário de origem. 
 
## <a name="known-issues"></a>Problemas conhecidos 

-  **Problema: os arquivos mortos expandidos automáticos não podem ser migrados.** O recurso de migração entre locatários suporta migrações da caixa de correio principal e caixa de correio de arquivo morto para um usuário específico. No entanto, se o usuário na fonte tiver um arquivo morto de expansão automática – o que significa mais de uma caixa de correio de arquivo morto, o recurso não poderá migrar os arquivos adicionais.

- **Problema: o Cloud MailUsers com bloqueio de proxyAddress SMTP não proprietário Sra move o plano de fundo.** Ao criar objetos MailUser de locatário de destino, você deve garantir que todos os endereços de proxy SMTP pertençam à organização de locatário de destino. Se uma proxyAddress SMTP existir no usuário de email de destino que não pertença ao locatário local, a conversão do MailUser para a caixa de correio será impedida. Isso se deve à nossa garantia de que os objetos de caixa de correio só podem enviar emails de domínios para os quais o locatário é autoritativo (domínios reivindicados pelo locatário): 
- 
   - Ao sincronizar os usuários no local usando o Azure AD Connect, configure os objetos do MailUser no local com o ExternalEmailAddress apontando para o locatário de origem onde a caixa de correio existe (laran@contoso \. onmicrosoft.com) e você carimba o PrimarySmtpAddress como um domínio que reside no locatário de destino (Lara.Newton@northwind \. com). Esses valores são sincronizados com o locatário, e um usuário de email apropriado é provisionado e está pronto para a migração. Um objeto de exemplo é mostrado aqui.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > O endereço *contoso. onmicrosoft \. com* *não* está presente na matriz emailaddresss/proxyAddresses.

- **Problema: os objetos MailUser com endereços SMTP "externos" primários são modificados/redefinidos para os domínios "internos" da empresa afirmados**

   Os objetos MailUser são ponteiros para caixas de correio não locais. No caso de migrações de caixa de correio de locatário cruzado, usamos objetos MailUser para representar a caixa de correio de origem (da perspectiva da organização de destino) ou a caixa de correio de destino (da perspectiva da organização de origem). O MailUsers terá um ExternalEmailAddress (targetAddress) que aponta para o endereço SMTP da caixa de correio real (ProxyTest \@ fabrikam \. onmicrosoft.com) e endereço primarySMTP que representa o endereço SMTP exibido do usuário da caixa de correio no diretório. Algumas organizações optam por exibir o endereço SMTP principal como um endereço SMTP externo, não como um endereço de propriedade/verificado pelo locatário local (como fabrikam.com em vez de contoso.com).  No entanto, depois que um objeto de plano do serviço do Exchange é aplicado ao MailUser via operações de licenciamento, o endereço SMTP principal é modificado para ser exibido como um domínio verificado pela organização local (contoso.com). Há dois motivos possíveis:
   
   - Quando qualquer plano de serviço do Exchange é aplicado a um MailUser, o processo do Azure AD começa a impor o scrubbing de proxy para garantir que a organização local não possa enviar emails, falsificar ou email de outro locatário. Qualquer endereço SMTP em um objeto Recipient com estes planos de serviço será removido se o endereço não for verificado pela organização local. Como é o caso no exemplo, o \. domínio com do FABIKAM não é verificado pelo locatário do \. onmicrosoft.com da Contoso, portanto, a depuração remove esse \. domínio com da Fabrikam. Se quiser persistir esse domínio externo no MailUser, antes da migração ou após a migração, você precisará alterar seus processos de migração para retirar as licenças após a conclusão da movimentação ou antes da movimentação para garantir que os usuários tenham a marca externa esperada aplicada. Você precisará garantir que o objeto de caixa de correio seja devidamente licenciado para não afetar o serviço de email.<br/><br/>Um script de exemplo para remover os planos de serviço em um MailUser no \. locatário da Contoso onmicrosoft.com é mostrado aqui.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Os resultados no conjunto de onplans atribuídos são mostrados aqui.

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       O PrimarySMTPAddress do usuário não está mais depurado. O domínio fabrikam.com não pertence ao locatário contoso.onmicrosoft.com e persistirá como o endereço SMTP principal mostrado no diretório.

       Veja um exemplo.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Quando msExchRemoteRecipientType é definido como 8 (DeprovisionMailbox), para MailUsers locais que são migrados para o locatário de destino, a lógica de depuração de proxy no Azure removerá domínios não pertencentes e redefinirá o primarySMTP para um domínio de propriedade. Limpando msExchRemoteRecipientType no MailUser local, a lógica de limpeza de proxy não se aplica mais. <br/><br>Veja a seguir o conjunto completo de possíveis planos de serviço que incluem o Exchange Online.

   | Nome                                              |
   |---------------------------------------------------|
   | Armazenamento de descoberta eletrônica avançado (500GB)               |
   | Sistema de Proteção de Dados do cliente                                  |
   | Prevenção contra Perda de Dados                              |
   | Serviços CAL do Exchange Enterprise (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (plano 1)                          |
   | Exchange Online (Plano 2)                          |
   | Arquivamento do Exchange Online para Exchange Online     |
   | Arquivamento do Exchange Online para Exchange Server     |
   | Complemento de usuário inativo do Exchange Online              |
   | Quiosque do Exchange Online                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Plano 1                            |
   | POP do Exchange Online                               |
   | Proteção do Exchange Online                        |
   | Barreiras de informações                              |
   | Proteção de Informações para o Office 365 – Premium   |
   | Proteção de informações para o Office 365 – Padrão  |
   | Ideias do myAnalytics                           |
   | Auditoria avançada da Microsoft 365                   |
   | Microsoft Bookings                                |
   | Centro de negócios da Microsoft                         |
   | Microsoft MyAnalytics (Completo)                      |
   | Descoberta Eletrônica Avançada do Office 365                    |
   | Microsoft defender para Office 365 (plano 1)    |
   | Microsoft defender para Office 365 (plano 2)    |
   | Privileged Access Management para Office 365           |
   | Criptografia Premium no Office 365                  |
    
