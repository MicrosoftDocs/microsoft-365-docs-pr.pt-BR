---
title: Gerenciar Chave do Cliente
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
description: Depois de configurar a Chave do Cliente, saiba como gerenciá-la restaurando chaves AKV e gerenciando permissões e políticas de criptografia de dados.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547081"
---
# <a name="manage-customer-key"></a>Gerenciar Chave do Cliente

Depois de configurar a Chave do Cliente para o Office 365, você poderá gerenciar suas chaves conforme descrito neste artigo. Saiba mais sobre a Chave do Cliente nos tópicos relacionados.

## <a name="restore-azure-key-vault-keys"></a>Restaurar chaves do Azure Key Vault

Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão suave. Todas as chaves usadas com a Chave do Cliente devem ter a exclusão suave habilitada. A exclusão suave age como uma lixeira e permite a recuperação por até 90 dias sem a necessidade de restauração. A restauração só deve ser necessária em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido. Se você tiver que restaurar uma chave para uso com a Chave do Cliente, no Azure PowerShell, execute o cmdlet Restore-AzureKeyVaultKey seguinte:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Por exemplo:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se o cofre de chaves já contiver uma chave com o mesmo nome, a operação de restauração falhará. Restore-AzKeyVaultKey restaura todas as versões principais e todos os metadados da chave, incluindo o nome da chave.
  
## <a name="manage-key-vault-permissions"></a>Gerenciar permissões de cofre de chaves

