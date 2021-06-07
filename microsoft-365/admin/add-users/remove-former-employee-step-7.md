---
title: Etapa 7 - Excluir a conta de usuário de um ex-funcionário
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
description: Siga estas etapas para excluir a conta de usuário de um ex-funcionário.
ms.openlocfilehash: e9f87f68650394a81c735346db929bf592e91d18
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779826"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="868ed-103">Etapa 7 - Excluir a conta de usuário de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="868ed-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="868ed-104">Depois de salvar e acessar todos os dados de usuário do ex-funcionário, você pode excluir a conta do ex-funcionário.</span><span class="sxs-lookup"><span data-stu-id="868ed-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="868ed-p101">Não exclua a conta se tiver configurado o encaminhamento de email ou se tiver convertido essa conta em uma caixa de correio compartilhada. Ambos precisam da conta para ancorar o encaminhamento ou a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="868ed-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="868ed-107">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="868ed-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="868ed-108">Selecione o nome do funcionário que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="868ed-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="868ed-109">Em nome do usuário, selecione **Excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="868ed-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="868ed-110">Escolha as opções que você deseja para esse usuário e selecione **Excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="868ed-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="868ed-111">Se você já tiver dado a outro usuário acesso ao email e ao OneDrive desse usuário, não será preciso fazer isso novamente aqui.</span><span class="sxs-lookup"><span data-stu-id="868ed-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="868ed-p103">Quando você exclui um usuário, a conta se torna inativa por aproximadamente 30 dias. Você tem até esse prazo para restaurar a conta antes de ela ser permanentemente excluída.</span><span class="sxs-lookup"><span data-stu-id="868ed-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>

## <a name="watch-delete-a-former-employees-user-account"></a><span data-ttu-id="868ed-114">Assista: Excluir a conta de usuário de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="868ed-114">Watch: Delete a former employee's user account</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

<span data-ttu-id="868ed-115">Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="868ed-115">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="868ed-116">Sua organização usa o Active Directory?</span><span class="sxs-lookup"><span data-stu-id="868ed-116">Does your organization use Active Directory?</span></span>

<span data-ttu-id="868ed-117">Se sua organização sincroniza contas de usuário Microsoft 365 de um ambiente local do Active Directory, você deve excluir e restaurar essas contas de usuário no serviço local do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="868ed-117">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="868ed-118">Não é possível excluí-las ou restaurá-las no Office 365.</span><span class="sxs-lookup"><span data-stu-id="868ed-118">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="868ed-119">Para saber como excluir e restaurar a conta de usuário no Active Directory, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="868ed-119">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="868ed-120">Se você estiver usando Azure Active Directory, consulte o cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="868ed-120">If you're using Azure Active Directory, see the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="868ed-121">O que você precisa saber sobre o encerramento da sessão de email de um funcionário</span><span class="sxs-lookup"><span data-stu-id="868ed-121">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="868ed-122">Aqui estão as informações sobre como excluir um funcionário do email (Exchange).</span><span class="sxs-lookup"><span data-stu-id="868ed-122">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="868ed-123">**O que você pode fazer**</span><span class="sxs-lookup"><span data-stu-id="868ed-123">**What you can do**</span></span> <br/> |<span data-ttu-id="868ed-124">**Como fazer isso**</span><span class="sxs-lookup"><span data-stu-id="868ed-124">**How you do it**</span></span> <br/> |
|<span data-ttu-id="868ed-125">Encerrar uma sessão (como o Outlook na Web, Outlook, Exchange Active Sync, etc.) e forçar a abertura de uma nova sessão</span><span class="sxs-lookup"><span data-stu-id="868ed-125">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="868ed-126">Redefina a senha</span><span class="sxs-lookup"><span data-stu-id="868ed-126">Reset password</span></span>  <br/> |
|<span data-ttu-id="868ed-127">Encerrar uma sessão e bloquear o acesso a sessões futuras (para todos os protocolos)</span><span class="sxs-lookup"><span data-stu-id="868ed-127">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="868ed-128">Desabilite a conta.</span><span class="sxs-lookup"><span data-stu-id="868ed-128">Disable the account.</span></span> <span data-ttu-id="868ed-129">Por exemplo, (no centro de administração Exchange ou usando o PowerShell):</span><span class="sxs-lookup"><span data-stu-id="868ed-129">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="868ed-130">Encerrar a sessão de um protocolo específico (como ActiveSync)</span><span class="sxs-lookup"><span data-stu-id="868ed-130">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="868ed-131">Desabilite o protocolo.</span><span class="sxs-lookup"><span data-stu-id="868ed-131">Disable the protocol.</span></span> <span data-ttu-id="868ed-132">Por exemplo, (no centro de administração Exchange ou usando o PowerShell):</span><span class="sxs-lookup"><span data-stu-id="868ed-132">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="868ed-133">As operações acima podem ser feitas em três locais:</span><span class="sxs-lookup"><span data-stu-id="868ed-133">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="868ed-134">**Se você encerrar a sessão aqui**</span><span class="sxs-lookup"><span data-stu-id="868ed-134">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="868ed-135">**Quanto tempo demora**</span><span class="sxs-lookup"><span data-stu-id="868ed-135">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="868ed-136">No centro de administração do Exchange ou usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="868ed-136">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="868ed-137">O atraso esperado é de 30 minutos</span><span class="sxs-lookup"><span data-stu-id="868ed-137">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="868ed-138">No centro de administração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="868ed-138">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="868ed-139">O atraso esperado é de 60 minutos</span><span class="sxs-lookup"><span data-stu-id="868ed-139">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="868ed-140">Em um ambiente local</span><span class="sxs-lookup"><span data-stu-id="868ed-140">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="868ed-141">O atraso esperado é de três horas ou mais</span><span class="sxs-lookup"><span data-stu-id="868ed-141">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="868ed-142">Como obter a resposta mais rapidamente para o encerramento da conta</span><span class="sxs-lookup"><span data-stu-id="868ed-142">How to get fastest response for account termination</span></span>

 <span data-ttu-id="868ed-p107">**Mais rápido**: use o centro de administração do Exchange (use o PowerShell) ou o centro de administração do Azure Active Directory. Em um ambiente local, pode demorar várias horas para sincronizar a alteração por meio do DirSync.</span><span class="sxs-lookup"><span data-stu-id="868ed-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="868ed-p108">**O mais rápido para um usuário com presença local e no Datacenter do Exchange**: Encerre a sessão usando o centro de administração do Azure Active Directory/centro de administração do Exchange e altere TAMBÉM no ambiente local. Caso contrário, a alteração no centro de administração do Azure Active Directory/centro de administração do Exchange será substituída pelo DirSync.</span><span class="sxs-lookup"><span data-stu-id="868ed-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="868ed-147">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="868ed-147">Related articles</span></span>

[<span data-ttu-id="868ed-148">Restaurar um usuário</span><span class="sxs-lookup"><span data-stu-id="868ed-148">Restore a user</span></span>](restore-user.md)

[<span data-ttu-id="868ed-149">Redefinir senhas</span><span class="sxs-lookup"><span data-stu-id="868ed-149">Reset passwords</span></span>](reset-passwords.md)
