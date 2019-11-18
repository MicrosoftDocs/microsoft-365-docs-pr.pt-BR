---
title: Colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível no Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Saiba como criar um bloqueio in-loco para uma caixa de correio excluída de forma reversível para torná-la inativa e preservar seu conteúdo. Em seguida, você pode usar as ferramentas de descoberta eletrônica da Microsoft para pesquisar a caixa de correio inativa.
ms.openlocfilehash: ab8ab8b8eff0eefd91a87fb72439547c7d2fe97b
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38684846"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível no Exchange Online

Saiba como criar um bloqueio in-loco para uma caixa de correio excluída de forma reversível para torná-la inativa e preservar seu conteúdo. Em seguida, você pode usar as ferramentas de descoberta eletrônica da Microsoft para pesquisar a caixa de correio inativa.
  
> [!NOTE]
> Adiamos o prazo para a criação de novas suspensões in-loco no Exchange Online (nos planos autônomos do Office 365 e do Exchange Online). Mas no final deste ano ou no início do próximo, você não poderá criar novos Bloqueios In-loco no Exchange Online. Como alternativa ao uso de bloqueios in-loco, você pode usar [casos de descoberta eletrônica](https://go.microsoft.com/fwlink/?linkid=780738) ou [políticas de retenção](https://go.microsoft.com/fwlink/?linkid=827811) no centro de conformidade de & de segurança. Depois de encerrarmos novas suspensões in-loco, você ainda poderá modificar bloqueios in-loco existentes e criar novos bloqueios in-loco no Exchange Server 2013 e implantações híbridas do Exchange ainda terão suporte. Além disso, você ainda poderá colocar caixas de correio em retenção de litígio. 
  
Você pode ter uma situação em que uma pessoa deixou sua organização e a conta de usuário correspondente e caixa de correio foram excluídas. Posteriormente, você perceberá que há informações na caixa de correio que precisam ser preservadas. O que você pode fazer? Se o período de retenção de caixa de correio excluída ainda não tiver expirado, você pode colocar um bloqueio in-loco na caixa de correio excluída (chamada de caixa de correio excluída por software) e torná-la uma caixa de correio inativa. Uma *caixa de correio inativa* é usada para preservar o email de um funcionário anterior, depois que ele deixa sua organização. O conteúdo de uma caixa de correio inativa é preservado para a duração do bloqueio in-loco que foi colocado na caixa de correio excluída por software quando ele foi tornado inativo. Após a caixa de correio ser desativada, você pode pesquisar a caixa de correio usando a descoberta eletrônica in-loco no Exchange Online, pesquisa de conteúdo no centro de conformidade de & de segurança ou no centro de descoberta eletrônica no SharePoint Online. 
  
> [!NOTE]
> No Exchange Online, uma caixa de correio excluída por software é uma caixa de correio excluída, mas pode ser recuperada dentro de um período de retenção específico. O período de retenção de caixa de correio excluída de forma reversível no Exchange Online é de 30 dias. Isso significa que a caixa de correio pode ser recuperada (ou criada em uma caixa de correio inativa) em 30 dias após a exclusão. Após 30 dias, uma caixa de correio excluída por software é marcada para exclusão permanente e não pode ser recuperada ou desativada. 
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa usar o cmdlet **New-MailboxSearch** no Windows PowerShell para colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível. Você não pode usar o centro de administração do Exchange (Eat) ou o centro de descoberta eletrônica no SharePoint Online. 

- Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Execute o seguinte comando para obter informações de identidade sobre as caixas de correio excluídas por software em sua organização. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Para obter mais informações sobre caixas de correio inativas, consulte [visão geral das caixas de correio inativas no Office 365](inactive-mailboxes-in-office-365.md).

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível para torná-la uma caixa de correio inativa

Use o cmdlet **New-MailboxSearch** para tornar uma caixa de correio de exclusão flexível uma caixa de correio inativa. Para obter mais informações, consulte [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Criar uma variável que contém as propriedades da caixa de correio excluída de forma reversível.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > No comando anterior, use o valor da propriedade **distinguishedName** ou **ExchangeGuid** para identificar a caixa de correio excluída de forma reversível. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e uma caixa de correio excluída de forma reversível possam ter o mesmo endereço SMTP principal. 
  
2. Crie um bloqueio in-loco e coloque-o na caixa de correio excluída de forma reversível. Neste exemplo, não é especificada nenhuma duração de retenção. Isso significa que os itens serão mantidos indefinidamente ou até que a retenção seja removida da caixa de correio inativa.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   Você também pode especificar uma duração de retenção ao criar o bloqueio in-loco. Este exemplo mantém itens na caixa de correio inativa por aproximadamente 7 anos.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Após alguns momentos, execute um dos seguintes comandos para verificar se a caixa de correio excluída por software é uma caixa de correio inativa.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Ou
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Mais informações

Após tornar uma caixa de correio inativa excluída por software, há várias maneiras de gerenciar a caixa de correio. Para saber mais, confira:
  
- [Alterar a duração de retenção de uma caixa de correio inativa](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Recuperar uma caixa de correio inativa](recover-an-inactive-mailbox.md)

- [Restaurar uma caixa de correio inativa](restore-an-inactive-mailbox.md)

- [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md) (removendo a isenção)
