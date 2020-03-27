---
title: Recuperar uma caixa de correio inativa no Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: 'Se um antigo funcionário retornar à sua organização ou se um novo funcionário for contratado para assumir as responsabilidades de trabalho de um funcionário de parte, você poderá recuperar o conteúdo da caixa de correio inativa no Office 365. Ao recuperar uma caixa de correio inativa, ela é convertida em uma nova caixa de correio que contém o conteúdo da caixa de correio inativa. '
ms.openlocfilehash: 5048df8c17f4f44c1bbed33753da51dac53c7789
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978141"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>Recuperar uma caixa de correio inativa no Office 365

Uma caixa de correio inativa (que é um tipo de caixa de correio excluída por software) é usada para preservar o email de um funcionário anterior, depois que ele deixa sua organização. Se esse funcionário retornar à sua organização ou se outro funcionário assumir as responsabilidades de trabalho do antigo funcionário, há duas maneiras de tornar o conteúdo da caixa de correio inativa disponível para um usuário: 
  
- **Recuperar uma caixa de correio inativa** Se o antigo funcionário retornar à sua organização ou se um novo funcionário for contratado para tomar as responsabilidades do cargo do funcionário anterior, você poderá recuperar o conteúdo da caixa de correio inativa. Este método converte a caixa de correio inativa em uma nova caixa de correio ativa que contenha o conteúdo da caixa de correio inativa. Após sua recuperação, a caixa de correio inativa deixa de existir. Os procedimentos neste tópico descrevem esse método. 
    
- **Restaurar uma caixa de correio inativa** Se outro funcionário assumir as responsabilidades de trabalho do antigo funcionário ou se outro usuário precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Você também pode restaurar o arquivo morto de uma caixa de correio inativa. Para obter os procedimentos desse método, confira [restaurar uma caixa de correio inativa no Office 365](restore-an-inactive-mailbox.md).
    
