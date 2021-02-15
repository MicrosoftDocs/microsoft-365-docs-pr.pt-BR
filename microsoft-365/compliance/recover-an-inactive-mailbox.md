---
title: Recuperar uma caixa de correio inativa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Saiba como recuperar o conteúdo de uma caixa de correio inativa no Office 365 convertendo-o em uma nova caixa de correio que contém o conteúdo da caixa de correio inativa.
ms.openlocfilehash: ab5b3265cd9d3b1bab539d45e5daf0e6b4110f9a
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920047"
---
# <a name="recover-an-inactive-mailbox"></a>Recuperar uma caixa de correio inativa

Uma caixa de correio inativa (que é um tipo de caixa de correio excluída de forma flexível) é usada para preservar o email de um ex-funcionário depois que ele sai da organização. Se esse funcionário retornar à sua organização ou se outro funcionário assumir as responsabilidades de trabalho do ex-funcionário, haverá duas maneiras de disponibilizar o conteúdo da caixa de correio inativa para um usuário:

- **Recuperar uma caixa de correio inativa.** Se o ex-funcionário retornar à sua organização ou se um novo funcionário for contratado para assumir as responsabilidades de trabalho do ex-funcionário, você poderá recuperar o conteúdo da caixa de correio inativa. Esse método converte a caixa de correio inativa em uma nova caixa de correio ativa que contém o conteúdo da caixa de correio inativa. Após sua recuperação, a caixa de correio inativa deixa de existir. Os procedimentos neste tópico descrevem esse método.

- **Restaure uma caixa de correio inativa.** Se outro funcionário assumir as responsabilidades de trabalho do ex-funcionário, ou se outro usuário precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Você também pode restaurar o arquivo morto de uma caixa de correio inativa. Para os procedimentos desse método, confira [Restaurar uma caixa de correio inativa no Office 365.](restore-an-inactive-mailbox.md)

