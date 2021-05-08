---
title: Configurar encaminhamento de email
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configurar o encaminhamento de email para uma ou mais contas de email usando o Office365.
ms.openlocfilehash: b5612a915fce21e9e9865fca6cb2275d8af17bd2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242403"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="dc03b-103">Configurar o encaminhamento de email em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc03b-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="dc03b-104">Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de email para a caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="dc03b-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="dc03b-105">O encaminhamento de email permite encaminhar mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="dc03b-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc03b-106">Você pode usar políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="dc03b-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="dc03b-107">Para obter mais informações, consulte [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="dc03b-107">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="dc03b-108">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="dc03b-108">Configure email forwarding</span></span>

<span data-ttu-id="dc03b-109">Antes de configurar o encaminhamento de email, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dc03b-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="dc03b-110">Depois de configurar o encaminhamento de email, somente **os** novos emails enviados para a caixa  *de*  correio da caixa de correio serão encaminhados.</span><span class="sxs-lookup"><span data-stu-id="dc03b-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="dc03b-111">O encaminhamento de email exige que  *a conta de*  a partir tenha uma licença.</span><span class="sxs-lookup"><span data-stu-id="dc03b-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="dc03b-112">Se você estiver configurando o encaminhamento de email porque o usuário deixou sua organização, outra opção é converter sua caixa de correio [em uma caixa de correio compartilhada.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="dc03b-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="dc03b-113">Dessa forma, várias pessoas podem acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="dc03b-113">This way several people can access it.</span></span> <span data-ttu-id="dc03b-114">No entanto, uma caixa de correio compartilhada não pode exceder 50 GB.</span><span class="sxs-lookup"><span data-stu-id="dc03b-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="dc03b-115">Você deve ser um administrador Exchange ou administrador global no Microsoft 365 para fazer essas etapas.</span><span class="sxs-lookup"><span data-stu-id="dc03b-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="dc03b-116">Para obter mais informações, consulte o tópico [Sobre funções de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dc03b-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="dc03b-117">No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="dc03b-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="dc03b-118">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="dc03b-118">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="dc03b-119">Na guia **Email,** selecione **Gerenciar encaminhamento de email**.</span><span class="sxs-lookup"><span data-stu-id="dc03b-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="dc03b-120">Na página de encaminhamento de email, selecione Encaminhar todos os **emails** enviados para essa caixa de correio, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="dc03b-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="dc03b-121">Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="dc03b-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="dc03b-122">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="dc03b-122">Select **Save changes**.</span></span>

    <span data-ttu-id="dc03b-123">**Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="dc03b-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="dc03b-124">Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="dc03b-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="dc03b-125">Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="dc03b-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="dc03b-126">Não exclua a conta do usuário que está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="dc03b-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="dc03b-127">Se você fizer isso, o encaminhamento de email será parado.</span><span class="sxs-lookup"><span data-stu-id="dc03b-127">If you do, email forwarding will stop.</span></span>