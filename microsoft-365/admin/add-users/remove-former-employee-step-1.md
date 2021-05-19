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
ms.openlocfilehash: 8eb41c3b449e63284371aaf168262307a4c21941
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535945"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="4de93-103">Etapa 1 - Impedir que um ex-funcionário entre e bloqueie o acesso aos serviços Microsoft 365 serviços</span><span class="sxs-lookup"><span data-stu-id="4de93-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="4de93-104">Se você precisar impedir imediatamente o acesso de entrada de um usuário, você deve redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="4de93-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="4de93-105">Nesta etapa, force uma saída do usuário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4de93-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="4de93-106">Você precisa ser um administrador global para iniciar a saída.</span><span class="sxs-lookup"><span data-stu-id="4de93-106">You need to be a global administrator to initiate sign-out.</span></span>

1. <span data-ttu-id="4de93-107">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="4de93-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4de93-108">Selecione a caixa ao lado do nome do usuário e selecione **Redefinir senha**.</span><span class="sxs-lookup"><span data-stu-id="4de93-108">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="4de93-109">Insira uma nova senha e selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="4de93-109">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="4de93-110">(Não envie para eles.)</span><span class="sxs-lookup"><span data-stu-id="4de93-110">(Don't send it to them.)</span></span>
4. <span data-ttu-id="4de93-111">Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Iniciar saída**.</span><span class="sxs-lookup"><span data-stu-id="4de93-111">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="4de93-112">Dentro de uma hora - ou depois de sair da página Microsoft 365 atual em que estão - eles são solicitados a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="4de93-112">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="4de93-113">Um token de acesso é bom para uma hora, portanto, a linha do tempo depende de quanto tempo resta nesse token e se eles navegam para fora de sua página da Web atual.</span><span class="sxs-lookup"><span data-stu-id="4de93-113">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4de93-114">Se o usuário estiver Outlook na Web, basta clicar em sua caixa de correio, ele pode não ser colocado para fora imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4de93-114">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="4de93-115">Assim que eles selecionam um OneDrive, ou atualizem o navegador, a saída é iniciada.</span><span class="sxs-lookup"><span data-stu-id="4de93-115">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="4de93-116">Para usar o PowerShell para sair imediatamente de um usuário, consulte o cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="4de93-116">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="4de93-117">Para saber mais sobre quanto tempo é preciso para excluir alguém do email, confira [O que você precisa saber sobre o encerramento da sessão de email de um funcionário](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="4de93-117">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="4de93-118">Bloquear o acesso de um ex-funcionário a serviços Microsoft 365 serviços</span><span class="sxs-lookup"><span data-stu-id="4de93-118">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="4de93-119">O bloqueio de uma conta pode levar até 24 horas para ter efeito.</span><span class="sxs-lookup"><span data-stu-id="4de93-119">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="4de93-120">Se você precisar impedir imediatamente o acesso de entrada de um usuário, siga as etapas acima e redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="4de93-120">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="4de93-121">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="4de93-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4de93-122">Selecione o nome do funcionário que você deseja bloquear e, sob o nome do usuário, selecione o símbolo para **Bloquear este usuário**.</span><span class="sxs-lookup"><span data-stu-id="4de93-122">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="4de93-123">Selecione **Bloquear o usuário de entrar** e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4de93-123">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="4de93-124">Bloquear o acesso de um ex-funcionário ao email (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="4de93-124">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="4de93-125">Se você tiver emails como parte da sua assinatura Microsoft 365, entre no centro de administração Exchange e siga estas etapas para impedir que seu ex-funcionário acesse seus emails.</span><span class="sxs-lookup"><span data-stu-id="4de93-125">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="4de93-126">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="4de93-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="4de93-127">No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**.</span><span class="sxs-lookup"><span data-stu-id="4de93-127">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="4de93-128">Clique duas vezes no usuário e vá para a página **Recursos de Caixa de** Correio.</span><span class="sxs-lookup"><span data-stu-id="4de93-128">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="4de93-129">Em **Dispositivos Móveis,** selecione **Desabilitar Exchange ActiveSync** e **Desabilitar o OWA para** Dispositivos e responda **Sim** a ambos quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="4de93-129">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="4de93-130">Em **Conectividade de Email,** selecione **Desabilitar** e responder **Sim** quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="4de93-130">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
