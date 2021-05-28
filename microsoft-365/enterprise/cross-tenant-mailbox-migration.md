---
title: Migração de caixa de correio entre locatários
description: Como mover caixas de correio entre Microsoft 365 ou Office 365 locatários.
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
ms.openlocfilehash: f9a4b7679a33d6722336ee5412e4992389ba915f
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694408"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migração de caixa de correio entre locatários (visualização)

Anteriormente, quando um locatário do Exchange Online precisava mover caixas de correio para outro locatário no mesmo serviço de Exchange Online, ele teria que removê-las completamente para o local e, em seguida, abordá-las para um novo locatário. Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários em locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais. Isso remove a necessidade de retirada e integração de caixas de correio.

Normalmente, durante fusões ou desinvestções, você precisa da capacidade de mover usuários e conteúdo para um novo locatário. Quando o administrador de locatários de destino executa a movimentação, ela é chamada de movimentação pull, semelhante às migrações locais para integração na nuvem.

As movimentações de caixa de correio entre locatários Exchange são totalmente autoatendadas pelos administradores de locatários, usando interfaces conhecidas que podem ser roteadas para os fluxos de trabalho maiores necessários para fazer a transição dos usuários para sua nova organização. Os administradores podem usar o cmdlet, disponível por meio da função de gerenciamento Mover Caixas de Correio, para executar movimentações `New-MigrationBatch` entre locatários. O processo de movimentação inclui verificações de autorização de locatário durante a sincronização e a finalização da caixa de correio. 
 
Os usuários que migram devem estar presentes no sistema Exchange Online de locatários de destino como MailUsers, marcados com atributos específicos para habilitar as movimentações entre locatários. O sistema falhará em movimentações para usuários que não estão corretamente definidos no locatário de destino.  

Quando as movimentações são concluídas, a caixa de correio do sistema de origem é convertida em MailUser e o targetAddress (mostrado como ExternalEmailAddress no Exchange) é marcado com o endereço de roteamento para o locatário de destino. Esse processo deixa o MailUser herdado no locatário de origem e permite um período de co-existência e roteamento de emails. Quando os processos de negócios permitem, o locatário de origem pode remover o MailUser de origem ou convertê-lo em um contato de email. 

As migrações de Exchange de caixa de correio entre locatários são suportadas apenas para locatários em nuvem ou híbrida ou qualquer combinação dos dois.

Este artigo descreve o processo de movimentações de caixa de correio entre locatários e fornece orientações sobre como preparar locatários de origem e destino para a movimentação de conteúdo.  

## <a name="preparing-source-and-target-tenants"></a>Preparando locatários de origem e destino

O recurso de migração de Exchange caixa de correio entre locatários requer autorização e scoping para migrações entre locatários. Usando o aplicativo Enterprise do Azure e soluções de armazenamento do Cofre de Chaves, os administradores de locatários agora estão habilitados para gerenciar tanto a autorização quanto o escoamento de migrações de Exchange Online de caixa de correio de um locatário para outro. As movimentações de caixa de correio entre locatários suportam um modelo de convite e consentimento para estabelecer um aplicativo Azure Active Directory (Azure AD) usado para autenticação entre um par de locatários. Componentes adicionais, como uma relação de organização e um ponto de extremidade de migração, também são necessários.