Consulte a seção [mais informações](#more-information) para obter mais detalhes sobre as diferenças entre a recuperação e restauração de uma caixa de correio inativa e para uma descrição do que acontece quando uma caixa de correio inativa é recuperada.
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa usar o PowerShell do Exchange Online para restaurar uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Execute o seguinte comando para obter informações de identidade para as caixas de correio inativas em sua organização. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Use as informações retornadas por este comando para recuperar uma caixa de correio inativa específica.

## <a name="recover-an-inactive-mailbox"></a>Recuperar uma caixa de correio inativa

Use o cmdlet **New-Mailbox** com o parâmetro *InactiveMailbox* para recuperar uma caixa de correio inativa. 
  
1. Criar uma variável que contém as propriedades da caixa de correio inativa. 
    
    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > No comando anterior, use o valor da propriedade **distinguishedName** ou **ExchangeGUID** para identificar a caixa de correio inativa. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e inativa tenha o mesmo endereço SMTP principal. 
  
2. Este exemplo usa as propriedades obtidas no comando anterior e recupera a caixa de correio inativa para uma caixa de correio ativa para o usuário Ana Beebe. Certifique-se de que os valores especificados para os parâmetros *Name* e *MicrosoftOnlineServicesID* sejam exclusivos em sua organização. 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    O endereço SMTP principal da caixa de correio inativa recuperada terá o mesmo valor que aquele especificado pelo parâmetro *MicrosoftOnlineServicesID* . 
    
Após recuperar uma caixa de correio inativa, uma nova conta de usuário do Office 365 também é criada. You have to activate this user account by assigning a license. Para atribuir uma licença no centro de administração do Microsoft 365, confira [Atribuir ou cancelar atribuição de licenças para o Office 365 para empresas](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Mais informações

- **Qual é a principal diferença entre a recuperação e a restauração de uma caixa de correio inativa?** Ao recuperar uma caixa de correio inativa, a caixa de correio é basicamente convertida para uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e a caixa de correio é vinculada a uma nova conta de usuário. Após a recuperação, a caixa de correio inativa não existe mais e qualquer alteração feita no conteúdo da nova caixa de correio afetará o conteúdo que estava originalmente em retenção na caixa de correio inativa. Por outro lado, quando você restaura uma caixa de correio inativa, o conteúdo é simplesmente copiado para outra caixa de correio. A caixa de correio inativa é preservada e permanece como inativa. As alterações feitas no conteúdo da caixa de correio de destino não afetarão o conteúdo original mantido na caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando a descoberta eletrônica in-loco, seu conteúdo pode ser restaurado para outra caixa de correio ou pode ser recuperado ou excluído posteriormente. 
    
- **O que acontece quando você recupera uma caixa de correio inativa?** Ao recuperar uma caixa de correio inativa, ocorrem as seguintes ações: 
    
  - A retenção de litígio (se tiver sido habilitada para a caixa de correio inativa) será removida.
    
  - Bloqueios in-loco são removidos. Isso significa que a caixa de correio inativa é removida como uma caixa de correio de origem de qualquer bloqueio in-loco ou pesquisas de descoberta eletrônica in-loco. 
    
  - A caixa de correio inativa é removida de todas as políticas de retenção do Office 365 que são aplicadas a ela.
    
  - O período de recuperação de item único (que é definido pela propriedade de caixa de correio **RetainDeletedItemsFor** ) é definido como 30 dias. Normalmente, quando uma nova caixa de correio é criada no Exchange Online, esse período de retenção é definido como 14 dias. Definir isso com o valor máximo de 30 dias dá a você mais tempo para recuperar todos os dados que foram excluídos permanentemente (ou removidos) da caixa de correio inativa. Você também pode desabilitar a recuperação de item único ou definir o período de recuperação de item único de volta para o padrão de 14 dias. Para mais informações, confira [Ativar ou desativar recuperação de item único para uma caixa de correio](https://go.microsoft.com/fwlink/?linkid=856769).
    
  - A retenção está habilitada e a duração da retenção é definida como 30 dias. Isso significa que a política de retenção padrão do Exchange e todas as políticas de retenção do Office 365 de toda a organização ou do Exchange que são atribuídas à nova caixa de correio não serão processadas por 30 dias. Isso fornece ao funcionário de retorno ou ao novo proprietário do tempo de caixa de correio inativo recuperado para gerenciar as mensagens antigas. Caso contrário, a política de retenção do Exchange ou do Office 365 pode excluir itens de caixa de correio antigos (ou mover itens para a caixa de correio de arquivo morto, se estiver habilitada) que expiraram com base nas configurações definidas para as políticas de retenção do Exchange ou do Office 365. Após 30 dias, a retenção expirará, a propriedade de caixa de correio **RetentionHoldEnabled** será definida como **false**e o assistente de pasta gerenciada começará a processar as políticas atribuídas à caixa de correio. Se você não precisar desse tempo adicional, só poderá remover a retenção. Como alternativa, você pode aumentar a duração da retenção, usando o comando **Set-Mailbox-EndDateForRetentionHold** . Para obter mais informações, consulte [colocar uma caixa de correio em retenção](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **Coloque uma retenção na caixa de correio recuperada se precisar preservar o estado original da caixa de correio inativa.** Para impedir que o novo proprietário da caixa de correio ou a política de retenção exclua permanentemente qualquer mensagem da caixa de correio inativa recuperada, você pode colocar a caixa de correio em retenção de litígio. Para obter mais informações, consulte [colocar uma caixa de correio em retenção de litígio](https://go.microsoft.com/fwlink/?linkid=856286).
    
- **Qual ID de usuário você pode usar ao recuperar uma caixa de correio inativa?** Ao recuperar uma caixa de correio inativa, o valor especificado para o parâmetro *MicrosoftOnlineServicesID* pode ser diferente do original que estava associado à caixa de correio inativa. Você também pode usar a ID de usuário original. Mas conforme declarado anteriormente, certifique-se de que os valores usados para *Name* e *MicrosoftOnlineServicesID* sejam exclusivos em sua organização quando você recuperar a caixa de correio inativa. 
    
- **E se o período de retenção de caixa de correio para a caixa de correio inativa não tiver expirado?** Se uma caixa de correio inativa foi excluída por menos de 30 dias, não é possível usar o comando **New-Mailbox-InactiveMailbox** para recuperá-la. Você precisa recuperá-lo restaurando a conta de usuário do Office 365 correspondente. Para obter mais informações, consulte [excluir ou restaurar usuários](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **Como saber se o período de retenção de caixa de correio de exclusão reversível de uma caixa de correio inativa expirou?** Execute o seguinte comando. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    Se não houver um valor para a propriedade **ExternalDirectoryObjectId** , o período de retenção de caixa de correio expirou e você pode recuperar a caixa de correio inativa executando o comando **New-Mailbox-InactiveMailbox** . Se houver um valor para a propriedade **ExternalDirectoryObjectId** , o período de retenção de caixa de correio excluída de forma reversível não expirou e você precisa recuperar a caixa de correio restaurando a conta de usuário do Office 365. Consulte [excluir ou restaurar usuários](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **Considere habilitar a caixa de correio de arquivo morto após recuperar uma caixa de correio inativa.** Isso permite que o usuário ou novo funcionário de retorno mova mensagens antigas para a caixa de correio de arquivo morto. E, quando a retenção expirar, a política de arquivamento que faz parte da política de retenção padrão do Exchange atribuída às caixas de correio do Exchange Online moverá itens que têm dois anos ou mais para a caixa de correio de arquivo morto. Se você não habilitar a caixa de correio de arquivo morto, os itens com mais de dois anos permanecerão na caixa de correio principal do usuário. Para obter mais informações, consulte [habilitar caixas de correio de arquivo morto](enable-archive-mailboxes.md).
 