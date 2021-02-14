---
title: Colocar um In-Place em uma caixa de correio excluída de forma suave no Exchange Online
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
description: Saiba como criar um In-Place para uma caixa de correio excluída de forma flexível para torná-la inativa e preservar seu conteúdo.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818860"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Colocar um In-Place em uma caixa de correio excluída de forma suave no Exchange Online

Saiba como criar um In-Place para uma caixa de correio excluída de forma flexível para torná-la inativa e preservar seu conteúdo. Em seguida, você pode usar as ferramentas de Descoberta Eletrônico da Microsoft para pesquisar a caixa de correio inativa.

> [!IMPORTANT]
> À medida que continuamos investindo em maneiras diferentes de preservar o conteúdo da caixa de correio, anunciamos a ressarção de In-Place retém no Centro de administração do Exchange (EAC). A partir de 1º de julho de 2020, você não poderá criar novos In-Place retém no Exchange Online. Mas você ainda poderá gerenciar In-Place Retém no EAC ou usando o cmdlet **Set-MailboxSearch** no PowerShell do Exchange Online. No entanto, a partir de 1º de outubro de 2020, você não poderá gerenciar o In-Place Retém. Você só os removerá no EAC ou usando o cmdlet **Remove-MailboxSearch.** Para obter mais informações sobre a baixa In-Place, consulte a Baixa das ferramentas de [Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)
  
Você pode ter uma situação em que uma pessoa saiu da sua organização, e a conta de usuário e a caixa de correio correspondentes foram excluídas. Depois disso, você perceberá que há informações na caixa de correio que precisam ser preservadas. O que você pode fazer? Se o período de retenção da caixa de correio excluída não tiver expirado, você poderá colocar uma retenção de In-Place na caixa de correio excluída (chamada de caixa de correio excluída de forma flexível) e torná-la uma caixa de correio inativa. Uma  *caixa de correio inativa*  é usada para preservar o email de um ex-funcionário depois que ele sai da organização. O conteúdo de uma caixa de correio inativa é preservado durante a In-Place de correio que foi colocada na caixa de correio excluída de forma flexível quando ela foi inativa. Depois que In-Place caixa de correio for inativa, você poderá pesquisar na caixa de correio usando a Descoberta Eletrônico do In-Place no Exchange Online &, a Pesquisa de Conteúdo no Centro de Conformidade e Segurança ou o Centro de Descobertas Eletrônicos no SharePoint Online. 
  
> [!NOTE]
> No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada dentro de um período de retenção específico. O período de retenção de caixa de correio excluída de forma suave no Exchange Online é de 30 dias. Isso significa que a caixa de correio pode ser recuperada (ou se tornou uma caixa de correio inativa) dentro de 30 dias após ser excluída. Após 30 dias, uma caixa de correio excluída de forma flexível é marcada para exclusão permanente e não pode ser recuperada ou inativa. 
  
## <a name="requirements-for-in-place-holds"></a>Requisitos para In-Place Retém

- Você precisa usar o cmdlet **New-MailboxSearch** no Windows PowerShell para colocar um In-Place em uma caixa de correio excluída de forma suave. Você não pode usar o Centro de administração do Exchange (EAC) ou o Centro de Descobertas Do SharePoint Online. 

- Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Execute o seguinte comando para obter informações de identidade sobre as caixas de correio excluídas de forma suave em sua organização. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Para saber mais sobre caixas de correio inativas, confira Visão geral de caixas de correio [inativas no Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Colocar um In-Place em uma caixa de correio excluída de forma flexível para torná-la uma caixa de correio inativa

Use o cmdlet **New-MailboxSearch** para tornar uma caixa de correio excluída de forma flexível uma caixa de correio inativa. Para obter mais informações, [consulte New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Crie uma variável que contenha as propriedades da caixa de correio excluída de forma suave.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > No comando anterior, use o valor da propriedade **DistinguishedName** ou **ExchangeGuid** para identificar a caixa de correio excluída de forma suave. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e uma caixa de correio excluída de forma suave tenham o mesmo endereço SMTP principal. 
  
2. Crie um In-Place e coloque-o na caixa de correio excluída de forma suave. Neste exemplo, nenhuma duração de espera é especificada. Isso significa que os itens serão mantidos indefinidamente ou até que a espera seja removida da caixa de correio inativa.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   Você também pode especificar uma duração de espera ao criar o In-Place De espera. Este exemplo mantém itens na caixa de correio inativa por aproximadamente 7 anos.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Após alguns instantes, execute um dos seguintes comandos para verificar se a caixa de correio excluída de forma flexível é uma caixa de correio inativa.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Ou
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Mais informações

Depois de tornar uma caixa de correio excluída de forma flexível uma caixa de correio inativa, há várias maneiras de gerenciar a caixa de correio. Para saber mais, confira:
  
- [Alterar a duração de retenção de uma caixa de correio inativa](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Recuperar uma caixa de correio inativa](recover-an-inactive-mailbox.md)

- [Restaurar uma caixa de correio inativa](restore-an-inactive-mailbox.md)

- [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md) (removendo a espera)