Vários cmdlets estão disponíveis que permitem exibir e, se necessário, remover permissões de cofre de chaves. Talvez seja necessário remover permissões, por exemplo, quando um funcionário deixa a equipe. Para cada uma dessas tarefas, você usará o Azure PowerShell. Para saber mais sobre o Azure PowerShell, confira [Visão geral do Azure PowerShell.](https://docs.microsoft.com/powershell/azure/)

Para exibir as permissões do cofre de chaves, execute o Get-AzKeyVault cmdlet.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Por exemplo:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Para remover as permissões de um administrador, execute o Remove-AzKeyVaultAccessPolicy cmdlet:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Por exemplo:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Gerenciar políticas de criptografia de dados (DEPs) com a Chave do Cliente

A Chave do Cliente lida com DEPs de maneira diferente entre os diferentes serviços. Por exemplo, você pode criar um número diferente de DEPs para os diferentes serviços.

**Exchange Online e Skype for Business:** Você pode criar até 50 DEPs. Para obter instruções, [consulte Criar uma política de criptografia de dados (DEP) para uso com o Exchange Online e o Skype for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

**SharePoint Online, OneDrive for Business e arquivos do Teams:** Uma DEP se aplica a dados em uma localização geográfica, também chamada de _localização geográfica._ Se você usar o recurso multi-geo do Office 365, poderá criar uma DEP por geo. Se você não estiver usando multi-geo, poderá criar uma DEP. Normalmente, você cria a DEP quando configura a Chave do Cliente. Para obter instruções, confira Criar uma política de criptografia de dados [(DEP) para cada área](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)geográfica do SharePoint Online e do OneDrive for Business.

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Exibir os DEPs que você criou para o Exchange Online e o Skype for Business

Para exibir uma lista de todos os DEPs criados para o Exchange Online e o Skype for Business usando o cmdlet Get-DataEncryptionPolicy PowerShell, conclua estas etapas.

1. Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Para retornar todos os DEPs em sua organização, execute o cmdlet Get-DataEncryptionPolicy sem parâmetros.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obter mais informações sobre Get-DataEncryptionPolicy cmdlet, consulte [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Atribuir uma DEP antes de migrar uma caixa de correio para a nuvem

Quando você atribui a DEP, o Microsoft 365 criptografa o conteúdo da caixa de correio usando a DEP atribuída durante a migração. Esse processo é mais eficiente do que migrar a caixa de correio, atribuir a DEP e aguardar a criptografia ocorrer, o que pode levar horas ou possivelmente dias.

Para atribuir um DEP a uma caixa de correio antes de migrá-la para o Office 365, execute o cmdlet Set-MailUser no PowerShell do Exchange Online:

1. Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o Set-MailUser cmdlet.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e *DataEncryptionPolicyIdParameter* é a ID da DEP. Para obter mais informações sobre Set-MailUser cmdlet, consulte [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar a DEP atribuída a uma caixa de correio

Para determinar a DEP atribuída a uma caixa de correio, use o Get-MailboxStatistics cmdlet. O cmdlet retorna um identificador exclusivo (GUID).
  
1. Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Onde *GeneralMailboxOrMailUserIdParameter especifica* uma caixa de correio e DataEncryptionPolicyID retorna o GUID da DEP. Para obter mais informações sobre o Get-MailboxStatistics cmdlet, consulte [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).
  
2. Execute o Get-DataEncryptionPolicy cmdlet para descobrir o nome amigável da DEP à qual a caixa de correio está atribuída.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Onde *GUID* é o GUID retornado pelo Get-MailboxStatistics cmdlet na etapa anterior.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Verificar se a chave do cliente concluiu a criptografia

Se você acabou de rolar uma Chave do Cliente, se atribuiu uma nova DEP ou migrou uma caixa de correio, use as etapas nesta seção para garantir que a criptografia seja concluída.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Verificar a criptografia concluída para o Exchange Online e o Skype for Business

Criptografar uma caixa de correio pode levar algum tempo. Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia depois de alterar uma DEP ou da primeira vez que atribuir um DEP a uma caixa de correio.
  
Use o Get-MailboxStatistics cmdlet para determinar se uma caixa de correio está criptografada.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

A propriedade IsEncrypted retornará um valor verdadeiro se a  caixa de correio estiver criptografada e um valor falso se a caixa de correio não estiver criptografada. 

O tempo para concluir as movimentações de caixa de correio depende do tamanho da caixa de correio. Se a Chave do Cliente não tiver criptografado completamente a caixa de correio após 72 horas a partir do momento em que você atribuir uma nova DEP, entre em contato com o suporte da Microsoft para ajudar. O New-MoveRequest cmdlet não está mais disponível para movimentações de caixa de correio local. Consulte este [comunicado para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obter informações adicionais.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Verificar a criptografia concluída para arquivos do SharePoint Online, OneDrive for Business e Teams

Verifique o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy a seguir:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

A saída desse cmdlet inclui:
  
- O URI da chave primária.

- O URI da chave secundária.

- O status de criptografia da área geográfica. Os estados possíveis incluem:

  - **Não registro:** A criptografia da Chave do Cliente ainda não foi aplicada.

  - **Registro:** A criptografia de Chave de Cliente foi aplicada e seus arquivos estão em processo de criptografia. Se a chave da área geográfica estiver se registrando, você também verá informações sobre qual porcentagem de sites na área geográfica está concluída para que você possa monitorar o progresso da criptografia.

  - **Registrado:** A criptografia da Chave do Cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.

  - **Rolagem:** Uma rolagem de teclas está em andamento. Se a chave da área geográfica estiver sendo rolada, você também verá informações sobre qual porcentagem de sites concluiu a operação de rolagem de chaves para que você possa monitorar o progresso.

## <a name="unassign-a-dep-from-a-mailbox"></a>Desa designe uma DEP de uma caixa de correio

Você desa designa uma DEP de uma caixa de correio usando o cmdlet Set-mailbox PowerShell e configurando `DataEncryptionPolicy` o para `$NULL` . A execução desse cmdlet desassocia a DEP atribuída no momento e criptografa a caixa de correio usando a DEP associada às chaves gerenciadas padrão da Microsoft. Você não pode desa designá-la usada pelas chaves gerenciadas da Microsoft. Se você não quiser usar chaves gerenciadas da Microsoft, poderá atribuir outra DEP à caixa de correio.

Para desa designar a DEP de uma caixa de correio usando o cmdlet Set-Mailbox PowerShell, conclua estas etapas.

1. Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o Set-Mailbox cmdlet.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revogar suas chaves e iniciar o processo de limpeza de dados

Você controla a revogação de todas as chaves raiz, incluindo a chave de disponibilidade. A Chave do Cliente fornece controle do aspecto de planejamento de saída dos requisitos regulatórios para você. Se você decidir revogar suas chaves para limpar seus dados e sair do serviço, o serviço excluirá a chave de disponibilidade depois que o processo de limpeza de dados for concluído.

O Microsoft 365 audita e valida o caminho de limpeza de dados. Para obter mais informações, consulte o Relatório do SOC 2 do SSAE 18 disponível no [Portal de Confiança do Serviço.](https://servicetrust.microsoft.com/) Além disso, a Microsoft recomenda os seguintes documentos:

- [Guia de Avaliação de Risco e Conformidade para Instituições Financeiras no Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Considerações sobre o planejamento de saída do O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

O caminho de limpeza de dados difere ligeiramente entre os diferentes serviços.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revogar suas Chaves do Cliente e a chave de disponibilidade do Exchange Online e do Skype for Business

Ao iniciar o caminho de limpeza de dados para o Exchange Online e o Skype for Business, você configura uma solicitação de limpeza de dados permanente em uma DEP. Isso exclui permanentemente os dados criptografados nas caixas de correio às quais essa DEP está atribuída.

Como você só pode executar o cmdlet do PowerShell em um DEP por vez, considere reatribuir uma única DEP a todas as suas caixas de correio antes de iniciar o caminho de limpeza de dados.

> [!WARNING]
> Não use o caminho de limpeza de dados para excluir um subconjunto de suas caixas de correio. Esse processo destina-se apenas aos clientes que estão saindo do serviço.

Para iniciar o caminho de limpeza de dados, conclua estas etapas:

1. Remova as permissões wrap e unwrap do "Exchange Online do O365" do Azure Key Vaults.

2. Usando uma conta de trabalho ou de estudante que tenha privilégios de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

3. Para cada DEP que contém caixas de correio que você deseja excluir, execute o cmdlet [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) da seguinte forma.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Se o comando falhar, verifique se você removeu as permissões do Exchange Online das duas chaves no Azure Key Vault conforme especificado anteriormente nesta tarefa.Depois de definir a opção PermanentDataPurgeRequested usando o cmdlet Set-DataEncryptionPolicy, você não poderá mais atribuir essa DEP às caixas de correio.

4. Entre em contato com o suporte da Microsoft e solicite o eDocument de Limpeza de Dados.

    A sua solicitação, a Microsoft envia um documento legal para confirmar e autorizar a exclusão de dados. A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento. Normalmente, é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.

5. Depois que seu representante assinar o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).

    Depois que a Microsoft recebe o documento legal, a Microsoft executa cmdlets para disparar a limpeza de dados que primeiro exclui a política, marca as caixas de correio para exclusão permanente e, em seguida, exclui a chave de disponibilidade. Depois que o processo de limpeza de dados for concluído, os dados serão limpos, estarão inacessíveis para o Exchange Online e não serão recuperáveis.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Revogar suas Chaves do Cliente e a chave de disponibilidade para arquivos do SharePoint Online, OneDrive for Business e Teams

Para iniciar o caminho de limpeza de dados para arquivos do SharePoint Online, OneDrive for Business e Teams, conclua estas etapas:

1. Revogar o acesso ao Azure Key Vault. Todos os administradores do cofre de chaves devem concordar em revogar o acesso.

   Você não exclui o Azure Key Vault para SharePoint Online. Os cofres de chaves podem ser compartilhados entre vários locatários e DEPs do SharePoint Online.

2. Contate a Microsoft para excluir a chave de disponibilidade.

    Quando você contatar a Microsoft para excluir a chave de disponibilidade, enviaremos um documento legal. A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento. Normalmente, é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.

3. Depois que seu representante assinar o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).

   Depois que a Microsoft recebe o documento legal, executamos cmdlets para disparar a limpeza de dados que executa a exclusão criptografada da chave de locatário, da chave do site e de todas as chaves individuais por documento, quebrando irrevogavelmente a hierarquia de chaves. Depois que os cmdlets de limpeza de dados são concluídos, seus dados são limpos.

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Configurar a Chave do Cliente](customer-key-set-up.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Sistema de Proteção de Dados do Cliente](customer-lockbox-requests.md)

- [Criptografia de Serviço](office-365-service-encryption.md)
