---
title: Migração de caixa de correio entre locatários
description: Como mover caixas de correio entre locatários do Microsoft 365 ou Office 365.
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
ms.openlocfilehash: 4296879b36e26f11f945105ccebea351ad88314d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029521"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migração de caixa de correio entre locatários (visualização)

Anteriormente, quando um locatário do Exchange Online precisava mover caixas de correio para outro locatário no mesmo serviço do Exchange Online, ele teria que removê-las completamente para o local e, em seguida, abordá-las para um novo locatário. Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários nos locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais. Isso elimina a necessidade de remoção e integração de caixas de correio.

Normalmente, durante fusões ou desa instituções, você precisa da capacidade de mover usuários e conteúdo para um novo locatário. Quando o administrador do locatário de destino executa a movimentação, ela é chamada de movimentação Pull, semelhante às migrações de integração na nuvem no local.

As movimentações de caixa de correio entre locatários do Exchange são totalmente autoatendida por administradores de locatários, usando interfaces conhecidas que podem ser scripts em fluxos de trabalho maiores necessários para fazer a transição de usuários para a nova organização. Os administradores podem usar o cmdlet, disponível por meio da função de gerenciamento Mover Caixas de Correio, para executar movimentações `New-MigrationBatch` entre locatários. O processo de movimentação inclui verificações de autorização de locatário durante a sincronização e finalização da caixa de correio. 
 
Os usuários que estão migrando devem estar presentes no sistema do Exchange Online do locatário de destino como MailUsers, marcados com atributos específicos para habilitar as movimentações entre locatários. O sistema falhará nas movimentações para usuários que não estão devidamente definidos no locatário de destino.  

Quando as movimentações são concluídas, a caixa de correio do sistema de origem é convertida em MailUser e o targetAddress (mostrado como ExternalEmailAddress no Exchange) é marcado com o endereço de roteamento para o locatário de destino. Esse processo deixa o MailUser herdado no locatário de origem e permite um período de co-existência e roteamento de email. Quando os processos empresariais permitem, o locatário de origem pode remover o MailUser de origem ou convertê-los em um contato de email. 

As migrações de caixa de correio entre locatários do Exchange são suportadas para locatários somente em nuvem ou híbrida ou qualquer combinação dos dois.

Este artigo descreve o processo de movimentações de caixa de correio entre locatários e fornece orientações sobre como preparar locatários de origem e destino para a movimentação de conteúdo.  

## <a name="preparing-source-and-target-tenants"></a>Preparando locatários de origem e destino

O recurso de migração de caixa de correio do Exchange entre locatários exige autorização e o exame para migrações entre locatários. Usando o aplicativo Azure Enterprise e as soluções de armazenamento do Key Vault, os administradores de locatários agora têm permissão para gerenciar a autorização e o controle de migrações de caixa de correio do Exchange Online de um locatário para outro. As movimentações de caixa de correio entre locatários suportam um modelo de convite e consentimento para estabelecer um aplicativo do Azure Active Directory (Azure AD) usado para autenticação entre um par de locatários. Componentes adicionais, como um relacionamento de organização e um ponto de extremidade de migração, também são necessários.

Esta seção não inclui as etapas específicas necessárias para preparar os objetos de usuário MailUser no diretório de destino, nem inclui o comando de exemplo para enviar um lote de migração. Consulte Preparar [objetos de usuário de destino para migração](#prepare-target-user-objects-for-migration) para essas informações.

## <a name="prerequisites"></a>Pré-requisitos

O recurso de movimentação de caixa de correio entre locatários exige que o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) estabeleça um aplicativo do Azure específico de par de locatários para armazenar e acessar com segurança o certificado/segredo usado para autenticar e autorizar a migração de caixa de correio de um locatário para o outro, removendo quaisquer requisitos para compartilhar certificados/segredos entre locatários. 

Antes de começar, certifique-se de ter as permissões necessárias para executar os scripts de implantação a fim de configurar o Azure Key Vault, o aplicativo Mover Caixa de Correio, o Ponto de Extremidade de Migração EXO e o Relacionamento de Organização EXO. Normalmente, o Administrador Global tem permissão para executar todas as etapas de configuração.

Além disso, os grupos de segurança habilitados para email no locatário de origem são necessários antes da execução da instalação. Esses grupos são usados para escopo da lista de caixas de correio que podem mudar do locatário de origem (ou às vezes chamado de recurso) para o locatário de destino. Isso permite que o administrador do locatário de origem restrinja ou denove o conjunto específico de caixas de correio que precisam ser movidas, impedindo que usuários não intencionais sejam migrados. Não há suporte para grupos aninhados.

