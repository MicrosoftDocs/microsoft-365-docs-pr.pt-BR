---
title: Gerenciar Chave do Cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Depois de configurar a Chave do Cliente, saiba como gerenciá-la restaurando chaves AKV e gerenciando permissões e criando e atribuindo políticas de criptografia de dados.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345053"
---
# <a name="manage-customer-key"></a>Gerenciar Chave do Cliente

Depois de configurar a Chave do Cliente para Office 365, você precisará criar e atribuir uma ou mais políticas de criptografia de dados (DEP). Depois de ter atribuído seus DEPs, você pode gerenciar suas chaves conforme descrito neste artigo. Saiba mais sobre a Chave do Cliente nos tópicos relacionados.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Criar um DEP para uso com várias cargas de trabalho para todos os usuários de locatários

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Cliente. Para obter informações, [consulte Set up Customer Key](customer-key-set-up.md). Para criar o DEP, você precisa das URIs do Cofre de Chaves obtidas durante a instalação. Para obter informações, [consulte Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

Para criar uma DEP de várias cargas de trabalho, siga estas etapas:
  
1. Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.

2. Para criar um DEP, use o New-M365DataAtRestEncryptionPolicy cmdlet.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Onde:

   - *PolicyName* é o nome que você deseja usar para a política. Os nomes não podem conter espaços. Por exemplo, Contoso_Global.

   - *KeyVaultURI1* é o URI da primeira chave da política. Por exemplo, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* é o URI da segunda chave da política. Por exemplo, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Separe as duas URIs por uma vírgula e um espaço.

   - *Descrição da* política é uma descrição amigável da política que ajudará você a lembrar para que a política é. Você pode incluir espaços na descrição. Por exemplo, "Política raiz para várias cargas de trabalho para todos os usuários no locatário.".

Exemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Atribuir política de várias cargas de trabalho

Atribua o DEP usando o Set-M365DataAtRestEncryptionPolicyAssignment cmdlet. Depois de atribuir a política, Microsoft 365 criptografa os dados com a chave identificada no DEP.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Onde *PolicyName* é o nome da política. Por exemplo, Contoso_Global.

Exemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Criar um DEP para uso com Exchange Online caixas de correio

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault. Para obter informações, [consulte Set up Customer Key](customer-key-set-up.md). Você concluirá essas etapas conectando-se remotamente ao Exchange Online com Windows PowerShell.

Um DEP é associado a um conjunto de chaves armazenadas no Azure Key Vault. Você atribui um DEP a uma caixa de correio em Microsoft 365. Microsoft 365 usar as chaves identificadas na política para criptografar a caixa de correio. Para criar o DEP, você precisa das URIs do Cofre de Chaves obtidas durante a instalação. Para obter informações, [consulte Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

Lembre-se! Quando você cria um DEP, especifica duas chaves em dois cofres de chave do Azure diferentes. Crie essas chaves em duas regiões separadas do Azure para garantir a redundância geográfica.

Para criar um DEP a ser usado com uma caixa de correio, siga estas etapas:
  
1. No computador local, usando uma conta de estudante ou de trabalho que tenha permissões de administrador global ou Exchange Online de administrador em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell.

2. Para criar um DEP, use o cmdlet New-DataEncryptionPolicy digitando o comando a seguir.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Onde:

   - *PolicyName* é o nome que você deseja usar para a política. Os nomes não podem conter espaços. Por exemplo, USA_mailboxes.

   - *Descrição da* política é uma descrição amigável da política que ajudará você a lembrar para que a política é. Você pode incluir espaços na descrição. Por exemplo, "Chave raiz para caixas de correio nos EUA e seus territórios".

   - *KeyVaultURI1* é o URI da primeira chave da política. Por exemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* é o URI da segunda chave da política. Por exemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separe as duas URIs por uma vírgula e um espaço.

   Exemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Atribuir um DEP a uma caixa de correio

Atribua o DEP a uma caixa de correio usando Set-Mailbox cmdlet. Depois de atribuir a política, Microsoft 365 criptografar a caixa de correio com a chave identificada no DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailboxIdParameter* especifica uma caixa de correio de usuário. Para obter mais informações sobre o Set-Mailbox cmdlet, consulte [Set-Mailbox](/powershell/module/exchange/set-mailbox).

Em ambientes híbridos, você pode atribuir um DEP aos dados de caixa de correio locais que são sincronizados no seu locatário Exchange Online local. Para atribuir um DEP a esses dados de caixa de correio sincronizados, você usará o cmdlet Set-MailUser usuário. Para obter mais informações sobre dados de caixa de correio no ambiente híbrido, consulte caixas de correio locais usando Outlook para iOS e Android com [autenticação moderna híbrida.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailUserIdParameter* especifica um usuário de email (também conhecido como um usuário habilitado para email). Para obter mais informações sobre o Set-MailUser cmdlet, consulte [Set-MailUser](/powershell/module/exchange/set-mailuser).

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Criar um DEP para uso com SharePoint online, OneDrive for Business e Teams arquivos

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault. Para obter informações, [consulte Set up Customer Key](customer-key-set-up.md).
  
Para configurar a Chave do Cliente para arquivos SharePoint Online, OneDrive for Business e Teams você conclui essas etapas conectando-se remotamente ao SharePoint Online com Windows PowerShell.
  
Você associa um DEP a um conjunto de chaves armazenadas no Azure Key Vault. Você aplica uma DEP a todos os seus dados em uma localização geográfica, também chamada de geo. Se você usar o recurso multi-geo da Office 365, poderá criar um DEP por geo com a capacidade de usar chaves diferentes por geo. Se você não estiver usando multi-geo, poderá criar um DEP em sua organização para uso com arquivos SharePoint Online, OneDrive for Business e Teams. Microsoft 365 usa as chaves identificadas no DEP para criptografar seus dados nesse geo. Para criar o DEP, você precisa das URIs do Cofre de Chaves obtidas durante a instalação. Para obter informações, [consulte Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).
  
Lembre-se! Quando você cria um DEP, especifica duas chaves em dois cofres de chave do Azure diferentes. Crie essas chaves em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar uma DEP, você precisa se conectar remotamente ao SharePoint Online usando Windows PowerShell.
  
1. No computador local, usando uma conta de trabalho ou de estudante que tenha permissões globais de administrador em sua organização, Conexão [para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)

2. No Shell Microsoft Office SharePoint Online Gerenciamento, execute o cmdlet Register-SPODataEncryptionPolicy da seguinte forma:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Exemplo:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Quando você registra o DEP, a criptografia começa nos dados no geo. A criptografia pode levar algum tempo. Para obter mais informações sobre como usar esse parâmetro, consulte [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Exibir os DEPs que você criou para Exchange Online caixas de correio

Para exibir uma lista de todos os DEPs que você criou para caixas de correio, use o cmdlet Get-DataEncryptionPolicy PowerShell.

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Para retornar todos os DEPs da sua organização, execute o cmdlet Get-DataEncryptionPolicy sem parâmetros.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obter mais informações sobre o Get-DataEncryptionPolicy cmdlet, consulte [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Atribuir um DEP antes de migrar uma caixa de correio para a nuvem

Quando você atribui o DEP, Microsoft 365 criptografa o conteúdo da caixa de correio usando o DEP atribuído durante a migração. Esse processo é mais eficiente do que migrar a caixa de correio, atribuir o DEP e esperar que a criptografia seja realizada, o que pode levar horas ou possivelmente dias.

Para atribuir um DEP a uma caixa de correio antes de migrar para Office 365, execute o cmdlet Set-MailUser no Exchange Online PowerShell:

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio, e *DataEncryptionPolicyIdParameter* é a ID do DEP. Para obter mais informações sobre o Set-MailUser cmdlet, consulte [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar o DEP atribuído a uma caixa de correio

Para determinar o DEP atribuído a uma caixa de correio, use Get-MailboxStatistics cmdlet. O cmdlet retorna um identificador exclusivo (GUID).
  
1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e DataEncryptionPolicyID retorna o GUID do DEP. Para obter mais informações sobre o Get-MailboxStatistics cmdlet, consulte [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).
  
2. Execute o Get-DataEncryptionPolicy cmdlet para descobrir o nome amigável do DEP ao qual a caixa de correio é atribuída.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Onde *GUID* é o GUID retornado pelo cmdlet Get-MailboxStatistics na etapa anterior.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Verificar se a Chave do Cliente terminou a criptografia

Se você tenha rolado uma Chave do Cliente, atribuído um novo DEP ou migrado uma caixa de correio, use as etapas nesta seção para garantir que a criptografia seja concluída.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Verificar se a criptografia é concluída para Exchange Online caixas de correio

Criptografar uma caixa de correio pode levar algum tempo. Pela primeira vez, a caixa de correio também deve mudar completamente de um banco de dados para outro para que o serviço possa criptografar a caixa de correio.
  
Use o cmdlet Get-MailboxStatistics para determinar se uma caixa de correio está criptografada.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

A propriedade IsEncrypted retorna  um valor true se a caixa de correio for criptografada e um valor de **false** se a caixa de correio não estiver criptografada. O tempo para concluir as movimentações de caixa de correio depende do número de caixas de correio às quais você atribui um DEP pela primeira vez e do tamanho das caixas de correio. Se as caixas de correio não foram criptografadas após uma semana a partir do momento em que você atribuiu o DEP, contate a Microsoft.

O New-MoveRequest cmdlet não está mais disponível para movimentações de caixa de correio local. Consulte este [comunicado para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obter informações adicionais.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verificar se a criptografia é concluída SharePoint arquivos online, OneDrive for Business e Teams online

Verifique o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy da seguinte forma:

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

A saída deste cmdlet inclui:
  
- O URI da chave primária.

- O URI da chave secundária.

- O status de criptografia do geo. Os estados possíveis incluem:

  - **Não-registro:** A criptografia chave do cliente ainda não foi aplicada.

  - **Registrando:** A criptografia chave do cliente foi aplicada e seus arquivos estão sendo criptografados. Se a chave do geo estiver registrando, você também será mostrado informações sobre qual porcentagem de sites no geo está concluída para que você possa monitorar o progresso da criptografia.

  - **Registrado:** A criptografia chave do cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.

  - **Rolling:** Um rol de teclas está em andamento. Se a chave do geo estiver rolando, você também será mostrado informações sobre qual porcentagem de sites concluiu a operação de rolagem de chaves para que você possa monitorar o progresso.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Obter detalhes sobre DEPs que você usa com várias cargas de trabalho

Para obter detalhes sobre todos os DEPs que você criou para usar com várias cargas de trabalho, conclua estas etapas:

1. Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.

   - Para retornar a lista de todos os DEPs de várias cargas de trabalho na organização, execute este comando.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Para retornar detalhes sobre um DEP específico, execute este comando. Este exemplo retorna informações detalhadas para a DEP chamada "Contoso_Global".

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Obter informações de atribuição de DEP de várias cargas de trabalho

Para descobrir qual DEP está atualmente atribuído ao seu locatário, siga estas etapas. 

1. Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.

2. Digite este comando.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Desabilitar uma DEP de várias cargas de trabalho

Antes de desabilitar uma DEP de várias cargas de trabalho, desaprompa o DEP de cargas de trabalho em seu locatário. Para desabilitar um DEP usado com várias cargas de trabalho, conclua estas etapas:

1. Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.

2. Execute o cmdlet Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Onde *PolicyName* é o nome ou ID exclusiva da política. Por exemplo, Contoso_Global.

Exemplo:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Restaurar chaves do Cofre de Chaves do Azure

Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão suave. Todas as chaves usadas com a Chave do Cliente são necessárias para habilitar a exclusão suave. A exclusão suave age como uma lixeira e permite a recuperação por até 90 dias sem a necessidade de restauração. A restauração só deve ser necessária em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido. Se você deve restaurar uma chave para uso com a Chave do Cliente, em Azure PowerShell, execute o cmdlet Restore-AzureKeyVaultKey da seguinte forma:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Por exemplo:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se o cofre de chaves já contiver uma chave com o mesmo nome, a operação de restauração falhará. Restore-AzKeyVaultKey restaura todas as versões principais e todos os metadados da chave, incluindo o nome da chave.
  
## <a name="manage-key-vault-permissions"></a>Gerenciar permissões de cofre de chaves

Vários cmdlets estão disponíveis que permitem que você veja e, se necessário, remova as permissões do cofre de chaves. Talvez seja necessário remover permissões, por exemplo, quando um funcionário sair da equipe. Para cada uma dessas tarefas, você usará Azure PowerShell. Para obter informações sobre Azure PowerShell, consulte [Overview of Azure PowerShell](/powershell/azure/).

Para exibir permissões de cofre de chaves, execute o cmdlet Get-AzKeyVault chave.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Por exemplo:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Para remover as permissões de um administrador, execute o cmdlet Remove-AzKeyVaultAccessPolicy:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Por exemplo:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Reverter da Chave do Cliente para chaves gerenciadas da Microsoft

Se precisar reverter para chaves gerenciadas pela Microsoft, você pode. Quando você sai do barco, seus dados são recriptados usando a criptografia padrão suportada por cada carga de trabalho individual. Por exemplo, Exchange Online dá suporte à criptografia padrão usando chaves gerenciadas pela Microsoft.

> [!IMPORTANT]
> O offboard não é o mesmo que uma limpeza de dados. Uma limpeza de dados exclui permanentemente os dados da sua organização Microsoft 365, o offboard não. Você não pode executar uma limpeza de dados para uma política de carga de trabalho múltipla.

Se você decidir não usar Mais a Chave do Cliente para atribuir DEPs de várias cargas de trabalho, você precisará falar com o suporte da Microsoft com uma solicitação para "offboard" da Chave do Cliente. Peça à equipe de suporte para arquivar uma solicitação de serviço Microsoft 365 equipe de Chave do Cliente. Entre em contato m365-ck@service.microsoft.com se você tiver alguma dúvida.

Se você não quiser mais criptografar caixas de correio individuais usando DEPs de nível de caixa de correio, poderá desasinhar DEPs de nível de caixa de correio de todas as suas caixas de correio.

Para desausinar DEPs de caixa de correio, use o cmdlet Set-Mailbox PowerShell.

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

Executar este cmdlet desassocia o DEP atribuído no momento e reenscriptografa a caixa de correio usando o DEP associado às chaves gerenciadas pela Microsoft padrão. Não é possível desa desasinalhar o DEP usado pelas chaves gerenciadas da Microsoft. Se você não quiser usar chaves gerenciadas pela Microsoft, poderá atribuir outro DEP de Chave de Cliente à caixa de correio.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revogar suas chaves e iniciar o processo de caminho de limpeza de dados

Você controla a revogação de todas as chaves raiz, incluindo a chave de disponibilidade. A Chave do Cliente fornece controle do aspecto de planejamento de saída dos requisitos regulatórios para você. Se você decidir revogar suas chaves para limpar seus dados e sair do serviço, o serviço excluirá a chave de disponibilidade depois que o processo de limpeza de dados for concluído. Isso é suportado para DEPs de Chave de Cliente que são atribuídos a caixas de correio individuais.

Microsoft 365 audita e valida o caminho de limpeza de dados. Para obter mais informações, consulte o Relatório soc 2 do SSAE 18 disponível no [Portal de Confiança do Serviço.](https://servicetrust.microsoft.com/) Além disso, a Microsoft recomenda os seguintes documentos:

- [Guia de Avaliação e Conformidade de Riscos para Instituições Financeiras no Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Considerações sobre o planejamento de saída do O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Não há suporte para a depuração de DEP de várias cargas de trabalho Microsoft 365 Customer Key. A DEP de várias cargas de trabalho é usada para criptografar dados em várias cargas de trabalho em todos os usuários de locatários. A purgação desse DEP resultaria em dados de várias cargas de trabalho inacessíveis. Se você decidir sair completamente Microsoft 365 serviços, poderá seguir o caminho da exclusão de locatários por meio do processo documentado. Veja [como excluir um locatário no Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revogar suas Chaves de Cliente e a chave de disponibilidade para Exchange Online e Skype for Business

Ao iniciar o caminho de limpeza de dados para Exchange Online e Skype for Business, você definirá uma solicitação permanente de limpeza de dados em um DEP. Isso exclui permanentemente os dados criptografados nas caixas de correio às quais esse DEP é atribuído.

Como você só pode executar o cmdlet do PowerShell em um DEP por vez, considere reatribuir um único DEP para todas as suas caixas de correio antes de iniciar o caminho de limpeza de dados.

> [!WARNING]
> Não use o caminho de limpeza de dados para excluir um subconjunto de suas caixas de correio. Esse processo destina-se apenas aos clientes que estão saindo do serviço.

Para iniciar o caminho de limpeza de dados, conclua estas etapas:

1. Remova permissões de quebra e desembrulhamento para "O365 Exchange Online" dos Cofres de Chaves do Azure.

2. Usando uma conta de estudante ou de trabalho que tenha privilégios globais de administrador em sua organização, [conecte-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

3. Para cada DEP que contém caixas de correio que você deseja excluir, execute o cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) da seguinte forma.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Se o comando falhar, verifique se você removeu as permissões Exchange Online de ambas as chaves no Azure Key Vault conforme especificado anteriormente nesta tarefa.Depois de definir a opção PermanentDataPurgeRequested usando o cmdlet Set-DataEncryptionPolicy, você não poderá mais atribuir esse DEP às caixas de correio.

4. Entre em contato com o suporte da Microsoft e solicite o eDocument de Limpeza de Dados.

    Em sua solicitação, a Microsoft envia um documento legal para confirmar e autorizar a exclusão de dados. A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento. Normalmente, esse é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.

5. Depois que seu representante tiver assinado o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).

    Depois que a Microsoft recebe o documento legal, a Microsoft executa cmdlets para disparar a limpeza de dados que primeiro exclui a política, marca as caixas de correio para exclusão permanente e exclui a chave de disponibilidade. Depois que o processo de limpeza de dados for concluído, os dados serão limpos, estarão inacessíveis Exchange Online e não serão recuperáveis.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Revogar suas Chaves de Cliente e a chave de disponibilidade para arquivos SharePoint Online, OneDrive for Business e Teams Online

Para iniciar o caminho de limpeza de dados para arquivos SharePoint Online, OneDrive for Business e Teams, conclua estas etapas:

1. Revogar o acesso ao Cofre de Chaves do Azure. Todos os administradores do cofre de chaves devem concordar em revogar o acesso.

   Você não exclui o Azure Key Vault para SharePoint Online. Os cofres chave podem ser compartilhados entre vários locatários SharePoint Online e DEPs.

2. Contate a Microsoft para excluir a chave de disponibilidade.

    Quando você entrar em contato com a Microsoft para excluir a chave de disponibilidade, enviaremos um documento legal. A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento. Normalmente, esse é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.

3. Depois que o representante assinar o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).

   Depois que a Microsoft recebe o documento legal, executamos cmdlets para disparar a limpeza de dados que executa a exclusão criptografada da chave de locatário, da chave do site e de todas as chaves individuais por documento, quebrando irrevogavelmente a hierarquia de chaves. Depois que os cmdlets de limpeza de dados são concluídos, seus dados são limpos.

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Configurar a Chave do Cliente](customer-key-set-up.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Sistema de Proteção de Dados do Cliente](customer-lockbox-requests.md)

- [Criptografia de Serviço](office-365-service-encryption.md)