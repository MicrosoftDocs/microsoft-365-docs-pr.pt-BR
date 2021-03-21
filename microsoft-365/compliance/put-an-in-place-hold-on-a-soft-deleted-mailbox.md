---
title: Colocar uma In-Place em uma caixa de correio excluída de forma suave no Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Saiba como criar um In-Place para uma caixa de correio excluída de forma suave para torná-la inativa e preservar seu conteúdo.
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925517"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Colocar uma In-Place em uma caixa de correio excluída de forma suave no Exchange Online

Saiba como criar um In-Place para uma caixa de correio excluída de forma suave para torná-la inativa e preservar seu conteúdo. Em seguida, você pode usar as ferramentas de Descoberta Eletrônico da Microsoft para pesquisar a caixa de correio inativa.

> [!IMPORTANT]
> À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a In-Place Detém no Centro de administração do Exchange (EAC). A partir de 1º de julho de 2020, você não poderá criar novos In-Place no Exchange Online. Mas você ainda poderá gerenciar o In-Place no EAC ou usando o cmdlet **Set-MailboxSearch** no PowerShell do Exchange Online. No entanto, a partir de 1º de outubro de 2020, você não poderá gerenciar In-Place Holds. Você só os removerá no EAC ou usando o cmdlet **Remove-MailboxSearch.** Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)
  
Você pode ter uma situação em que uma pessoa tenha deixado sua organização e sua conta de usuário e caixa de correio correspondentes tenham sido excluídas. Depois, você percebe que há informações na caixa de correio que precisam ser preservadas. O que você pode fazer? Se o período de retenção de caixa de correio excluído não tiver expirado, você poderá colocar uma retenção de In-Place na caixa de correio excluída (chamada de caixa de correio excluída de forma suave) e torná-la uma caixa de correio inativa. Uma  *caixa de correio inativa*  é usada para preservar o email de um ex-funcionário depois que ele sai da sua organização. O conteúdo de uma caixa de correio inativa é preservado durante a duração do In-Place Que foi colocado na caixa de correio excluída quando ela foi inativa. Depois que a caixa de correio for inativa, você poderá pesquisar In-Place caixa de correio usando In-Place Descoberta eDiscovery no Exchange Online, Pesquisa de Conteúdo no Centro de Conformidade & Segurança ou no Centro de Descoberta Eletrônico no SharePoint Online. 
  
> [!NOTE]
> No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada em um período de retenção específico. O período de retenção de caixa de correio excluído no Exchange Online é de 30 dias. Isso significa que a caixa de correio pode ser recuperada (ou feita uma caixa de correio inativa) dentro de 30 dias após a exclusão. Após 30 dias, uma caixa de correio excluída de forma suave é marcada para exclusão permanente e não pode ser recuperada ou inativa. 
  
## <a name="requirements-for-in-place-holds"></a>Requisitos para In-Place Detém

- Você precisa usar o cmdlet **New-MailboxSearch** no Windows PowerShell para colocar um In-Place em uma caixa de correio excluída de forma suave. Não é possível usar o Centro de administração do Exchange (EAC) ou o Centro de Descoberta Virtual no SharePoint Online. 

- Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Execute o seguinte comando para obter informações de identidade sobre as caixas de correio excluídas de forma suave em sua organização. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Para obter mais informações sobre caixas de correio inativas, consulte [Overview of inactive mailboxes in office 365](inactive-mailboxes-in-office-365.md).

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Colocar uma In-Place em uma caixa de correio excluída de forma suave para torná-la uma caixa de correio inativa

Use o cmdlet **New-MailboxSearch** para tornar uma caixa de correio excluída de forma suave uma caixa de correio inativa. Para obter mais informações, consulte [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).
  
1. Crie uma variável que contenha as propriedades da caixa de correio excluída de forma suave.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > No comando anterior, use o valor da propriedade **DistinguishedName** ou **ExchangeGuid** para identificar a caixa de correio excluída de forma suave. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e uma caixa de correio excluída de forma suave tenham o mesmo endereço SMTP principal. 
  
2. Crie uma In-Place e coloque-a na caixa de correio excluída. Neste exemplo, nenhuma duração de espera é especificada. Isso significa que os itens serão mantidos indefinidamente ou até que a espera seja removida da caixa de correio inativa.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   Você também pode especificar uma duração de espera ao criar o In-Place Hold. Este exemplo mantém itens na caixa de correio inativa por aproximadamente 7 anos.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Depois de alguns instantes, execute um dos seguintes comandos para verificar se a caixa de correio excluída de forma suave é uma caixa de correio inativa.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Ou
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Mais informações

Depois de tornar uma caixa de correio excluída de forma suave uma caixa de correio inativa, há várias maneiras de gerenciar a caixa de correio. Para mais informações, confira:
  
- [Alterar a duração de retenção de uma caixa de correio inativa](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Recuperar uma caixa de correio inativa](recover-an-inactive-mailbox.md)

- [Restaurar uma caixa de correio inativa](restore-an-inactive-mailbox.md)

- [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md) (removendo a espera)