Você também precisará se comunicar com sua empresa parceira confiável (com quem você vai mover caixas de correio) para obter a ID de locatário do Microsoft 365. Essa ID de locatário é usada no campo Relacionamento da `DomainName` Organização.

Para obter a ID de locatário de uma assinatura, entre no centro de administração do Microsoft 365 e vá para [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Clique no ícone de cópia da propriedade de ID de locatário para copiá-lo para a área de transferência.

Veja como funciona o processo.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparação do locatário para migração de caixa de correio.":::

[Veja uma versão maior desta imagem.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Preparar locatários

Em um nível alto, as seguintes ações de configuração ocorrem ao executar os scripts de instalação.

Prepare o locatário de destino:

1. Se um Grupo de Recursos do Azure existente não for fornecido, um novo será criado (SCRIPT).
2. Se um Key Vault existente não for fornecido, um novo será criado (SCRIPT).
3. Uma nova Política de Acesso é criada para o aplicativo de Migração de Caixa de Correio do Exchange Online (SCRIPT) do Office 365.
4. Um novo certificado é criado (ou existente, se especificado) para manter o segredo do aplicativo de migração (SCRIPT).
5. Um novo aplicativo do Azure AD é criado (SCRIPT).
6. O certificado/segredo é carregado no aplicativo de migração (SCRIPT).
7. As permissões de migração de caixa de correio são atribuídas ao aplicativo (SCRIPT).
8. O script de implantação pausa até que o administrador de destino consenta com seu próprio aplicativo (SCRIPT).
9. O administrador do locatário de destino concorda com as permissões concedidas ao aplicativo (MANUAL).
10. Um relacionamento de organização é criado para o locatário de destino (SCRIPT).
11. Um ponto de extremidade de migração é criado para puxar caixas de correio para o locatário de destino (SCRIPT).

Prepare o locatário de origem:

1. O administrador do locatário de origem aceita o consentimento para o convite do aplicativo de Migração de Caixa de Correio do locatário de destino (MANUAL).
2. O administrador de locatários de origem cria um grupo de segurança habilitado para email em seu locatário para conter a lista de caixas de correio que podem ser movidas pelo aplicativo de migração (MANUAL).
3. Um relacionamento de organização é criado para o locatário de destino especificando que o aplicativo de migração de caixa de correio deve ser usado para verificação OAuth para aceitar a solicitação de movimentação (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Instruções passo a passo para o administrador do locatário de destino

1. Baixe o SetupCrossTenantRelationshipForTargetTenant.ps1 script para a configuração do locatário de destino no repositório [do GitHub.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Salve o script (SetupCrossTenantRelationshipForTargetTenant.ps1) no computador do qual você executará o script.
3. Crie uma conexão do PowerShell Remoto com o locatário de destino do Exchange Online. Novamente, certifique-se de ter as permissões necessárias para executar os scripts de implantação a fim de configurar o armazenamento e o certificado do Azure Key Vault, o aplicativo Mover Caixa de Correio, o ponto de extremidade de migração exO e o relacionamento de organização EXO.
4. Altere o diretório da pasta de arquivos para o local do script ou verifique se o script está atualmente salvo no local em sua sessão do PowerShell Remoto.
5. Execute o script com os seguintes parâmetros e valores.

    | Parâmetro | Valor | Obrigatório ou opcional
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Domínio de locatário de destino, como contoso \. onmicrosoft.com. | Obrigatório |
    | -ResourceTenantDomain                       | Domínio do locatário de origem, como fabrikam \. onmicrosoft.com. | Obrigatório |
    | -ResourceTenantAdminEmail                   | Endereço de email do administrador do locatário de origem. Este é o administrador de locatários de origem que concordará com o uso do aplicativo de migração de caixa de correio enviado pelo administrador de destino. Este é o administrador que receberá o convite de email para o aplicativo. | Obrigatório |
    | -ResourceTenantId                           | ID da organização do locatário de origem (GUID). | Obrigatório |
    | -SubscriptionId                             | A assinatura do Azure a ser usada para criar recursos. | Obrigatório |
    | -ResourceGroup                              | Nome do grupo de recursos do Azure que contém ou conterá o Key Vault. | Obrigatório |
    | -KeyVaultName                               | Instância do Azure Key Vault que armazenará o certificado/segredo do aplicativo de migração de caixa de correio. | Obrigatório |
    | -CertificateName                            | Nome do certificado ao gerar ou procurar certificado no cofre de chaves. | Obrigatório |
    | -CertificateSubject                         | Nome do assunto do certificado do Azure Key Vault, como CN=contoso_fabrikam. | Obrigatório |
    | -ExistingApplicationId                      | Aplicativo de migração de email a ser usado se já tiver sido criado. | Opcional |
    | -AzureAppPermissions                        | As permissões necessárias para serem concedidas ao aplicativo de migração de caixa de correio, como Exchange ou MSGraph (Exchange para mover caixas de correio, MSGraph para usar este aplicativo para enviar um convite de link de consentimento para o locatário do recurso). | Obrigatório |
    | -UseAppAndCertGeneratedForSendingInvitation | Parâmetro para usar o aplicativo criado para migração a ser usado para enviar convite de link de consentimento para o administrador do locatário de origem. Se não estiver presente, isso solicitará que as credenciais do administrador de destino se conectem ao gerenciador de convites do Azure e enviem o convite como administrador de destino. | Opcional |
    | -KeyVaultAuditStorageAccountName            | A conta de armazenamento onde os logs de auditoria do Key Vault seriam armazenados. | Opcional |
    | -KeyVaultAuditStorageResourceGroup          | O grupo de recursos que contém a conta de armazenamento para armazenar logs de auditoria do Key Vault. | Opcional |
    ||||

    >[!Note]
    > Verifique se você instalou o módulo do PowerShell do Azure AD antes de executar os scripts. Confira aqui as ![ ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) etapas de instalação

6. O script pausa e solicita que você aceite ou consenta com o aplicativo de migração de caixa de correio do Exchange criado durante esse processo. Veja um exemplo.

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. Uma URL será exibida na sessão do PowerShell Remoto. Copie o link fornecido para o consentimento do locatário e o colar em um navegador da Web.

8. Entre com suas credenciais de Administrador Global. Quando a tela a seguir for apresentada, selecione **Aceitar**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Caixa de diálogo Aceitar permissões":::

9. Volte para a sessão do PowerShell Remoto e aperte Enter para continuar.

10. O script configurará os objetos de instalação restantes. Veja um exemplo.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

A configuração do administrador de destino agora está concluída!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Instruções passo a passo para o administrador do locatário de origem

1.  Entre em sua caixa de correio como o -ResourceTenantAdminEmail especificado pelo administrador de destino durante a configuração. Encontre o convite de email do locatário de destino e selecione o **botão Começar.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Você foi convidado para a caixa de diálogo":::

2. Selecione **Aceitar** para aceitar o convite.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Caixa de diálogo para aceitar permissões":::

   > [!NOTE]
   > Se você não receber esse email ou não conseguir encontrá-lo, o administrador do locatário de destino recebeu uma URL direta que pode ser fornecida para você aceitar o convite. A URL deve estar na transcrição da sessão do PowerShell Remoto do administrador do locatário de destino.

3. No Centro de administração do Microsoft 365 ou em uma sessão do PowerShell Remoto, crie um ou mais grupos de segurança habilitados para email para controlar a lista de caixas de correio permitidas pelo locatário de destino para puxar (mover) do locatário de origem para o locatário de destino. Você não precisa preencher esse grupo com antecedência, mas pelo menos um grupo deve ser fornecido para executar as etapas de configuração (script). Não há suporte para grupos de aninhar. 

4. Baixe o SetupCrossTenantRelationshipForResourceTenant.ps1 script para a configuração do locatário de origem no repositório do GitHub aqui: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Crie uma conexão do PowerShell Remoto com o locatário de origem com suas permissões de Administrador do Exchange. As permissões de Administrador Global não são necessárias para configurar o locatário de origem, somente o locatário de destino devido ao processo de criação de aplicativos do Azure.

6. Altere o diretório para o local do script ou verifique se o script está atualmente salvo no local em sua sessão do PowerShell Remoto.

7. Execute o script com os seguintes parâmetros e valores necessários.

    | Parâmetro | Valor |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Grupo de segurança habilitado para email criado pelo locatário de origem para as identidades/caixas de correio que estão no escopo da migração. |
    | -ResourceTenantDomain | Nome de domínio do locatário de origem, como fabrikam \. onmicrosoft.com. |
    | -ApplicationId | A ID do aplicativo do Azure (GUID) do aplicativo usado para migração. ID do aplicativo disponível por meio do portal do Azure (Azure AD, Aplicativos Empresariais, nome do aplicativo, ID do aplicativo) ou incluído no email do convite.  |
    | -TargetTenantDomain | Nome de domínio do locatário de destino, como contoso \. onmicrosoft.com. |
    | -TargetTenantId | ID de locatário do locatário de destino. Por exemplo, a ID de locatário do Azure AD da contoso \. onmicrosoft.com locatário. |
    |||

    Veja um exemplo.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

A configuração do administrador de origem agora está concluída!

### <a name="verify-setup"></a>Verificar a configuração

Verifique se os relacionamentos da organização nos locatários de origem e de destino e no ponto de extremidade de migração no destino foram criados com êxito.

#### <a name="target-tenant"></a>Locatário de destino

**Relacionamento de organização**

Verifique se o objeto de relacionamento da organização foi criado e configurado com esse comando.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Veja um exemplo:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Ponto de extremidade de migração**

Verifique se o objeto do ponto de extremidade de migração foi criado e configurado com esse comando.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Veja um exemplo.

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Locatário de origem

**Relacionamento de organização**

Verifique se o objeto de relacionamento da organização foi criado e configurado com esse comando.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

Veja um exemplo.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Mover caixas de correio de volta para a origem original

Se uma caixa de correio voltar para o locatário de origem original for necessária, o mesmo conjunto de etapas e scripts precisará ser executado nos novos locatários de origem e de destino. O objeto De relacionamento de organização existente será atualizado ou anexado, não recriado.

## <a name="prepare-target-user-objects-for-migration"></a>Preparar objetos de usuário de destino para migração

Os usuários que estão migrando devem estar presentes no locatário de destino e no sistema do Exchange Online (como MailUsers) marcados com atributos específicos para habilitar as movimentações entre locatários. O sistema falhará nas movimentações para usuários que não estão devidamente definidos no locatário de destino. A seção a seguir detalha os requisitos do objeto MailUser para o locatário de destino.

### <a name="prerequisites"></a>Pré-requisitos
  
Você deve garantir que os seguintes objetos e atributos sejam definidos na organização de destino.  

1. Para qualquer caixa de correio que se mover de uma organização de origem, você deve provisionar um objeto MailUser na organização de destino: 

   - O MailUser de destino deve ter esses atributos da caixa de correio de origem ou atribuídos ao novo objeto User:
      - ExchangeGUID (fluxo direto de origem para destino) – O GUID da caixa de correio deve corresponder. O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino. 
      - ArchiveGUID (fluxo direto de origem para destino) – o GUID de arquivo morto deve corresponder. O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino. (Isso só será necessário se a caixa de correio de origem estiver habilitada para Arquivo Morto). 
      - LegacyExchangeDN (fluxo como proxyAddress, "x500: ") – o LegacyExchangeDN deve estar presente no MailUser de destino <LegacyExchangeDN> como x500: proxyAddress. Os processos de movimentação não prosseguirão se isso não estiver presente no objeto de destino. 
      - UserPrincipalName – o UPN será alinhado com a nova identidade ou empresa de destino do usuário (por exemplo, user@northwindtraders.onmicrosoft.com). 
      - SMTPAddress principal – o endereço SMTP principal será alinhado à empresa NEW do usuário (por exemplo, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser fará referência à caixa de correio atual do usuário hospedada no locatário de origem (por exemplo, user@contoso.onmicrosoft.com). Ao atribuir esse valor, verifique se você tem/está atribuindo PrimarySMTPAddress ou esse valor definirá PrimarySMTPAddress que causará falhas de movimentação. 
      - Você não pode adicionar endereços proxy smtp herdado da caixa de correio de origem para MailUser de destino. Por exemplo, você não pode manter contoso.com no MEU em fabrikam.onmicrosoft.com de locatário). Os domínios são associados apenas a um locatário do Azure AD ou do Exchange Online.
 
     Exemplo **de** objeto MailUser de destino:
 
     | Atributo             | Valor                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Exemplo de **objeto de caixa** de correio de origem:

     | Atributo             | Valor                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Atributos adicionais já podem estar incluídos no write-back híbrido do Exchange. Caso não sejam, eles devem ser incluídos. 
   - msExchBlockedSendersHash – Grava novamente dados de remetentes seguros e bloqueados online de clientes para o Active Directory local.
   - msExchSafeRecipientsHash – Grava novamente dados de remetentes seguros e bloqueados online de clientes para o Active Directory local.
   - msExchSafeSendersHash – Grava novamente dados de remetentes seguros e bloqueados online de clientes para o Active Directory local.

2. Se a caixa de correio de origem estiver em LitigationHold e o tamanho dos Itens Recuperáveis da caixa de correio de origem for maior que o padrão do banco de dados (30 GB), as movimentações não continuarão, pois a cota de destino é menor que o tamanho da caixa de correio de origem. Você pode atualizar o objeto MailUser de destino para fazer a transição dos sinalizadores de caixa de correio ELC do ambiente de origem para o destino, o que dispara o sistema de destino para expandir a cota do MailUser para 100 GB, permitindo assim a movimentação para o destino. Essas instruções funcionarão apenas para a identidade híbrida executando o Azure AD Connect, pois os comandos para carimbar os sinalizadores ELC não são expostos aos administradores de locatários.

    >[!Note]
    > EXEMPLO – COMO ESTÁ, SEM GARANTIA<br/>Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o Active Directory local de destino (para carimbar o objeto ADUser). Se a fonte tiver litígio ou recuperação de item único habilitado, de definida na conta de destino.  Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Os locatários de destino não híbridos podem modificar a cota na pasta Itens Recuperáveis para mailUsers antes da migração executando o seguinte comando para habilitar a responsabilidade de litígio no objeto MailUser e aumentando a cota para 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Observe que isso não funcionará para locatários híbridos.

4. Os usuários na organização de destino devem ser licenciados com as assinaturas apropriadas do Exchange Online aplicáveis à organização. Você pode aplicar uma licença antes de uma movimentação de caixa de correio, mas apenas uma vez que o MailUser de destino está corretamente definido com o ExchangeGUID e endereços proxy. A aplicação de uma licença antes da aplicação do ExchangeGUID resultará em uma nova caixa de correio provisionada na organização de destino. 

    > [!Note]
    > Quando você aplica uma licença em um objeto MailUser ou Caixa de Correio, todos os proxyAddresses do tipo SMTP são limpos para garantir que apenas domínios verificados sejam incluídos na matriz Exchange EmailAddresses. 

5. Você deve garantir que o MailUser de destino não tenha ExchangeGuid anterior que não corresponder ao ExchangeGuid de origem. Isso pode ocorrer se o MEU de destino tiver sido licenciado anteriormente para o Exchange Online e provisionado uma caixa de correio. Se o MailUser de destino tiver sido licenciado anteriormente ou tiver um ExchangeGuid que não corresponder ao ExchangeGuid de origem, você precisará executar uma limpeza do MEU de nuvem. Para essas MEUs de nuvem, você pode `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` executar.  

    > [!Caution]
    > Esse processo é irreversível. Se o objeto tiver uma caixa de correio softDeleted, ele não poderá ser restaurado após esse ponto. Uma vez limpo, no entanto, você pode sincronizar o ExchangeGuid correto com o objeto de destino e o MRS conectará a caixa de correio de origem à caixa de correio de destino recém-criada. (Referência do blog EHLO sobre o novo parâmetro.)  

    Encontre objetos que anteriormente eram caixas de correio usando este comando.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    Veja um exemplo. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    Limpe a caixa de correio excluída de forma suave usando este comando.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    Veja um exemplo.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>Executar migrações de caixa de correio

As migrações de caixa de correio do Exchange entre locatários são enviadas como lotes de migração iniciados do locatário de destino. Isso é semelhante à maneira como os lotes de migração de relembro funcionam ao migrar do Exchange local para o Microsoft 365. 

### <a name="create-migration-batches"></a>Criar lotes de migração

Aqui está um cmdlet de lote de migração de exemplo para movimentações de desaquete.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> O endereço de email no arquivo CSV deve ser o especificado no locatário de destino, não o locatário de origem.

O envio de lote de migração também é suportado no novo Centro de Administração do Exchange ao selecionar a opção entre locatários.

#### <a name="update-on-premises-mailusers"></a>Atualizar MailUsers local

Depois que a caixa de correio se mover de origem para destino, você deve garantir que os usuários de email locais, origem e destino, sejam atualizados com o novo targetAddress. Nos exemplos, o targetDeliveryDomain usado na movimentação é **contoso.onmicrosoft.com**. Atualize os usuários de email com este targetAddress.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Precisamos atualizar RemoteMailboxes na origem local após a mudança?**

Sim, você deve atualizar o targetAddress (RemoteRoutingAddress/ExternalEmailAddress) dos usuários locais de origem quando a caixa de correio de locatário de origem for movimentada para o locatário de destino.  Embora o roteamento de email possa seguir as indicações em vários usuários de email com targetAddresses diferentes, as buscas de usuários de email DEVEM direcionar o local do usuário de caixa de correio. As buscas de informações de livre/ocupado não irão seguir vários redirecionamentos. 

**O conteúdo da pasta de chat do Teams migra entre locatários?**  

Não, o conteúdo da pasta de chat do Teams não migra entre locatários.  

**Como posso ver apenas movimentações que são movimentações entre locatários, não minhas movimentações de integração e de integração?**

Use o `-flags` parâmetro. Veja um exemplo.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Você pode fornecer scripts de exemplo para copiar atributos usados no teste?**

> [!Note]
> EXEMPLO – COMO ESTÁ, SEM GARANTIA<br/>Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e os Serviços de Domínio Active Directory locais de destino (para carimbar o objeto ADUser). Se a fonte tiver litígio ou recuperação de item único habilitado, de definida na conta de destino.  Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.

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
**Como acessamos o Outlook no Dia 1 depois que a caixa de correio de uso for movida?**

Como apenas um locatário pode ter um domínio, o antigo SMTPAddress principal não será associado ao usuário no locatário de destino quando a movimentação da caixa de correio for concluída; somente os domínios associados ao novo locatário. Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system. Como o endereço herdado não está no sistema de destino, o perfil do outlook não se conectará para encontrar a caixa de correio recém-movida. 

Para essa implantação inicial, os usuários precisarão recriar seu perfil com seu novo UPN, endereço SMTP principal e ressincronize o conteúdo OST. 

> [!Note]
> Planeje conforme você lote seus usuários para conclusão. Você precisa levar em conta a utilização e a capacidade da rede quando os perfis de cliente do Outlook são criados e os arquivos OST e OAB subsequentes são baixados para os clientes. 
 
**De quais funções do Exchange RBAC preciso ser membro para configurar ou concluir uma movimentação entre locatários?**
 
Há uma matriz de funções com base na suposição de tarefas delegadas ao executar uma movimentação de caixa de correio. Atualmente, duas funções são necessárias:  

- A primeira função é para uma tarefa de configuração única que estabelece a autorização para mover o conteúdo para dentro ou para fora do limite do locatário/organização. Como a movimentação de dados de seu controle organizacional é uma preocupação crítica para todas as empresas, optamos pela função mais alta atribuída de Administrador da Organização (OrgAdmin). Essa função deve alterar ou configurar uma nova OrganizationRelationship que define o -MailboxMoveCapability com a organização remota. Somente o OrgAdmin pode alterar a configuração MailboxMoveCapability, enquanto outros atributos no OrganizationRelationhip podem ser gerenciados pelo administrador de Compartilhamento Federado. 
 
- A função de executar os comandos de movimentação real pode ser delegada a uma função de nível inferior. A função de Mover Caixas de Correio recebe a capacidade de mover caixas de correio para dentro ou para fora da organização usando o `-RemoteTenant` parâmetro.  

**Como podemos direcionar qual endereço SMTP é selecionado para targetAddress (TargetDeliveryDomain) na caixa de correio convertida (para conversão de MailUser)?**
 
Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object. O processo assume o valor -TargetDeliveryDomain passado para o comando de movimentação e verifica se há um proxy correspondente para esse domínio no lado de destino. Quando encontramos uma correspondência, o proxyAddress correspondente é usado para definir ExternalEmailAddress (targetAddress) no objeto de caixa de correio convertida (agora MailUser).
 
**Como fazer a transição de permissões de caixa de correio?**

As permissões de caixa de correio incluem Enviar em Nome de e Acesso à Caixa de Correio: 

- Send On Behalf Of (AD:publicDelegates) armazena o DN dos destinatários com acesso à caixa de correio de um usuário como um representante. Esse valor é armazenado no Active Directory e atualmente não é movimentado como parte da transição da caixa de correio. Se a caixa de correio de origem tiver publicDelegates definida, você precisará executar publicDelegates na Caixa de Correio de destino assim que a conversão de MEU para Caixa de Correio for concluída no ambiente de destino executando `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- As Permissões de Caixa de Correio armazenadas na caixa de correio serão movidas com a caixa de correio quando a entidade de segurança e o representante são movidos para o sistema de destino. Por exemplo, o usuário TestUser_7 é concedido FullAccess à caixa de correio TestUser_8 no locatário SourceCompany.onmicrosoft.com. Depois que a movimentação de caixa de correio TargetCompany.onmicrosoft.com concluída, as mesmas permissões são configuradas no diretório de destino. Exemplos usando *Get-MailboxPermission* para TestUser_7 locatários de origem e destino são mostrados abaixo. Os cmdlets do Exchange têm o prefixo de origem e destino de acordo. 
 
Aqui está um exemplo da saída da permissão da caixa de correio antes de uma movimentação. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Veja um exemplo da saída da permissão da caixa de correio após a movimentação. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Não há suporte para permissões de calendário e caixa de correio entre locatários. Você deve organizar entidades e representantes em lotes de movimentação consolidados para que essas caixas de correio conectadas sejam transição ao mesmo tempo do locatário de origem. 

**Qual proxy X500 deve ser adicionado aos endereços proxy MailUser de destino para habilitar a migração?**  

A migração de caixa de correio entre locatários exige que o valor LegacyExchangeDN do objeto de caixa de correio de origem seja carimbado como um endereço de email x500 no objeto MailUser de destino.  

Exemplo:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Além desse proxy X500, você precisará copiar todos os proxies X500 da caixa de correio na fonte para a caixa de correio no destino.  

**O Azure Key Vault é necessário e quando as transações são feitas?**  

Sim, uma assinatura do Azure é necessária para usar o Key Vault para armazenar o certificado para autorizar a migração. Ao contrário das migrações de integração que usam o nome de usuário & senha para se autenticar na origem, as migrações de caixa de correio entre locatários usam o OAuth e esse certificado como o segredo/credencial. O acesso ao Key Vault deve ser mantido em todas as migrações de caixa de correio, pois ele é acessado uma vez no início e depois do fim da migração, bem como uma vez a cada 24 horas durante os tempos de sincronização incrementais. Você pode revisar os detalhes de custo de AKV [aqui.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)  

**Você tem alguma recomendação para lotes?**  

Não exceder 2.000 caixas de correio por lote. É recomendável enviar lotes duas semanas antes da data de recortar, pois não há impacto para os usuários finais durante a sincronização. Se você precisar de orientação para quantidades de caixas de correio acima de 50.000, entre em contato com a Lista de Distribuição de Comentários de Engenharia em crosstenantmigrationpreview@service.microsoft.com.

**E se eu usar a criptografia de serviço com a Chave do Cliente?**

A caixa de correio será descriptografada antes da movimentação. Verifique se a Chave do Cliente está configurada no locatário de destino, se ainda for necessária. Consulte [aqui](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) para obter mais informações.  

**Qual é o tempo estimado de migração?**

Para ajudá-lo a planejar [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) a migração, a tabela apresentada aqui mostra as diretrizes sobre quando esperar a conclusão de migrações de caixa de correio em massa ou migrações individuais. Essas estimativas são baseadas em uma análise de dados de migrações anteriores do cliente. Como cada ambiente é exclusivo, sua velocidade de migração exata pode variar.  

Lembre-se de que esse recurso está atualmente em visualização, e o SLA e quaisquer Níveis de Serviço aplicáveis não se aplicam a nenhum problema de desempenho ou disponibilidade durante o status de visualização desse recurso.

## <a name="known-issues"></a>Problemas conhecidos  

-  **Problema: arquivos expandidos automaticamente não podem ser migrados.** O recurso de migração entre locatários suporta migrações da caixa de correio principal e da caixa de correio de arquivo morto para um usuário específico. No entanto, se o usuário na fonte tiver um arquivo morto expandido automaticamente, ou seja, mais de uma caixa de correio de arquivo morto, o recurso não poderá migrar os arquivos morto adicionais.

- **Problema: Cloud MailUsers com proxy smtp não pertencente ao bloco MRS move o plano de fundo.** Ao criar objetos MailUser de locatário de destino, você deve garantir que todos os endereços proxy SMTP pertencem à organização de locatário de destino. Se houver um proxyAddress SMTP no usuário de email de destino que não pertença ao locatário local, a conversão de MailUser em Caixa de Correio será impedida. Isso se deve à nossa garantia de que os objetos de caixa de correio só podem enviar emails de domínios para os quais o locatário é autoritativo (domínios reivindicados pelo locatário): 

   - Ao sincronizar usuários do local usando o Azure AD Connect, você provisiona objetos MailUser locais com ExternalEmailAddress apontando para o locatário de origem onde a caixa de correio existe (laran@contoso.onmicrosoft.com) e carimba o PrimarySMTPAddress como um domínio que reside no locatário de destino (Lara.Newton@northwind.com). Esses valores são sincronizados com o locatário e um usuário de email apropriado está provisionado e pronto para a migração. Um objeto de exemplo é mostrado aqui.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > O *contoso.onmicrosoft.com* endereço não *está* presente na matriz EmailAddresses/proxyAddresses.

- **Problema: os objetos MailUser com endereços SMTP primários "externos" são modificados/redefinidos para domínios "internos" reivindicados pela empresa**

   Objetos MailUser são ponteiros para caixas de correio não locais. No caso de migrações de caixa de correio entre locatários, usamos objetos MailUser para representar a caixa de correio de origem (da perspectiva da organização de destino) ou a caixa de correio de destino (da perspectiva da organização de origem). MailUsers terá um ExternalEmailAddress (targetAddress) que aponta para o endereço smtp da caixa de correio real (ProxyTest@fabrikam.onmicrosoft.com) e o endereço primarySMTP que representa o endereço SMTP exibido do usuário de caixa de correio no diretório. Algumas organizações optam por exibir o endereço SMTP principal como um endereço SMTP externo, não como um endereço de propriedade/verificado pelo locatário local (como fabrikam.com em vez de contoso.com).  No entanto, depois que um objeto de plano de serviço do Exchange é aplicado ao MailUser por meio de operações de licenciamento, o endereço SMTP principal é modificado para aparecer como um domínio verificado pela organização local (contoso.com). Há dois motivos possíveis:
   
   - Quando qualquer plano de serviço do Exchange é aplicado a um MailUser, o processo do Azure AD começa a impor a depuração de proxy para garantir que a organização local não consiga enviar emails, spoof ou emails de outro locatário. Qualquer endereço SMTP em um objeto de destinatário com esses planos de serviço será removido se o endereço não for verificado pela organização local. Como é o caso no exemplo, o domínio Fabikam.com não é verificado pelo locatário do contoso.onmicrosoft.com, portanto, a depuração remove esse fabrikam.com domínio. Se você quiser manter esses domínios externos em MailUser, antes da migração ou após a migração, será necessário alterar seus processos de migração para retirar licenças após a conclusão da movimentação ou antes da movimentação para garantir que os usuários tenham a identidade visual externa esperada aplicada. Você precisará garantir que o objeto de caixa de correio está licenciado corretamente para não afetar o serviço de email.<br/><br/>Um script de exemplo para remover os planos de serviço em um MailUser no Contoso.onmicrosoft.com locatário é mostrado aqui.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Os resultados no conjunto de ServicePlans atribuídos são mostrados aqui.

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
 
       PrimarySMTPAddress do usuário não é mais limpo. O fabrikam.com domínio não pertence ao locatário contoso.onmicrosoft.com e persistirá como o endereço SMTP principal mostrado no diretório.

       Veja um exemplo.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Quando msExchRemoteRecipientType é definida como 8 (DeprovisionMailbox), para MailUsers locais que são migrados para o locatário de destino, a lógica de depuração de proxy no Azure removerá domínios não proprietários e redefinirá o primarySMTP para um domínio de propriedade. Ao limpar msExchRemoteRecipientType no MailUser local, a lógica de limpeza de proxy não se aplica mais. <br/><br>Abaixo está o conjunto completo de planos de serviço possíveis que incluem o Exchange Online.

   | Nome                                              |
   |---------------------------------------------------|
   | Armazenamento Avançado de Descobertas Públicas (500 GB)               |
   | Sistema de Proteção de Dados do cliente                                  |
   | Prevenção contra Perda de Dados                              |
   | Exchange Enterprise CAL Services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (Plano 1)                          |
   | Exchange Online (Plano 2)                          |
   | Arquivamento do Exchange Online para Exchange Online     |
   | Arquivamento do Exchange Online para Exchange Server     |
   | Complemento do usuário inativo do Exchange Online              |
   | Quiosque do Exchange Online                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Plano 1                            |
   | Exchange Online POP                               |
   | Proteção do Exchange Online                        |
   | Barreiras de informações                              |
   | Proteção de Informações para o Office 365 – Premium   |
   | Proteção de informações para o Office 365 – Padrão  |
   | Insights do MyAnalytics                           |
   | Auditoria Avançada do Microsoft 365                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Completo)                      |
   | Descoberta Eletrônica Avançada do Office 365                    |
   | Microsoft Defender para Office 365 (Plano 1)    |
   | Microsoft Defender para Office 365 (Plano 2)    |
   | Privileged Access Management para Office 365           |
   | Criptografia Premium no Office 365                  |
    
