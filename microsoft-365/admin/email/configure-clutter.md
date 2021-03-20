---
title: Configurar o Clutter para sua organização
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Aprenda a habilitar ou desabilitar o recurso Clutter para todos ou usuários específicos em sua organização, usando o Exchange PowerShell. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915897"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="fdfd9-103">Configurar o Clutter para sua organização</span><span class="sxs-lookup"><span data-stu-id="fdfd9-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="fdfd9-104">[A Caixa de Entrada Focada](../setup/configure-focused-inbox.md) substituirá o Clutter.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="fdfd9-105">Saiba mais: [Atualizar a Caixa de Entrada Focada e nossos planos para o Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="fdfd9-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="fdfd9-106">Como administrador, talvez seja preciso gerenciar o recurso Clutter no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="fdfd9-107">Para ativar/desativar o recurso Clutter para usuários em sua organização, você deve usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="fdfd9-108">(Os indivíduos podem a turn-lo/off usando estas instruções: [Desativar/ativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="fdfd9-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="fdfd9-109">Confira Usando [o PowerShell com o Exchange Online e](/powershell/exchange/exchange-online-powershell) [Conecte-se ao PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online para obter detalhes sobre como usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="fdfd9-110">Você precisa ter uma conta que tenha pelo menos a função de administrador do Exchange Service e a capacidade de se conectar ao Exchange Online com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="fdfd9-111">Ativar o Clutter usando o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdfd9-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="fdfd9-112">Você pode habilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter)</span><span class="sxs-lookup"><span data-stu-id="fdfd9-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="fdfd9-113">Você também pode exibir as configurações do Clutter para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter)</span><span class="sxs-lookup"><span data-stu-id="fdfd9-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="fdfd9-114">Ativar o Clutter para um único usuário chamado Allie Bellew</span><span class="sxs-lookup"><span data-stu-id="fdfd9-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="fdfd9-115">Desativar o Clutter usando o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdfd9-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="fdfd9-116">Você pode desabilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter)</span><span class="sxs-lookup"><span data-stu-id="fdfd9-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="fdfd9-117">Você também pode exibir **as configurações do Clutter** para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter)</span><span class="sxs-lookup"><span data-stu-id="fdfd9-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="fdfd9-118">Desativar o Clutter para um único usuário chamado Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="fdfd9-119">Se você usar o PowerShell para criar seus usuários em massa, precisará executar [Set-Clutter](/powershell/module/exchange/set-clutter) na caixa de correio de cada usuário para gerenciar o Clutter.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="fdfd9-120">Quando a opção Clutter on/off aparece para os usuários no Outlook na Web?</span><span class="sxs-lookup"><span data-stu-id="fdfd9-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="fdfd9-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="fdfd9-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="fdfd9-122">Como administrador, você pode habilitar o Clutter usando o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="fdfd9-123">Depois que isso for feito, a Caixa de Entrada Focalizada será desligada e o Clutter estará ativo novamente.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="fdfd9-124">**Se você estiver usando o Outlook na Web com uma assinatura do Microsoft 365 Business Premium:**</span><span class="sxs-lookup"><span data-stu-id="fdfd9-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="fdfd9-125">Se o usuário tiver Atualmente o Clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="fdfd9-126">As configurações de clutter são exibidas</span><span class="sxs-lookup"><span data-stu-id="fdfd9-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="fdfd9-127">Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="fdfd9-128">As configurações de clutter não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="fdfd9-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="fdfd9-129">Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="fdfd9-130">Tanto o Clutter quanto a Caixa de Entrada Focalizada aparecem como opções nas Configurações de Email do usuário</span><span class="sxs-lookup"><span data-stu-id="fdfd9-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="fdfd9-131">**Se você estiver usando Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="fdfd9-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="fdfd9-132">Se o usuário tiver Atualmente o Clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="fdfd9-133">As configurações de clutter são exibidas</span><span class="sxs-lookup"><span data-stu-id="fdfd9-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="fdfd9-134">Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="fdfd9-135">As configurações de clutter não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="fdfd9-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="fdfd9-136">Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="fdfd9-137">Tanto o Clutter quanto a Caixa de Entrada Focalizada aparecem como opções nas Configurações de Email do usuário</span><span class="sxs-lookup"><span data-stu-id="fdfd9-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="fdfd9-138">Se o usuário habilitar a Caixa de Entrada Focada em algum ponto do passado:</span><span class="sxs-lookup"><span data-stu-id="fdfd9-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="fdfd9-139">As configurações de clutter nunca serão exibidas</span><span class="sxs-lookup"><span data-stu-id="fdfd9-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="fdfd9-140">Caso contrário,</span><span class="sxs-lookup"><span data-stu-id="fdfd9-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="fdfd9-141">As configurações de clutter serão exibidas</span><span class="sxs-lookup"><span data-stu-id="fdfd9-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="fdfd9-142">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="fdfd9-142">Related articles</span></span>
<span data-ttu-id="fdfd9-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="fdfd9-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="fdfd9-144">Usar o Clutter para classificar mensagens de baixa prioridade no Outlook</span><span class="sxs-lookup"><span data-stu-id="fdfd9-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="fdfd9-145">Usar o Clutter para classificar mensagens de baixa prioridade no OWA</span><span class="sxs-lookup"><span data-stu-id="fdfd9-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="fdfd9-146">Desativar o Clutter no Outlook</span><span class="sxs-lookup"><span data-stu-id="fdfd9-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
