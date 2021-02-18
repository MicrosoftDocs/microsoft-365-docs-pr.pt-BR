---
title: Exibir e liberar mensagens em quarentena de caixas de correio compartilhadas
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Os usuários podem aprender a exibir e agir em mensagens em quarentena enviadas a caixas de correio compartilhadas para as quais eles têm permissões.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31fbf9c54c3f28e439f444dde872469918dc29d4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290136"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="b91d7-103">Exibir e liberar mensagens em quarentena de caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b91d7-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="b91d7-104">Os recursos descritos neste artigo estão atualmente na visualização, não estão disponíveis para todos e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="b91d7-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="b91d7-105">Os usuários podem gerenciar mensagens em quarentena em que são um dos destinatários, conforme descrito em [Find e release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="b91d7-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="b91d7-106">Mas e as caixas de correio compartilhadas onde o usuário tem permissões de Acesso Total e Enviar como ou Enviar em nome de para a caixa de correio, conforme descrito em caixas de correio [compartilhadas no Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="b91d7-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="b91d7-107">Anteriormente, a capacidade de os usuários gerenciarem mensagens em quarentena enviadas a uma caixa de correio compartilhada exigiam que os administradores deixem o automapeamento habilitado para a caixa de correio compartilhada (ele é habilitado por padrão quando um administrador dá a um usuário acesso a outra caixa de correio).</span><span class="sxs-lookup"><span data-stu-id="b91d7-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="b91d7-108">No entanto, dependendo do tamanho e do número de caixas de correio às  que o usuário tem acesso, o desempenho pode ser prejudicado à medida que o Outlook tenta abrir todas as caixas de correio às que o usuário tem acesso.</span><span class="sxs-lookup"><span data-stu-id="b91d7-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="b91d7-109">Por esse motivo, muitos administradores optam por [remover o autopping para caixas de correio compartilhadas.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="b91d7-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="b91d7-110">Agora, o automapeamento não é mais necessário para que os usuários gerenciem mensagens em quarentena que foram enviadas para caixas de correio compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="b91d7-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="b91d7-111">Funciona apenas.</span><span class="sxs-lookup"><span data-stu-id="b91d7-111">It just works.</span></span> <span data-ttu-id="b91d7-112">Há dois métodos diferentes para acessar mensagens em quarentena que foram enviadas para uma caixa de correio compartilhada:</span><span class="sxs-lookup"><span data-stu-id="b91d7-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="b91d7-113">Se o administrador tiver habilitado as notificações de spam do usuário final em políticas anti-spam, qualquer usuário que  tenha acesso às notificações de spam do usuário final na caixa de correio compartilhada poderá clicar no botão Revisão na notificação para ir para a quarentena no Centro de Conformidade e & Segurança. [](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b91d7-113">If the admin has [enabled end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="b91d7-114">Observe que esse método só permite que os usuários gerenciem mensagens em quarentena que foram enviadas para a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="b91d7-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="b91d7-115">Os usuários não podem gerenciar suas próprias mensagens de quarentena nesse contexto.</span><span class="sxs-lookup"><span data-stu-id="b91d7-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="b91d7-116">O usuário pode [ir para a quarentena no Centro de Conformidade & segurança.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="b91d7-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="b91d7-117">Por padrão, apenas as mensagens que foram enviadas para o usuário são mostradas.</span><span class="sxs-lookup"><span data-stu-id="b91d7-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="b91d7-118">No entanto, o usuário pode alterar os resultados de classificação (o botão **ID** da mensagem  por padrão) para o endereço de email do destinatário, insira o endereço de **email** da caixa de correio compartilhada e clique em Atualizar para ver as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. </span><span class="sxs-lookup"><span data-stu-id="b91d7-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Classificar mensagens em quarentena por endereço de email do destinatário.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="b91d7-120">Independentemente do método, os usuários podem evitar confusão incluindo a coluna **Destinatário** para mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b91d7-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="b91d7-121">O número máximo de colunas a exibir é 7, portanto, o usuário precisará clicar em Modificar **colunas,** remover  uma coluna existente (por **exemplo,** tipo de política ), **selecionar** Destinatário e clicar em Salvar ou Salvar como **padrão.**</span><span class="sxs-lookup"><span data-stu-id="b91d7-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Remova a coluna Tipo de Política e adicione a coluna Destinatário à quarentena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="b91d7-123">Tenha em mente</span><span class="sxs-lookup"><span data-stu-id="b91d7-123">Things to keep in mind</span></span>

- <span data-ttu-id="b91d7-124">O primeiro usuário a agir na mensagem em quarentena decide o nome da mensagem para todos que usam a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="b91d7-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="b91d7-125">Por exemplo, se uma caixa de correio compartilhada for acessada por 10 usuários e um usuário decidir excluir a mensagem de quarentena, a mensagem será excluída para todos os 10 usuários.</span><span class="sxs-lookup"><span data-stu-id="b91d7-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="b91d7-126">Da mesma forma, se um usuário decidir liberar a mensagem, ela será liberada para a caixa de correio compartilhada e poderá ser acessada por todos os outros usuários da caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="b91d7-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="b91d7-127">Atualmente, o **botão Bloquear** remetente não está disponível no flyout Detalhes para mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. </span><span class="sxs-lookup"><span data-stu-id="b91d7-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="b91d7-128">Para gerenciar mensagens em quarentena para a caixa de correio compartilhada no PowerShell do [Exchange Online,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)o usuário final precisará usar o cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) com o endereço de email da caixa de correio compartilhada para o valor do parâmetro _RecipientAddress_ para identificar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="b91d7-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="b91d7-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b91d7-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="b91d7-130">Em seguida, o usuário final pode selecionar uma mensagem em quarentena na lista para exibir ou tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="b91d7-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="b91d7-131">Este exemplo mostra todas as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada e, em seguida, libera a primeira mensagem da lista da quarentena (a primeira mensagem na lista é 0, a segunda é 1 e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="b91d7-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="b91d7-132">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b91d7-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="b91d7-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b91d7-133">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="b91d7-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="b91d7-134">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="b91d7-135">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b91d7-135">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="b91d7-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b91d7-136">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
