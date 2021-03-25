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
description: Os usuários podem aprender a exibir e agir em mensagens em quarentena enviadas a caixas de correio compartilhadas às quais eles têm permissões.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e3bf4c84e7a762f7f54f42ff61f0fbdb9dc1edd
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215499"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="c0ed6-103">Exibir e liberar mensagens em quarentena de caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="c0ed6-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="c0ed6-104">Os recursos descritos neste artigo estão atualmente em Visualização, não estão disponíveis para todos e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="c0ed6-105">Os usuários podem gerenciar mensagens em quarentena em que são um dos destinatários, conforme descrito em [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c0ed6-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="c0ed6-106">Mas e as caixas de correio compartilhadas em que o usuário tem permissões de Acesso Total e Enviar como ou Enviar em Nome para a caixa de correio, conforme descrito em Caixas de correio [compartilhadas no Exchange Online?](/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="c0ed6-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="c0ed6-107">Anteriormente, a capacidade dos usuários de gerenciar mensagens em quarentena enviadas a uma caixa de correio compartilhada exigia que os administradores deixassem a automação habilitada para a caixa de correio compartilhada (ela é habilitada por padrão quando um administrador dá acesso ao usuário a outra caixa de correio).</span><span class="sxs-lookup"><span data-stu-id="c0ed6-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="c0ed6-108">No entanto, dependendo do tamanho e do número de caixas de correio às  que o usuário tem acesso, o desempenho pode sofrer à medida que o Outlook tenta abrir todas as caixas de correio às que o usuário tem acesso.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="c0ed6-109">Por esse motivo, muitos administradores optam por [remover o automapping para caixas de correio compartilhadas.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="c0ed6-109">For this reason, many admins choose to [remove automapping for shared mailboxes](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="c0ed6-110">Agora, a automação não é mais necessária para que os usuários gerenciem mensagens em quarentena enviadas para caixas de correio compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="c0ed6-111">Ele só funciona.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-111">It just works.</span></span> <span data-ttu-id="c0ed6-112">Há dois métodos diferentes para acessar mensagens em quarentena enviadas a uma caixa de correio compartilhada:</span><span class="sxs-lookup"><span data-stu-id="c0ed6-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="c0ed6-113">Se o administrador habilitar notificações de spam do usuário [final](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) em políticas anti-spam, qualquer usuário que tenha  acesso às notificações de & spam do usuário final na caixa de correio compartilhada poderá clicar no botão Revisar na notificação para ir para a quarentena no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="c0ed6-114">Observe que esse método só permite que os usuários gerenciem mensagens em quarentena enviadas para a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="c0ed6-115">Os usuários não podem gerenciar suas próprias mensagens de quarentena neste contexto.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="c0ed6-116">O usuário pode [ir para a quarentena no Centro de Conformidade & Segurança.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="c0ed6-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="c0ed6-117">Por padrão, apenas as mensagens enviadas ao usuário são mostradas.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="c0ed6-118">No entanto, o usuário pode alterar os resultados de classificação (o botão **ID** da mensagem  por padrão) para o endereço de **email** do destinatário, inserir o endereço de email da caixa de correio compartilhada e clicar em Atualizar para ver as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. </span><span class="sxs-lookup"><span data-stu-id="c0ed6-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Classificação de mensagens em quarentena por endereço de email do destinatário.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="c0ed6-120">Independentemente do método, os usuários podem evitar confusão incluindo a **coluna Destinatário** para mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="c0ed6-121">O número máximo de colunas a ser exibido é 7, portanto, o usuário precisará clicar em Modificar **colunas,** remover uma coluna existente (por **exemplo,** tipo de política ), selecionar **Destinatário** e clicar em **Salvar** ou Salvar como **padrão**.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Remova a coluna Tipo de Política e adicione a coluna Destinatário à quarentena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="c0ed6-123">Tenha em mente</span><span class="sxs-lookup"><span data-stu-id="c0ed6-123">Things to keep in mind</span></span>

- <span data-ttu-id="c0ed6-124">O primeiro usuário a agir na mensagem em quarentena decide o destino da mensagem para todos que usam a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="c0ed6-125">Por exemplo, se uma caixa de correio compartilhada for acessada por 10 usuários e um usuário decidir excluir a mensagem de quarentena, a mensagem será excluída para todos os 10 usuários.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="c0ed6-126">Da mesma forma, se um usuário decidir liberar a mensagem, ela será liberada para a caixa de correio compartilhada e será acessível por todos os outros usuários da caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="c0ed6-127">Atualmente, o **botão Bloquear remetente** não está disponível no sobremenu **de** Detalhes para mensagens em quarentena enviadas à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="c0ed6-128">Em relação às operações de quarentena para caixas de correio compartilhadas, se você usar grupos de segurança aninhados para conceder acesso a uma caixa de correio compartilhada, recomendamos não mais do que dois níveis de grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-128">Regarding quarantine operations for shared mailboxes, if you use nested security groups to grant access to a shared mailbox, we recommend no more than two levels of nested groups.</span></span> <span data-ttu-id="c0ed6-129">Por exemplo, o Grupo A é membro do Grupo B, que é membro do Grupo C. Para atribuir permissões a uma caixa de correio compartilhada, não adicione o usuário ao Grupo A e atribua o Grupo C à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-129">For example, Group A is a member of Group B, which is a member of Group C. To assign permissions to a shared mailbox, don't add the user to Group A and then assign Group C to the shared mailbox.</span></span>  

- <span data-ttu-id="c0ed6-130">Para gerenciar mensagens em quarentena para a caixa de correio compartilhada no PowerShell do [Exchange Online,](/powershell/exchange/connect-to-exchange-online-powershell)o usuário final precisará usar o cmdlet [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) com o endereço de email de caixa de correio compartilhado para o valor do parâmetro _RecipientAddress_ para identificar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-130">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="c0ed6-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c0ed6-131">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="c0ed6-132">Em seguida, o usuário final pode selecionar uma mensagem em quarentena na lista para exibir ou tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="c0ed6-132">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="c0ed6-133">Este exemplo mostra todas as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada e, em seguida, libera a primeira mensagem na lista de quarentena (a primeira mensagem na lista é 0, a segunda é 1 e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="c0ed6-133">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="c0ed6-134">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c0ed6-134">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="c0ed6-135">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c0ed6-135">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="c0ed6-136">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="c0ed6-136">Get-QuarantineMessageHeader</span></span>](/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="c0ed6-137">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c0ed6-137">Preview-QuarantineMessage</span></span>](/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="c0ed6-138">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c0ed6-138">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