Esta seção não inclui as etapas específicas necessárias para preparar os objetos de usuário MailUser no diretório de destino, nem inclui o comando de exemplo para enviar um lote de migração. Confira Preparar [objetos de usuário de destino para migração](#prepare-target-user-objects-for-migration) para essas informações.

## <a name="prerequisites"></a>Pré-requisitos

O recurso de movimentação de caixa de correio entre locatários exige que o [Azure Key Vault](/azure/key-vault/basic-concepts) estabeleça um aplicativo do Azure específico do par de locatários para armazenar e acessar com segurança o certificado/segredo usado para autenticar e autorizar a migração de caixa de correio de um locatário para o outro, removendo todos os requisitos para compartilhar certificados/segredos entre locatários. 

Antes de começar, certifique-se de que você tem as permissões necessárias para executar os scripts de implantação para configurar o Azure Key Vault, o aplicativo Mover Caixa de Correio, o Ponto de Extremidade de Migração do EXO e o Relacionamento da Organização do EXO. Normalmente, o Administrador Global tem permissão para executar todas as etapas de configuração.

Além disso, grupos de segurança habilitados para email no locatário de origem são necessários antes de executar a instalação. Esses grupos são usados para escopo da lista de caixas de correio que podem mudar do locatário de origem (ou às vezes chamado de recurso) para o locatário de destino. Isso permite que o administrador do locatário de origem restrinja ou escopo o conjunto específico de caixas de correio que precisam ser movidas, impedindo que usuários não intencionados sejam migrados. Não há suporte para grupos aninhados.

Você também precisará se comunicar com sua empresa parceira confiável (com a qual você estará movendo caixas de correio) para obter sua ID Microsoft 365 locatário. Essa ID de locatário é usada no campo Relacionamento da `DomainName` Organização.

Para obter a ID do locatário de uma assinatura, entre no centro de administração Microsoft 365 e vá para [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Clique no ícone de cópia da propriedade ID do locatário para copiá-lo para a área de transferência.

Veja como o processo funciona.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparação do locatário para migração de caixa de correio.":::

[Consulte uma versão maior dessa imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Preparar locatários

Em alto nível, as seguintes ações de configuração ocorrem ao executar os scripts de instalação.

Preparar o locatário de destino:

1. Se um grupo de recursos do Azure existente não for fornecido, um novo será criado (SCRIPT).
2. Se um Cofre de Chaves existente não for fornecido, um novo será criado (SCRIPT).
3. Uma nova Política de Acesso é criada para o Office 365 Exchange Online de Migração de Caixa de Correio (SCRIPT).
4. Um novo certificado é criado (ou existente, se especificado) para manter o segredo para o aplicativo de migração (SCRIPT).
5. Um novo aplicativo do Azure AD é criado (SCRIPT).
6. O certificado/segredo é carregado no aplicativo de migração (SCRIPT).
7. As permissões de migração de caixa de correio são atribuídas ao aplicativo (SCRIPT).
8. O script de implantação pausa até que o administrador de destino consenta com seu próprio aplicativo (SCRIPT).
9. O administrador do locatário de destino consente com as permissões concedidas ao aplicativo (MANUAL).
10. Uma relação de organização é criada para o locatário de destino (SCRIPT).
11. Um ponto de extremidade de migração é criado para puxar caixas de correio para o locatário de destino (SCRIPT).

Preparar o locatário de origem:

1. O administrador do locatário de origem aceita o consentimento para o convite do aplicativo de Migração de Caixa de Correio do locatário de destino (MANUAL).
2. O administrador do locatário de origem cria um grupo de segurança habilitado para email em seu locatário para conter a lista de caixas de correio permitidas para serem movidas pelo aplicativo de migração (MANUAL).
3. Uma relação de organização é criada com o locatário de destino especificando que o aplicativo de migração de caixa de correio deve ser usado para verificação OAuth para aceitar a solicitação de movimentação (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Instruções passo a passo para o administrador do locatário de destino

1. Baixe o SetupCrossTenantRelationshipForTargetTenant.ps1 script do locatário de destino no [repositório GitHub .](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Salve o script (SetupCrossTenantRelationshipForTargetTenant.ps1) no computador do qual você executará o script.
3. Crie uma conexão remota do PowerShell com o Exchange Online de destino. Novamente, certifique-se de ter as permissões necessárias para executar os scripts de implantação para configurar o certificado e o armazenamento e o certificado do Cofre de Chaves do Azure, o aplicativo Mover Caixa de Correio, o Ponto de Extremidade de Migração do EXO e o Relacionamento da Organização do EXO.
4. Altere o diretório da pasta de arquivos para o local do script ou verifique se o script está salvo no momento no local em sua sessão do PowerShell Remoto.
5. Execute o script com os seguintes parâmetros e valores.

    | Parâmetro | Valor | Obrigatório ou Opcional
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Domínio de locatário de destino, como fabrikam \. onmicrosoft.com. | Obrigatório |
    | -ResourceTenantDomain                       | Domínio de locatário de origem, como contoso \. onmicrosoft.com. | Obrigatório |
    | -ResourceTenantAdminEmail                   | Endereço de email do administrador do locatário de origem. Este é o administrador do locatário de origem que consentiá com o uso do aplicativo de migração de caixa de correio enviado do administrador de destino. Este é o administrador que receberá o convite de email para o aplicativo. | Obrigatório |
    | -ResourceTenantId                           | ID da organização de locatários de origem (GUID). | Obrigatório |
    | -SubscriptionId                             | A assinatura do Azure a ser usada para criar recursos. | Obrigatório |
    | -ResourceGroup                              | Nome do grupo de recursos do Azure que contém ou conterá o Cofre de Chaves. | Obrigatório |
    | -KeyVaultName                               | Instância do Azure Key Vault que armazenará seu certificado/segredo do aplicativo de migração de caixa de correio. | Obrigatório |
    | -CertificateName                            | Nome do certificado ao gerar ou pesquisar certificado no cofre de chaves. | Obrigatório |
    | -CertificateSubject                         | Nome do assunto do certificado do Azure Key Vault, como CN=contoso_fabrikam. | Obrigatório |
    | -AzureResourceLocation                      | O local do grupo de recursos do Azure e do cofre de chaves. | Obrigatório |
    | -ExistingApplicationId                      | Aplicativo de migração de email a ser usado se já tiver sido criado. | Opcional |
    | -AzureAppPermissions                        | As permissões necessárias para serem concedidas ao aplicativo de migração de caixa de correio, como Exchange ou MSGraph (Exchange para mover caixas de correio, MSGraph para usar esse aplicativo para enviar um convite de link de consentimento para locatário de recursos). | Obrigatório |
    | -UseAppAndCertGeneratedForSendingInvitation | Parâmetro para usar o aplicativo criado para migração a ser usado para enviar convite de link de consentimento para o administrador do locatário de origem. Se não estiver presente, solicitará que as credenciais do administrador de destino se conectem ao gerenciador de convites do Azure e enviem o convite como administrador de destino. | Opcional |
    | -KeyVaultAuditStorageAccountName            | A conta de armazenamento onde os logs de auditoria do Key Vault seriam armazenados. | Opcional |
    | -KeyVaultAuditStorageResourceGroup          | O grupo de recursos que contém a conta de armazenamento para armazenar logs de auditoria do Key Vault. | Opcional |
    ||||

    >[!Note]
    > Verifique se você instalou o módulo do PowerShell do Azure AD antes de executar os scripts. Consulte aqui ![ para etapas de ](/powershell/azure/install-az-ps?view=azps-5.1.0) instalação

6. O script pausa e solicita que você aceite ou consenta com o aplicativo Exchange de migração de caixa de correio criado durante esse processo. Veja um exemplo.

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

9. Alternar de volta para a sessão do PowerShell remoto e aperte Enter para continuar.

10. O script configurará os objetos de instalação restantes. Veja um exemplo.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

A configuração do administrador de destino agora está concluída!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Instruções passo a passo para o administrador do locatário de origem

1.  Entre em sua caixa de correio como o -ResourceTenantAdminEmail especificado pelo administrador de destino durante a instalação. Encontre o convite de email do locatário de destino e selecione **o** botão Introdução.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Você foi convidado na caixa de diálogo":::

2. Selecione **Aceitar** para aceitar o convite.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Caixa de diálogo para aceitar permissões":::

   > [!NOTE]
   > Se você não receber esse email ou não conseguir encontrá-lo, o administrador do locatário de destino recebeu uma URL direta que pode ser dada a você para aceitar o convite. A URL deve estar na transcrição da sessão do PowerShell Remoto do administrador do locatário de destino.

3. No centro de administração do Microsoft 365 ou em uma sessão do PowerShell Remoto, crie um ou mais grupos de segurança habilitados para email para controlar a lista de caixas de correio permitidas pelo locatário de destino para puxar (mover) do locatário de origem para o locatário de destino. Você não precisa preencher esse grupo com antecedência, mas pelo menos um grupo deve ser fornecido para executar as etapas de instalação (script). Não há suporte para grupos de aninhar. 

4. Baixe o SetupCrossTenantRelationshipForResourceTenant.ps1 para a configuração do locatário de origem no repositório GitHub aqui: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Crie uma conexão do PowerShell remota com o locatário de origem com suas Exchange de administrador. As permissões de Administrador Global não são necessárias para configurar o locatário de origem, apenas o locatário de destino devido ao processo de criação de aplicativos do Azure.

6. Altere o diretório para o local do script ou verifique se o script está atualmente salvo no local em sua sessão do PowerShell Remoto.

7. Execute o script com os seguintes parâmetros e valores necessários.

    | Parâmetro | Valor |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Grupo de segurança habilitado para email criado pelo locatário de origem para as identidades/caixas de correio que estão no escopo da migração. |
    | -ResourceTenantDomain | Nome de domínio de locatário de origem, como contoso \. onmicrosoft.com. |
    | -ApplicationId | ID do aplicativo do Azure (GUID) do aplicativo usado para migração. ID do aplicativo disponível por meio do portal do Azure (Azure AD, Enterprise Aplicativos, nome do aplicativo, ID do aplicativo) ou incluído no email do convite.  |
    | -TargetTenantDomain | Nome de domínio de locatário de destino, como fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | ID de locatário do locatário de destino. Por exemplo, a ID de locatário do Azure AD da contoso \. onmicrosoft.com locatário. |
    |||

    Veja um exemplo.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

A configuração do administrador de origem agora está concluída!

### <a name="verify-setup"></a>Verificar a instalação

Verifique se as relações da organização nos locatários de origem e de destino e no ponto de extremidade de migração no destino foram criadas com êxito.

#### <a name="target-tenant"></a>Locatário de destino

**Relação de organização**

Verifique se o objeto de relação da organização foi criado e configurado com esse comando.

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

Verifique se o objeto de ponto de extremidade de migração foi criado e configurado com esse comando.

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

**Relação de organização**

Verifique se o objeto de relação da organização foi criado e configurado com esse comando.

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

#### <a name="verify-setup-script"></a>Verificar Script de Instalação

Se você receber erros durante a configuração dos locatários de origem ou [](https://github.com/microsoft/cross-tenant/releases/tag/Preview) de destino, poderá executar o script VerifySetup.ps1 localizado no GitHub e revisar a saída.

Veja um exemplo de execução de VerifySetup.ps1 no locatário de destino:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Veja um exemplo de VerifySetup.ps1 no locatário de origem:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Mover caixas de correio de volta para a fonte original

Se uma caixa de correio voltar para o locatário de origem original for necessária, o mesmo conjunto de etapas e scripts precisará ser executado nos novos locatários de origem e de destino. O objeto Organization Relationship existente será atualizado ou anexado, não recriado.

## <a name="prepare-target-user-objects-for-migration"></a>Preparar objetos de usuário de destino para migração

Os usuários que migram devem estar presentes no locatário de destino e no sistema Exchange Online (como MailUsers) marcado com atributos específicos para habilitar as movimentações entre locatários. O sistema falhará em movimentações para usuários que não estão corretamente definidos no locatário de destino. A seção a seguir detalha os requisitos de objeto MailUser para o locatário de destino.

### <a name="prerequisites"></a>Pré-requisitos
  
Você deve garantir que os seguintes objetos e atributos sejam definidos na organização de destino.  

1. Para qualquer caixa de correio que se move de uma organização de origem, você deve provisionar um objeto MailUser na organização De destino: 

   - O MailUser de destino deve ter esses atributos da caixa de correio de origem ou atribuídos ao novo objeto User:
      - ExchangeGUID (fluxo direto de origem para destino) – O GUID da caixa de correio deve corresponder. O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino. 
      - ArchiveGUID (fluxo direto de origem para destino) – O GUID de arquivo morto deve corresponder. O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino. (Isso só será necessário se a caixa de correio de origem estiver habilitada para Arquivamento). 
      - LegacyExchangeDN (fluxo como proxyAddress, "x500: ") – O LegacyExchangeDN deve estar presente no MailUser de destino <LegacyExchangeDN> como x500: proxyAddress. Os processos de movimentação não continuarão se isso não estiver presente no objeto de destino. 
      - UserPrincipalName – o UPN se alinhará à nova identidade ou à empresa de destino do usuário (por exemplo, user@northwindtraders.onmicrosoft.com). 
      - SMTPAddress principal – O endereço SMTP principal se alinhará à nova empresa do usuário (por exemplo, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser fará referência à caixa de correio atual do usuário hospedada no locatário de origem (por exemplo, user@contoso.onmicrosoft.com). Ao atribuir esse valor, verifique se você também está atribuindo PrimarySMTPAddress ou esse valor definirá PrimarySMTPAddress que causará falhas de movimentação. 
      - Não é possível adicionar endereços proxy smtp herdado da caixa de correio de origem para direcionar MailUser. Por exemplo, você não pode manter contoso.com no MEU em objetos fabrikam.onmicrosoft.com locatários). Os domínios são associados a um locatário do Azure AD ou Exchange Online locatário.
 
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
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Grupo Administrativo                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EndereçosEmail        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Exemplo do objeto Mailbox de **origem:**

     | Atributo             | Valor                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Grupo Administrativo                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EndereçosEmail        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Atributos adicionais podem ser incluídos Exchange gravação híbrida já. Caso não seja, eles devem ser incluídos. 
   - msExchBlockedSendersHash – Grava novamente dados de remetentes seguros e bloqueados dos clientes no Active Directory local.
   - msExchSafeRecipientsHash – Grava novamente dados de remetentes seguros e bloqueados dos clientes no Active Directory local.
   - msExchSafeSendersHash – Grava novamente dados de remetentes seguros e bloqueados dos clientes no Active Directory local.

2. Se a caixa de correio de origem estiver em LitigationHold e o tamanho de Itens Recuperáveis da caixa de correio de origem for maior do que o padrão do banco de dados (30 GB), as movimentações não continuarão, pois a cota de destino é menor que o tamanho da caixa de correio de origem. Você pode atualizar o objeto MailUser de destino para fazer a transição dos sinalizadores de caixa de correio ELC do ambiente de origem para o destino, o que dispara o sistema de destino para expandir a cota do MailUser para 100 GB, permitindo assim a movimentação para o destino. Essas instruções funcionarão apenas para a identidade híbrida que executa o Azure AD Conexão, pois os comandos para carimbar os sinalizadores ELC não são expostos aos administradores de locatários.

    >[!Note]
    > EXEMPLO – COMO ESTÁ, SEM GARANTIA<br/>Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o Active Directory local de destino (para carimbar o objeto ADUser). Se a fonte tiver litígio ou recuperação de item único habilitada, de definir isso na conta de destino.  Isso aumentará o tamanho da lixeira da conta de destino para 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Os locatários de destino não híbridos podem modificar a cota na pasta Itens Recuperáveis para os MailUsers antes da migração executando o seguinte comando para habilitar a Responsabilidade de Litígio no objeto MailUser e aumentando a cota para 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Observe que isso não funcionará para locatários híbridos.

4. Os usuários na organização de destino devem ser licenciados com Exchange Online assinaturas apropriadas aplicáveis à organização. Você pode aplicar uma licença antes de uma movimentação de caixa de correio, mas SOMENTE depois que o MailUser de destino for corretamente definido com o ExchangeGUID e endereços proxy. Aplicar uma licença antes da aplicação do ExchangeGUID resultará em uma nova caixa de correio provisionada na organização de destino. 

    > [!Note]
    > Quando você aplica uma licença a um objeto Mailbox ou MailUser, todos os proxy de tipo SMTPAddresses são limpos para garantir que apenas domínios verificados sejam incluídos na matriz Exchange EmailAddresses. 

5. Você deve garantir que o MailUser de destino não tenha nenhum ExchangeGuid anterior que não corresponder ao ExchangeGuid de origem. Isso pode ocorrer se o MEU de destino tiver sido licenciado anteriormente para Exchange Online e provisionado uma caixa de correio. Se o MailUser de destino tiver sido licenciado anteriormente ou tiver um ExchangeGuid que não corresponder ao ExchangeGuid de origem, você precisará executar uma limpeza da nuvem MEU. Para essas MEUs de nuvem, você pode executar `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .  

    > [!Caution]
    > Esse processo é irreversível. Se o objeto tiver uma caixa de correio softDeleted, ele não poderá ser restaurado após esse ponto. Uma vez limpo, no entanto, você pode sincronizar o ExchangeGuid correto com o objeto de destino e o MRS conectará a caixa de correio de origem à caixa de correio de destino recém-criada. (Referência do blog EHLO no novo parâmetro.)  

    Encontre objetos que eram caixas de correio anteriores usando esse comando.

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

As migrações de Exchange de caixa de correio entre locatários são enviadas como lotes de migração iniciados do locatário de destino. Isso é semelhante à maneira como os lotes de migração ao abordar funcionam ao migrar do Exchange local para o Microsoft 365. 

### <a name="create-migration-batches"></a>Criar lotes de migração

Aqui está um exemplo de cmdlet em lotes de migração para início de movimentações.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> O endereço de email no arquivo CSV deve ser o especificado no locatário de destino, não o locatário de origem.

O envio em lote de migração também tem suporte do novo Exchange Admin Center ao selecionar a opção entre locatários.

#### <a name="update-on-premises-mailusers"></a>Atualizar MailUsers local

Depois que a caixa de correio mudar de origem para destino, você deve garantir que os usuários de email locais, origem e o destino, sejam atualizados com o novo targetAddress. Nos exemplos, o targetDeliveryDomain usado na movimentação é **contoso.onmicrosoft.com**. Atualize os usuários de email com esse targetAddress.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Precisamos atualizar RemoteMailboxes na origem local após a movimentação?**

Sim, você deve atualizar o targetAddress (RemoteRoutingAddress/ExternalEmailAddress) dos usuários locais de origem quando a caixa de correio de locatário de origem for migrada para o locatário de destino.  Embora o roteamento de email possa seguir as indicações entre vários usuários de email com destinos diferentesAddresses, as buscas de usuários de email devem direcionar o local do usuário da caixa de correio. As buscas de livre/ocupado não perseguirão vários redirecionamentos. 

**As Teams migram entre locatários?**  

As reuniões mudarão no entanto, Teams URL da reunião não será atualizada quando os itens migrarem entre locatários. Como a URL será inválida no locatário de destino, você precisará remover e recriar as reuniões Teams de destino.

**O conteúdo Teams de pasta de chat migra entre locatários?**  

Não, o Teams de pasta de chat não migra entre locatários.  

**Como posso ver apenas movimentações que são movimentações entre locatários, não minhas movimentações de integração e de off-boarding?**

Use o `-flags` parâmetro. Veja um exemplo.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Você pode fornecer scripts de exemplo para copiar atributos usados no teste?**

> [!Note]
> EXEMPLO – COMO ESTÁ, SEM GARANTIA<br/>Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o destino dos Serviços de Domínio do Active Directory local (para carimbar o objeto ADUser). Se a fonte tiver litígio ou recuperação de item único habilitada, de definir isso na conta de destino.  Isso aumentará o tamanho da lixeira da conta de destino para 100 GB.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit" 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects 
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**Como acessamos o Outlook dia 1 após a movimentação da caixa de correio de uso?**

Como apenas um locatário pode possuir um domínio, o SMTPAddress principal anterior não será associado ao usuário no locatário de destino quando a movimentação da caixa de correio for concluída; somente os domínios associados ao novo locatário. Outlook usa o novo UPN dos usuários para autenticar o serviço e o perfil Outlook espera encontrar o SMTPAddress principal herdado para corresponder à caixa de correio no sistema de destino. Como o endereço herdado não está no destino O perfil do outlook não se conectará para encontrar a caixa de correio movida recentemente. 

Para essa implantação inicial, os usuários precisarão recriar seu perfil com seu novo UPN, endereço SMTP principal e ressincronize o conteúdo OST. 

> [!Note]
> Planeje de acordo à medida que você lote seus usuários para conclusão. Você precisa levar em conta a utilização e a capacidade da rede quando Outlook perfis de cliente são criados e os arquivos OST e OAB subsequentes são baixados para clientes. 
 
**De Exchange funções RBAC de que preciso ser membro para configurar ou concluir uma movimentação entre locatários?**
 
Há uma matriz de funções com base na suposição de funções delegadas ao executar uma movimentação de caixa de correio. Atualmente, duas funções são necessárias:  

- A primeira função é para uma tarefa de instalação única que estabelece a autorização de mover o conteúdo para ou para fora do limite de locatário/organizacional. Como a movimentação de dados do controle organizacional é uma preocupação crítica para todas as empresas, optamos pela função mais alta atribuída do Administrador da Organização (OrgAdmin). Essa função deve alterar ou configurar um novo OrganizationRelationship que define o -MailboxMoveCapability com a organização remota. Somente o OrgAdmin pode alterar a configuração MailboxMoveCapability, enquanto outros atributos no OrganizationRelationhip podem ser gerenciados pelo administrador de Compartilhamento Federado. 
 
- A função de executar os comandos de movimentação real pode ser delegada a uma função de nível inferior. A função de Mover Caixas de Correio recebe a capacidade de mover caixas de correio para dentro ou para fora da organização usando o `-RemoteTenant` parâmetro.  

**Como direcionar qual endereço SMTP está selecionado para targetAddress (TargetDeliveryDomain) na caixa de correio convertida (para conversão mailUser)?**
 
Exchange de caixa de correio usando MRS crie o targetAddress na caixa de correio de origem original ao converter em um MailUser correspondendo a um endereço de email (proxyAddress) no objeto de destino. O processo pega o valor -TargetDeliveryDomain passado para o comando de movimentação e verifica se há um proxy correspondente para esse domínio no lado de destino. Quando encontramos uma correspondência, o proxy correspondenteAddress é usado para definir ExternalEmailAddress (targetAddress) no objeto de caixa de correio convertida (agora MailUser).
 
**Como fazer a transição de permissões de caixa de correio?**

As permissões de caixa de correio incluem Send on Behalf of e Mailbox Access: 

- Send On Behalf Of (AD:publicDelegates) armazena a DN de destinatários com acesso à caixa de correio de um usuário como representante. Esse valor é armazenado no Active Directory e atualmente não se move como parte da transição de caixa de correio. Se a caixa de correio de origem tiver publicDelegates definida, você precisará manter o publicDelegates na Caixa de Correio de destino assim que a conversão MEU para Caixa de Correio for concluída no ambiente de destino executando `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- As permissões de caixa de correio armazenadas na caixa de correio serão movidas com a caixa de correio quando a entidade e o representante são movidos para o sistema de destino. Por exemplo, o usuário TestUser_7 é concedido FullAccess à caixa de correio TestUser_8 no locatário SourceCompany.onmicrosoft.com. Depois que a movimentação de caixa de correio é concluída TargetCompany.onmicrosoft.com, as mesmas permissões são configuradas no diretório de destino. Exemplos usando *Get-MailboxPermission* para TestUser_7 locatários de origem e destino são mostrados abaixo. Exchange cmdlets são prefixados com origem e destino de acordo. 
 
Aqui está um exemplo da saída da permissão de caixa de correio antes de uma movimentação. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Aqui está um exemplo da saída da permissão de caixa de correio após a movimentação. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> As permissões de caixa de correio e calendário entre locatários NÃO são suportadas. Você deve organizar entidades e representantes em lotes de movimentação consolidados para que essas caixas de correio conectadas sejam transidas ao mesmo tempo do locatário de origem. 

**Qual proxy X500 deve ser adicionado aos endereços proxy mailUser de destino para habilitar a migração?**  

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

**Onde começar a solucionar problemas se as movimentações não funcionarem?**  

Comece executando o script VerifySetup.ps1 localizado [no](https://github.com/microsoft/cross-tenant/releases/tag/Preview) GitHub e revise a saída.

Veja um exemplo de execução de VerifySetup.ps1 no locatário de destino:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Aqui está um eExample de execução de VerifySetup.ps1 no locatário de origem:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**O locatário de origem e destino pode usar o mesmo nome de domínio?**  

Não. Os nomes de domínio de locatário de origem e destino devem ser exclusivos. Por exemplo, um domínio de origem de contoso.com e o domínio de destino de fourthcoffee.com.

**As caixas de correio compartilhadas serão movimentadas e ainda funcionarão?**

Sim, no entanto, só manteremos as permissões da loja conforme descrito nestes artigos:

- [Microsoft Docs | Gerenciar permissões para destinatários no Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Suporte da Microsoft | Como conceder Exchange e Outlook de caixa de correio em um Office 365 dedicado](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**O Azure Key Vault é necessário e quando as transações são feitas?**  

Sim, uma assinatura do Azure é necessária para usar o Key Vault para armazenar o certificado para autorizar a migração. Ao contrário das migrações de integração que usam o nome de usuário & senha para autenticar na origem, as migrações de caixa de correio entre locatários usam o OAuth e esse certificado como segredo/credencial. O acesso ao Cofre de Chaves deve ser mantido em todas as migrações de caixa de correio, pois ele é acessado uma vez no início e depois do fim da migração, bem como uma vez a cada 24 horas durante os tempos de sincronização incrementais. Você pode revisar os detalhes de custo do AKV [aqui]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).  

**Você tem alguma recomendação para lotes?**  

Não exceda 2.000 caixas de correio por lote. Recomendamos o envio de lotes duas semanas antes da data de recortamento, pois não há impacto para os usuários finais durante a sincronização. Se você precisar de orientações para quantidades de caixas de correio com mais de 50.000, você poderá falar com a Lista de Distribuição de Feedback de Engenharia no crosstenantmigrationpreview@service.microsoft.com.

**E se eu usar a criptografia de serviço com a Chave do Cliente?**

A caixa de correio será descriptografada antes de se mover. Verifique se a Chave do Cliente está configurada no locatário de destino, se ela ainda for necessária. Consulte [aqui](../compliance/customer-key-overview.md) para obter mais informações.  

**Qual é o tempo estimado de migração?**

Para ajudá-lo a planejar [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) sua migração, a tabela presente aqui mostra as diretrizes sobre quando esperar que as migrações de caixa de correio em massa ou migrações individuais seja concluídas. Essas estimativas se baseiam em uma análise de dados de migrações anteriores do cliente. Como cada ambiente é exclusivo, a velocidade exata de migração pode variar.  

Lembre-se de que esse recurso está atualmente em visualização e o SLA e quaisquer Níveis de Serviço aplicáveis não se aplicam a qualquer problema de desempenho ou disponibilidade durante o status de visualização desse recurso.

## <a name="known-issues"></a>Problemas conhecidos  

-  **Problema: arquivos expandidos automaticamente não podem ser migrados.** O recurso de migração entre locatários suporta migrações da caixa de correio principal e da caixa de correio de arquivo morto para um usuário específico. Se o usuário na origem, no entanto, tiver um arquivo morto expandido automaticamente – ou seja, mais de uma caixa de correio de arquivo morto, o recurso não poderá migrar os arquivos adicionais e deverá falhar.

- **Problema: Cloud MailUsers with non-owned smtp proxyAddress block MRS move background.** Ao criar objetos MailUser de locatário de destino, você deve garantir que todos os endereços proxy SMTP pertencem à organização do locatário de destino. Se houver um proxy SMTPAddress no usuário de email de destino que não pertença ao locatário local, a conversão do MailUser para a Caixa de Correio será impedida. Isso ocorre devido à nossa garantia de que os objetos de caixa de correio só podem enviar emails de domínios para os quais o locatário é autoritativo (domínios reivindicados pelo locatário): 

   - Quando você sincroniza usuários do local usando o Azure AD Conexão, provisiona objetos MailUser locais com ExternalEmailAddress apontando para o locatário de origem onde a caixa de correio existe (laran@contoso.onmicrosoft.com) e você carimba o PrimarySMTPAddress como um domínio que reside no locatário de destino (Lara.Newton@northwind.com). Esses valores são sincronizados com o locatário e um usuário de email apropriado está provisionado e pronto para migração. Um objeto example é mostrado aqui.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > O *contoso.onmicrosoft.com* endereço não *está* presente na matriz EmailAddresses/proxyAddresses.

- **Problema: objetos MailUser com endereços SMTP "externos" primários são modificados/redefinidos para domínios "internos" reivindicados pela empresa**

   Objetos MailUser são ponteiros para caixas de correio não locais. No caso de migrações de caixa de correio entre locatários, usamos objetos MailUser para representar a caixa de correio de origem (da perspectiva da organização de destino) ou a caixa de correio de destino (da perspectiva da organização de origem). Os MailUsers terão um ExternalEmailAddress (targetAddress) que aponta para o endereço smtp da caixa de correio real (ProxyTest@fabrikam.onmicrosoft.com) e o endereço primarySMTP que representa o endereço SMTP exibido do usuário de caixa de correio no diretório. Algumas organizações optam por exibir o endereço SMTP principal como um endereço SMTP externo, não como um endereço de propriedade/verificado pelo locatário local (como fabrikam.com em vez de contoso.com).  No entanto, uma vez que um objeto de plano de serviço Exchange é aplicado ao MailUser por meio de operações de licenciamento, o endereço SMTP principal é modificado para mostrar como um domínio verificado pela organização local (contoso.com). Há dois motivos potenciais:
   
   - Quando qualquer Exchange de serviço é aplicado a um MailUser, o processo do Azure AD começa a impor a limpeza de proxy para garantir que a organização local não seja capaz de enviar emails, spoof ou emails de outro locatário. Qualquer endereço SMTP em um objeto de destinatário com esses planos de serviço será removido se o endereço não for verificado pela organização local. Como é o caso no exemplo, o domínio Fabikam.com não é verificado pelo locatário contoso.onmicrosoft.com, portanto, a limpeza remove esse fabrikam.com domínio. Se desejar persistir esses domínios externos no MailUser, antes da migração ou após a migração, você precisará alterar seus processos de migração para retirar licenças após a conclusão da movimentação ou antes da movimentação para garantir que os usuários tenham a identidade visual externa esperada aplicada. Você precisará garantir que o objeto de caixa de correio seja licenciado corretamente para não afetar o serviço de email.<br/><br/>Um script de exemplo para remover os planos de serviço em um MailUser no Contoso.onmicrosoft.com locatário é mostrado aqui.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Os resultados do conjunto de ServicePlans atribuídos são mostrados aqui.

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
 
       O PrimarySMTPAddress do usuário não está mais limpo. O fabrikam.com domínio não pertence ao locatário contoso.onmicrosoft.com e persistirá como o endereço SMTP principal mostrado no diretório.

       Veja um exemplo.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Quando msExchRemoteRecipientType for definido como 8 (DeprovisionMailbox), para MailUsers locais que são migrados para o locatário de destino, a lógica de limpeza de proxy no Azure removerá domínios não proprietários e redefinirá o primarySMTP para um domínio de propriedade. Ao limpar msExchRemoteRecipientType no MailUser local, a lógica de limpeza de proxy não se aplica mais. <br/><br>Abaixo está o conjunto completo de possíveis Planos de Serviço que incluem Exchange Online.

   | Nome                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Armazenamento (500 GB)               |
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
   | Exchange Online Complemento do usuário inativo              |
   | Quiosque do Exchange Online                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Plano 1                            |
   | POP do Exchange Online                               |
   | Proteção do Exchange Online                        |
   | Barreiras de informações                              |
   | Proteção de Informações para o Office 365 – Premium   |
   | Proteção de informações para o Office 365 – Padrão  |
   | Insights by MyAnalytics                           |
   | Microsoft 365 Auditoria Avançada                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Completo)                      |
   | Descoberta Eletrônica Avançada do Office 365                    |
   | Microsoft Defender para Office 365 (Plano 1)    |
   | Microsoft Defender para Office 365 (Plano 2)    |
   | Privileged Access Management para Office 365           |
   | Premium Criptografia no Office 365                  |
