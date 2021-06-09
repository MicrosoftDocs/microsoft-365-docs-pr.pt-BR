---
title: Etapa 3 - Encaminhar o email de um ex-funcionário para outro funcionário ou converter em uma caixa de correio compartilhada
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga estas etapas para encaminhar o email de um ex-funcionário para outro funcionário ou convertê-lo em uma caixa de correio compartilhada.
ms.openlocfilehash: 5ab66cf9d71a597a7f33c9a5e3a180738592faca
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244155"
---
# <a name="step-3---forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a><span data-ttu-id="f88e3-103">Etapa 3 - Encaminhar o email de um ex-funcionário para outro funcionário ou converter em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="f88e3-103">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>

<span data-ttu-id="f88e3-104">Nesta etapa, você atribui o endereço de email do ex-funcionário a outro funcionário ou converte a caixa de correio do usuário em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="f88e3-104">In this step, you assign the former employee's email address to another employee, or convert the user's mailbox to a shared mailbox.</span></span>

## <a name="convert-former-employees-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="f88e3-105">Converter a caixa de correio do ex-funcionário em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="f88e3-105">Convert former employee's mailbox to a shared mailbox</span></span>

<span data-ttu-id="f88e3-106">Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todo o email e calendário existentes são mantidos.</span><span class="sxs-lookup"><span data-stu-id="f88e3-106">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="f88e3-107">Somente agora ele está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="f88e3-107">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="f88e3-108">Você pode converter uma caixa de correio compartilhada de volta para uma caixa de correio de usuário (privada) em uma data posterior, se quiser.</span><span class="sxs-lookup"><span data-stu-id="f88e3-108">You can convert a shared mailbox back to a user (private) mailbox at a later date if you want.</span></span>

- <span data-ttu-id="f88e3-p102">Criar uma caixa de correio compartilhada é a maneira mais econômica, pois assim não é necessário pagar por uma licença, **desde que a caixa de correio tenha menos de 50 GB**. Para caixas de correio acima de 50 GB, é necessário atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="f88e3-p102">Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it.</span></span>
- <span data-ttu-id="f88e3-p103">Se você converter a caixa de correio em uma caixa de correio compartilhada, todos os emails antigos ficarão disponíveis também. Isso pode ocupar muito espaço.</span><span class="sxs-lookup"><span data-stu-id="f88e3-p103">If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.</span></span>
- <span data-ttu-id="f88e3-113">Se você configurar o encaminhamento de email, apenas *novos* emails enviados para o ex-funcionário serão enviados para o funcionário atual.</span><span class="sxs-lookup"><span data-stu-id="f88e3-113">If you set up email forwarding, only *new* emails sent to the former employee will now be sent to the current employee.</span></span>

<span data-ttu-id="f88e3-114">Siga estas etapas sobre como converter a caixa de correio do usuário [em uma caixa de correio compartilhada.](../email/convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f88e3-114">Follow these steps on how to [convert the user's mailbox to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md).</span></span>

## <a name="forward-a-former-employees-email-to-another-employee"></a><span data-ttu-id="f88e3-115">Encaminhar o email de um ex-funcionário para outro funcionário</span><span class="sxs-lookup"><span data-stu-id="f88e3-115">Forward a former employee's email to another employee</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="f88e3-116">Se você estiver configurando o encaminhamento de email ou uma caixa de correio compartilhada, no final, não exclua a conta do ex-funcionário.</span><span class="sxs-lookup"><span data-stu-id="f88e3-116">If you're setting up email forwarding or a shared mailbox, at the end, don't delete the former employee's account.</span></span> <span data-ttu-id="f88e3-117">Ela deve existir para ancorar o encaminhamento de email ou a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="f88e3-117">The account needs to be there to anchor the email forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="f88e3-118">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="f88e3-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f88e3-119">Selecione o nome do funcionário que você deseja bloquear e selecione a **guia Email.**</span><span class="sxs-lookup"><span data-stu-id="f88e3-119">Select the name of the employee that you want to block, and then select the **Mail** tab.</span></span>
3. <span data-ttu-id="f88e3-120">Em **Encaminhamento de Email,** selecione **Gerenciar encaminhamento de email.**</span><span class="sxs-lookup"><span data-stu-id="f88e3-120">Under **Email Forwarding**, select **Manage email forwarding**.</span></span>
4. <span data-ttu-id="f88e3-121">Ative **Encaminhar todos os emails enviados para esta caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="f88e3-121">Turn on **Forward all email sent to this mailbox**.</span></span> <span data-ttu-id="f88e3-122">Na caixa **Endereço de encaminhamento,** digite o endereço de email do funcionário atual que vai receber o email.</span><span class="sxs-lookup"><span data-stu-id="f88e3-122">In the **Forwarding address** box, type the email address of the current employee who's going to get the email.</span></span>
5. <span data-ttu-id="f88e3-123">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f88e3-123">Select **Save**.</span></span>
6. <span data-ttu-id="f88e3-124">Lembre-se de não excluir a conta do ex-funcionário.</span><span class="sxs-lookup"><span data-stu-id="f88e3-124">Remember, don't delete the former employee's account.</span></span>