Consulte [](#more-information) a seção Mais informações para obter mais detalhes sobre as diferenças entre recuperar e restaurar uma caixa de correio inativa e obter uma descrição do que acontece quando uma caixa de correio inativa é recuperada.

> [!NOTE]
> Não é possível recuperar ou restaurar uma caixa de correio inativa configurada com um arquivo morto de expansão automática. Se você precisar recuperar dados de uma caixa de correio inativa com um arquivo morto de expansão automática, use a pesquisa de conteúdo para exportar os dados da caixa de correio e, em seguida, importe para outra caixa de correio. Para obter instruções, consulte os seguintes tópicos:
>
> - [Pesquisa de conteúdo](content-search.md)
> - [Exportar resultados de pesquisa de conteúdo](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Requisitos para recuperar uma caixa de correio inativa

- Você precisa usar o PowerShell do Exchange Online para recuperar uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Execute o seguinte comando para obter informações de identidade para as caixas de correio inativas em sua organização.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Use as informações retornadas por esse comando para recuperar uma caixa de correio inativa específica.

## <a name="recover-inactive-mailboxes"></a>Recuperar caixas de correio inativas

Use o cmdlet **New-Mailbox** com o parâmetro  *InactiveMailbox*  para recuperar uma caixa de correio inativa.

1. Crie uma variável que contenha as propriedades da caixa de correio inativa.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > No comando anterior, use o valor da propriedade **DistinguishedName** ou **ExchangeGUID** para identificar a caixa de correio inativa. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e inativa possa ter o mesmo endereço SMTP principal.

2. Este exemplo usa as propriedades obtidas no comando anterior e recupera a caixa de correio inativa em uma caixa de correio ativa para a usuária Ann Beebe. Certifique-se de que os valores especificados para os parâmetros  *Name*  e  *MicrosoftOnlineServicesID*  sejam exclusivos em sua organização.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   O endereço SMTP principal da caixa de correio inativa recuperada terá o mesmo valor que o especificado pelo *parâmetro MicrosoftOnlineServicesID.*

Depois de recuperar uma caixa de correio inativa, uma nova conta de usuário também é criada. Você precisa ativar essa conta de usuário atribuindo uma licença. Para atribuir uma licença no centro de administração do Microsoft 365, confira Adicionar usuários e [atribuir licenças ao mesmo tempo.](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)

## <a name="more-information"></a>Mais informações

- **Qual é a principal diferença entre recuperar e restaurar uma caixa de correio inativa?** Ao recuperar uma caixa de correio inativa, ela é convertida em uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e ela é vinculada a uma nova conta de usuário. Após a recuperação, a caixa de correio inativa não existe mais, e quaisquer alterações feitas no conteúdo na nova caixa de correio afetarão o conteúdo originalmente em espera na caixa de correio inativa. Por outro lado, quando você restaura uma caixa de correio inativa, o conteúdo é simplesmente copiado para outra caixa de correio. A caixa de correio inativa é preservada e permanece como inativa. Quaisquer alterações feitas no conteúdo na caixa de correio de destino não afetarão o conteúdo original mantido na caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando a Descoberta In-Place, seu conteúdo pode ser restaurado para outra caixa de correio ou pode ser recuperado ou excluído posteriormente.

- **O que acontece quando você recupera uma caixa de correio inativa?** Quando você recupera uma caixa de correio inativa, ocorrem as seguintes coisas:

  - A espera que foi aplicada a uma caixa de correio inativa é alterada ou removida com base no tipo de espera que foi aplicado à caixa de correio inativa antes de ela ser recuperada.

    - **1.000.00** Se a Habilitada para a Caixa de Correio Inativa for habilitada, ela será removida da caixa de correio recuperada.

    - **As Remoção de** In-Place Local são removidas da caixa de correio recuperada. Isso significa que a caixa de correio recuperada é removida como uma caixa de correio de origem de qualquer In-Place ou In-Place pesquisa de Descoberta Eletrônico.

    - **Política de retenção do Microsoft 365 com Bloqueio de Preservação.** Se *a* caixa de correio inativa tiver sido atribuída a uma política de retenção com Bloqueio de Preservação (chamada de política de retenção bloqueada), a caixa de correio recuperada será atribuída à mesma política de retenção bloqueada. Para obter mais informações sobre políticas de retenção bloqueadas, consulte [ Usar o Bloqueio de Preservação para restringir as alterações nas políticas de retenção e[políticas de rótulo de retenção.](retention-preservation-lock.md)

    - **Política de retenção do Microsoft 365 sem Bloqueio de Preservação.** A caixa de correio inativa é removida de qualquer política de retenção desbloqueada do Microsoft 365 que foi aplicada a ela. No entanto, a Retenção de Litígio é habilitada na caixa de correio recuperada para impedir a exclusão do conteúdo da caixa de correio com base em quaisquer políticas de retenção em toda a organização que excluam conteúdo mais antigo do que uma idade específica. Você pode manter a Moção de Litígio ou removê-la. Para obter mais informações, [consulte Create a Litigation Hold](create-a-litigation-hold.md).

  - O período de recuperação de item único (que é definido pela propriedade de caixa de correio **RetainDeletedItemsFor)** é definido como 30 dias. Normalmente, quando uma nova caixa de correio é criada no Exchange Online, esse período de retenção é definido como 14 dias. Definir isso para o valor máximo de 30 dias oferece mais tempo para recuperar quaisquer dados que foram excluídos permanentemente (ou excluídos) da caixa de correio inativa. Você também pode desabilitar a recuperação de item único ou definir o período de recuperação de item único novamente para o padrão de 14 dias. Para mais informações, confira [Ativar ou desativar recuperação de item único para uma caixa de correio](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).

  - A retenção está habilitada e a duração da retenção é definida como 30 dias. Isso significa que a política de retenção padrão do Exchange e quaisquer políticas de retenção do Microsoft 365 em toda a organização ou do Exchange atribuídas à nova caixa de correio não serão processadas por 30 dias. Isso dá ao funcionário ou ao novo proprietário da caixa de correio inativa recuperada tempo para gerenciar as mensagens antigas. Caso contrário, a política de retenção do Exchange ou do Microsoft 365 pode excluir itens de caixa de correio antigos (ou mover itens para a caixa de correio de arquivo morto, se estiver habilitada) que expiraram com base nas configurações configuradas para as políticas de retenção do Exchange ou do Microsoft 365. Após 30 dias, a retenção expira, a propriedade da caixa de correio **RetentionHoldEnabled** é definida como **False** e o Assistente de Pasta Gerenciada começa a processar as políticas atribuídas à caixa de correio. Se você não precisar desse tempo adicional, basta remover a retenção. Como alternativa, você pode aumentar a duração da retenção usando o comando **Set-Mailbox -EndDateForRetentionHold.** Para obter mais informações, consulte [Colocar uma caixa de correio em retenção.](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)

- **Coloque uma espera na caixa de correio recuperada se precisar preservar o estado original da caixa de correio inativa.** Para impedir que o novo proprietário da caixa de correio ou a política de retenção exclui permanentemente todas as mensagens da caixa de correio inativa recuperada, você pode colocar a caixa de correio em Retenção de Litígio. Para obter mais informações, [consulte Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

- **Qual ID de usuário você pode usar ao recuperar uma caixa de correio inativa?** Quando você recupera uma caixa de correio inativa, o valor especificado para o parâmetro  *MicrosoftOnlineServicesID*  pode ser diferente do original associado à caixa de correio inativa. Você também pode usar a ID de usuário original. Porém, conforme mencionado anteriormente, certifique-se de que os valores usados para  *Name*  e  *MicrosoftOnlineServicesID*  sejam exclusivos em sua organização quando você recuperar a caixa de correio inativa.

- **E se o período de retenção de caixa de correio para a caixa de correio inativa não tiver expirado?** Se uma caixa de correio inativa tiver sido excluída de forma flexível há menos de 30 dias, não será possível usar o comando **New-Mailbox -InactiveMailbox** para recuperá-la. Você precisa recuperá-la restaurando a conta de usuário correspondente. Para obter mais informações, [consulte Excluir um usuário da sua organização.](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

- **Como saber se o período de retenção de caixa de correio excluída de forma flexível para uma caixa de correio inativa expirou?** Execute o seguinte comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Se não houver um valor para a propriedade **ExternalDirectoryObjectId,** o período de retenção da caixa de correio expirou e você poderá recuperar a caixa de correio inativa executando o comando **New-Mailbox -InactiveMailbox.** Se houver um valor para a propriedade **ExternalDirectoryObjectId,** o período de retenção da caixa de correio excluída de forma suave não expirou e você terá que recuperar a caixa de correio restaurando a conta de usuário. Confira [Excluir um usuário da sua organização](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user). 

- **Considere habilizar a caixa de correio de arquivo morto depois de recuperar uma caixa de correio inativa.** Isso permite que o usuário ou novo funcionário que retorne as mensagens antigas para a caixa de correio de arquivo morto. E quando a retenção expirar, a política de arquivo morto que faz parte da política de retenção padrão do Exchange atribuída às caixas de correio do Exchange Online moverá itens que são dois anos ou mais antigos para a caixa de correio de arquivo morto. Se você não habilitar a caixa de correio de arquivo morto, os itens com mais de dois anos permanecerão na caixa de correio principal do usuário. Para obter mais informações, consulte [Habilitar caixas de correio de arquivo morto.](enable-archive-mailboxes.md)
