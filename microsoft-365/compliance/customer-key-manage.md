---
title: Gerenciar chave do cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Depois de configurar a chave do cliente, saiba como gerenciá-la restaurando as chaves do AKV e gerenciando as permissões e as políticas de criptografia de dados.
ms.openlocfilehash: 8f5f23fa1b8ce8baa8fafd3f29ca5fb8905887a1
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324253"
---
# <a name="manage-customer-key"></a>Gerenciar chave do cliente

Depois de configurar a chave do cliente para o Office 365, você pode gerenciar suas chaves, conforme descrito neste artigo. Saiba mais sobre a chave do cliente nos tópicos relacionados.

## <a name="restore-azure-key-vault-keys"></a>Restaurar chaves do Azure Key Vault

Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão reversível. Todas as chaves usadas com a chave do cliente são necessárias para que a exclusão reversível seja habilitada. A exclusão reversível funciona como uma lixeira e permite a recuperação de até 90 dias sem a necessidade de restauração. A restauração deve ser necessária somente em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido. Se for necessário restaurar uma chave para uso com a chave do cliente, no PowerShell do Azure, execute o cmdlet Restore-AzureKeyVaultKey da seguinte maneira:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Por exemplo:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se o cofre de chaves já contiver uma chave com o mesmo nome, a operação de restauração falhará. Restore-AzKeyVaultKey restaura todas as versões de chave e todos os metadados da chave, incluindo o nome da chave.
  
## <a name="manage-key-vault-permissions"></a>Gerenciar permissões do Key Vault

