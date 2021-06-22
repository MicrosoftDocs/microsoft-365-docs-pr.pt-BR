---
title: Etapa 1 - Impedir que um funcionário entre no Microsoft 365
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
description: Impedir que um ex-funcionário entre e bloqueie o acesso aos Microsoft 365 serviços.
ms.openlocfilehash: f2258b165c3d61f809288003f4a536ffe160ea59
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061829"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="2147f-103">Etapa 1 - Impedir que um ex-funcionário entre e bloqueie o acesso aos serviços Microsoft 365 serviços</span><span class="sxs-lookup"><span data-stu-id="2147f-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="2147f-104">Se você precisar impedir imediatamente o acesso de entrada de um usuário, você deve redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="2147f-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="2147f-105">Nesta etapa, force uma saída do usuário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2147f-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="2147f-106">Você precisa ser um administrador global para iniciar a saída para outros administradores.</span><span class="sxs-lookup"><span data-stu-id="2147f-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="2147f-107">Para usuários que não são administradores, você pode usar um Administrador de Usuário ou um usuário do Administrador do Helpdesk para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="2147f-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="2147f-108">Saiba mais sobre as Funções de Administrador</span><span class="sxs-lookup"><span data-stu-id="2147f-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="2147f-109">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="2147f-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="2147f-110">Selecione a caixa ao lado do nome do usuário e selecione **Redefinir senha**.</span><span class="sxs-lookup"><span data-stu-id="2147f-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="2147f-111">Insira uma nova senha e selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="2147f-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="2147f-112">(Não envie para eles.)</span><span class="sxs-lookup"><span data-stu-id="2147f-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="2147f-113">Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Sair de todas as sessões**.</span><span class="sxs-lookup"><span data-stu-id="2147f-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Sign out of all sessions**.</span></span>

<span data-ttu-id="2147f-114">Dentro de uma hora - ou depois de sair da página Microsoft 365 atual em que estão - eles são solicitados a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="2147f-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="2147f-115">Um token de acesso é bom para uma hora, portanto, a linha do tempo depende de quanto tempo resta nesse token e se eles navegam para fora de sua página da Web atual.</span><span class="sxs-lookup"><span data-stu-id="2147f-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2147f-116">Se o usuário estiver em Outlook na Web, basta clicar em sua caixa de correio, ele pode não ser colocado para fora imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2147f-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="2147f-117">Assim que eles selecionam um OneDrive, ou atualizem o navegador, a saída é iniciada.</span><span class="sxs-lookup"><span data-stu-id="2147f-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="2147f-118">Para usar o PowerShell para sair imediatamente de um usuário, consulte o cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="2147f-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="2147f-119">Para saber mais sobre quanto tempo é preciso para excluir alguém do email, confira [O que você precisa saber sobre o encerramento da sessão de email de um funcionário](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="2147f-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="2147f-120">Bloquear o acesso de um ex-funcionário a serviços Microsoft 365 serviços</span><span class="sxs-lookup"><span data-stu-id="2147f-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="2147f-121">O bloqueio de uma conta pode levar até 24 horas para ter efeito.</span><span class="sxs-lookup"><span data-stu-id="2147f-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="2147f-122">Se você precisar impedir imediatamente o acesso de entrada de um usuário, siga as etapas acima e redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="2147f-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="2147f-123">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="2147f-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="2147f-124">Selecione o nome do funcionário que você deseja bloquear e, sob o nome do usuário, selecione o símbolo para **Bloquear este usuário**.</span><span class="sxs-lookup"><span data-stu-id="2147f-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="2147f-125">Selecione **Bloquear o usuário de entrar** e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2147f-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="2147f-126">Bloquear o acesso de um ex-funcionário ao email (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="2147f-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="2147f-127">Se você tiver emails como parte da sua assinatura Microsoft 365, entre no centro de administração Exchange e siga estas etapas para impedir que seu ex-funcionário acesse seus emails.</span><span class="sxs-lookup"><span data-stu-id="2147f-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="2147f-128">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="2147f-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="2147f-129">No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**.</span><span class="sxs-lookup"><span data-stu-id="2147f-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="2147f-130">Clique duas vezes no usuário e vá para a página **Recursos de Caixa de** Correio.</span><span class="sxs-lookup"><span data-stu-id="2147f-130">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="2147f-131">Em **Dispositivos Móveis,** selecione **Desabilitar Exchange ActiveSync** e **Desabilitar o OWA para** Dispositivos e responda **Sim** a ambos quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="2147f-131">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="2147f-132">Em **Conectividade de Email,** selecione **Desabilitar** e responder **Sim** quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="2147f-132">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