Há vários cmdlets disponíveis que permitem que você visualize e, se necessário, remova as permissões do Key Vault. Talvez seja necessário remover permissões, por exemplo, quando um funcionário sair da equipe. Para cada uma dessas tarefas, você usará o Azure PowerShell. Para obter informações sobre o Azure PowerShell, consulte [visão geral do Azure PowerShell](https://docs.microsoft.com/powershell/azure/).

Para exibir as permissões do compartimento de chaves, execute o cmdlet Get-AzKeyVault.

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

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Gerenciar políticas de criptografia de dados (DEPs) com a chave do cliente

As alças de chave do cliente DEPs de forma diferente entre os diferentes serviços. Por exemplo, você pode criar um número diferente de DEPs para os diferentes serviços.

**Exchange Online e Skype for Business:** Você pode criar até 50 DEPs. Para obter instruções, consulte [criar uma política de criptografia de dados (DEP) para uso com o Exchange Online e o Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**SharePoint Online, onedrive for Business e arquivos do teams:** Uma DEP aplica-se aos dados em um local geográfico, também chamado de uma _geografia_. Se você usar o recurso multigeográfico do Office 365, poderá criar uma DEP por Geo. Se você não estiver usando o multigeográfico, você pode criar um DEP. Normalmente, você cria a DEP ao configurar a chave do cliente. Para obter instruções, consulte [criar uma DEP (política de criptografia de dados) para cada Geografia do SharePoint Online e do onedrive for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Exibir o DEPs que você criou para o Exchange Online e o Skype for Business

Para exibir uma lista de todos os DEPs que você criou para o Exchange Online e o Skype for Business usando o cmdlet Get-DataEncryptionPolicy do PowerShell, conclua estas etapas.

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Para retornar todos os DEPs em sua organização, execute o cmdlet Get-DataEncryptionPolicy sem nenhum parâmetro.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obter mais informações sobre o cmdlet Get-DataEncryptionPolicy, consulte [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Atribuir uma DEP antes de migrar uma caixa de correio para a nuvem

Quando você atribui a DEP, a Microsoft 365 criptografa o conteúdo da caixa de correio usando a DEP atribuída durante a migração. Esse processo é mais eficiente do que migrar a caixa de correio, atribuindo a DEP e, em seguida, aguardando a criptografia ocorrer, o que pode levar horas ou possivelmente dias.

Para atribuir uma DEP a uma caixa de correio antes de migrá-la para o Office 365, execute o cmdlet Set-MailUser no PowerShell do Exchange Online:

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Execute o cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e *DATAENCRYPTIONPOLICYIDPARAMETER* é a ID da DEP. Para obter mais informações sobre o cmdlet Set-MailUser, consulte [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar a DEP atribuída a uma caixa de correio

Para determinar a DEP atribuída a uma caixa de correio, use o cmdlet Get-MailboxStatistics. O cmdlet retorna um identificador exclusivo (GUID).
  
1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e DataEncryptionPolicyID retorna o GUID da DEP. Para obter mais informações sobre o cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).
  
2. Execute o cmdlet Get-DataEncryptionPolicy para descobrir o nome amigável da DEP à qual a caixa de correio é atribuída.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Onde *GUID* é o GUID retornado pelo cmdlet Get-MailboxStatistics na etapa anterior.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Verificar se a chave do cliente terminou a criptografia

Se você acabou de reverter uma chave de cliente, atribuiu uma nova DEP ou migrou uma caixa de correio, use as etapas desta seção para garantir que a criptografia seja concluída.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Verificar se a criptografia é concluída para o Exchange Online e o Skype for Business

Criptografar uma caixa de correio pode levar algum tempo. Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia após alterar uma DEP ou a primeira vez em que você atribui uma DEP a uma caixa de correio.
  
Use o cmdlet Get-MailboxStatistics para determinar se uma caixa de correio está criptografada.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

A Propriedade IsEncrypted retornará um valor **true** se a caixa de correio for criptografada e um valor **false** se a caixa de correio não estiver criptografada.

O tempo para concluir movimentações de caixa de correio depende do tamanho da caixa de correio. Se a chave do cliente não tiver criptografado completamente a caixa de correio após 72 horas a partir do momento em que você atribuir uma nova DEP, contate o suporte da Microsoft para obter ajuda. O cmdlet New-MoveRequest não está mais disponível para movimentações de caixa de correio locais. Consulte [este anúncio](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) para obter mais informações.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Verificar se a criptografia é concluída para os arquivos do SharePoint Online, do OneDrive for Business e do teams

Verifique o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy da seguinte maneira:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

A saída deste cmdlet inclui:
  
- O URI da chave primária.

- O URI da chave secundária.

- O status de criptografia para a geografia. Os Estados possíveis incluem:

  - Não **registrado:** A criptografia de chave do cliente ainda não foi aplicada.

  - **Registro:** A criptografia da chave do cliente foi aplicada e seus arquivos estão em processo de criptografia. Se a chave da geografia estiver se registrando, você também verá informações sobre qual porcentagem de sites na geografia estão concluídas para que você possa monitorar o andamento da criptografia.

  - **Registrado:** A criptografia da chave do cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.

  - **Sem interrupção:** Um rolo de chave está em andamento. Se a chave da geografia estiver sem interrupção, você também verá informações sobre a porcentagem de sites que concluiram a operação do registro principal para que você possa monitorar o progresso.

## <a name="unassign-a-dep-from-a-mailbox"></a>Cancelar a atribuição de uma DEP de uma caixa de correio

Você não atribui uma DEP de uma caixa de correio usando o cmdlet Set-Mailbox do PowerShell e definindo o `DataEncryptionPolicy` para `$NULL` . A execução deste cmdlet retira a atribuição da DEP atribuída atualmente e criptografa a caixa de correio usando a DEP associada às chaves gerenciadas padrão da Microsoft. Não é possível cancelar a atribuição da DEP usada pelas chaves gerenciadas pela Microsoft. Se você não quiser usar chaves gerenciadas pela Microsoft, poderá atribuir outra DEP à caixa de correio.

Para cancelar a atribuição da DEP de uma caixa de correio usando o cmdlet Set-Mailbox do PowerShell, conclua estas etapas.

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Execute o cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revogar suas chaves e iniciar o processo de caminho de limpeza de dados

Você controla a revogação de todas as chaves raiz, incluindo a chave de disponibilidade. A chave do cliente oferece controle do aspecto de planejamento de saída dos requisitos normativos para você. Se você decidir revogar suas chaves para limpar seus dados e sair do serviço, o serviço excluirá a chave de disponibilidade após a conclusão do processo de limpeza de dados.

O Microsoft 365 audita e valida o caminho de limpeza dos dados. Para obter mais informações, consulte o SSAE 18 SOC 2 Report disponível no [portal de confiança do serviço](https://servicetrust.microsoft.com/). Além disso, a Microsoft recomenda os seguintes documentos:

- [Guia de conformidade e avaliação de riscos para instituições financeiras na nuvem da Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Considerações de planejamento de saída do O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

O caminho de limpeza de dados difere ligeiramente entre os diferentes serviços.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revogar as chaves do cliente e a chave de disponibilidade para o Exchange Online e o Skype for Business

Ao iniciar o caminho de limpeza de dados do Exchange Online e do Skype for Business, você define uma solicitação de limpeza de dados permanente em uma DEP. Isso exclui permanentemente os dados criptografados nas caixas de correio às quais a DEP é atribuída.

Como você só pode executar o cmdlet do PowerShell em uma DEP por vez, considere reatribuir uma única DEP a todas as suas caixas de correio antes de iniciar o caminho de limpeza dos dados.

> [!WARNING]
> Não use o caminho de limpeza de dados para excluir um subconjunto de suas caixas de correio. Este processo destina-se apenas aos clientes que estão saindo do serviço.

Para iniciar o caminho de limpeza de dados, conclua estas etapas:

1. Remova as permissões de quebra e descodificação de "O365 Exchange Online" dos compartimentos de chave do Azure.

2. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

3. Para cada DEP que contenha caixas de correio que você deseja excluir, execute o cmdlet [set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) da seguinte maneira.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Se o comando falhar, verifique se você removeu as permissões do Exchange Online das chaves do Azure Key Vault, conforme especificado anteriormente nesta tarefa.Depois de definir a opção PermanentDataPurgeRequested usando o cmdlet Set-DataEncryptionPolicy, você não poderá mais atribuir essa DEP às caixas de correio.

4. Entre em contato com o suporte da Microsoft e solicite a limpeza de dados eDocument.

    Na sua solicitação, a Microsoft envia a você um documento legal para confirmar e autorizar a exclusão de dados. A pessoa em sua organização que se inscreveu como Aprovador na oferta do FastTrack durante a integração precisa assinar este documento. Normalmente, esse é um executivo ou outra pessoa designada em sua empresa legalmente autorizada a assinar a papelada em nome da sua organização.

5. Depois que seu representante assinou o documento legal, devolva-o à Microsoft (geralmente por meio de uma assinatura eDoc).

    Depois que a Microsoft recebe o documento legal, a Microsoft executa cmdlets para acionar a limpeza de dados que primeiro exclui a política, marca as caixas de correio para exclusão permanente e, em seguida, exclui a chave de disponibilidade. Após a conclusão do processo de limpeza de dados, os dados são removidos, não podem ser acessados pelo Exchange Online e não são recuperáveis.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Revogar as chaves do cliente e a chave de disponibilidade para os arquivos do SharePoint Online, do OneDrive for Business e do teams

Para iniciar o caminho de limpeza de dados para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, conclua estas etapas:

1. Revoga o acesso do Azure Key Vault. Todos os administradores de cofre de chaves devem concordar em revogar o acesso.

   Você não exclui o Azure Key Vault para o SharePoint Online. Os principais cofres podem ser compartilhados entre vários locatários e DEPs do SharePoint Online.

2. Contate a Microsoft para excluir a chave de disponibilidade.

    Ao entrar em contato com a Microsoft para excluir a chave de disponibilidade, enviaremos um documento legal. A pessoa em sua organização que se inscreveu como Aprovador na oferta do FastTrack durante a integração precisa assinar este documento. Normalmente, este é um executivo ou outra pessoa designada na sua empresa legalmente autorizada a assinar a papelada em nome da sua organização.

3. Depois que o representante assinar o documento legal, devolva-o à Microsoft (geralmente por meio de uma assinatura eDoc).

   Depois que a Microsoft recebe o documento legal, executamos cmdlets para acionar a limpeza de dados que realiza a exclusão de criptografia da chave do locatário, da chave do site e de todas as chaves individuais por documento, irrevogável a hierarquia de chaves. Depois que os cmdlets de limpeza de dados forem concluídos, seus dados foram removidos.

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia de serviço com a chave do cliente](customer-key-overview.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Configurar a chave do cliente](customer-key-set-up.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Sistema de Proteção de Dados do Cliente](customer-lockbox-requests.md)

- [Criptografia de serviço](office-365-service-encryption.md)
