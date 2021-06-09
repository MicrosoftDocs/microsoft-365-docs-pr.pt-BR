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
description: 'Aprenda a habilitar ou desabilitar o recurso Clutter para todos ou usuários específicos em sua organização, usando Exchange PowerShell. '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706101"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="eeec2-103">Configurar o Clutter para sua organização</span><span class="sxs-lookup"><span data-stu-id="eeec2-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="eeec2-104">[A Caixa de Entrada Focada](../setup/configure-focused-inbox.md) substituirá o Clutter.</span><span class="sxs-lookup"><span data-stu-id="eeec2-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="eeec2-105">Saiba mais: [Atualizar a Caixa de Entrada Focada e nossos planos para o Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="eeec2-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="eeec2-106">Como administrador, talvez seja preciso gerenciar o recurso Clutter no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eeec2-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="eeec2-107">Para ativar/desativar o recurso Clutter para usuários em sua organização, você deve usar Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeec2-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="eeec2-108">(Os indivíduos podem a turn-lo/off usando estas instruções: [Desativar/ativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="eeec2-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="eeec2-109">Confira Usando [o PowerShell com Exchange Online](/powershell/exchange/exchange-online-powershell) e Conexão para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obter detalhes sobre como usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeec2-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="eeec2-110">Você precisa ter uma conta que tenha pelo menos a função de administrador do serviço Exchange e a capacidade de se conectar ao Exchange Online com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeec2-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="eeec2-111">Ativar o Clutter usando Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="eeec2-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="eeec2-112">Você pode habilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter)</span><span class="sxs-lookup"><span data-stu-id="eeec2-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="eeec2-113">Você também pode exibir as configurações do Clutter para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter)</span><span class="sxs-lookup"><span data-stu-id="eeec2-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="eeec2-114">Ativar o Clutter para um único usuário chamado Allie Bellew</span><span class="sxs-lookup"><span data-stu-id="eeec2-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="eeec2-115">Desativar o Clutter usando Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="eeec2-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="eeec2-116">Você pode desabilitar o Clutter manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter)</span><span class="sxs-lookup"><span data-stu-id="eeec2-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="eeec2-117">Você também pode exibir **as configurações do Clutter** para caixas de correio em sua organização executando o cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter)</span><span class="sxs-lookup"><span data-stu-id="eeec2-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="eeec2-118">Desativar o Clutter para um único usuário chamado Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="eeec2-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="eeec2-119">Se você usar o PowerShell para criar seus usuários em massa, precisará executar [Set-Clutter](/powershell/module/exchange/set-clutter) na caixa de correio de cada usuário para gerenciar o Clutter.</span><span class="sxs-lookup"><span data-stu-id="eeec2-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="eeec2-120">Quando a opção Clutter on/off aparece para os usuários Outlook na Web?</span><span class="sxs-lookup"><span data-stu-id="eeec2-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="eeec2-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="eeec2-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="eeec2-122">Como administrador, você pode habilitar o Clutter usando Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeec2-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="eeec2-123">Depois que isso for feito, a Caixa de Entrada Focalizada será desligada e o Clutter estará ativo novamente.</span><span class="sxs-lookup"><span data-stu-id="eeec2-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="eeec2-124">**Se você estiver usando Outlook na Web com uma assinatura Microsoft 365 Business Premium:**</span><span class="sxs-lookup"><span data-stu-id="eeec2-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="eeec2-125">Se o usuário tiver Atualmente o Clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="eeec2-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="eeec2-126">As configurações de clutter são exibidas</span><span class="sxs-lookup"><span data-stu-id="eeec2-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="eeec2-127">Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada:</span><span class="sxs-lookup"><span data-stu-id="eeec2-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="eeec2-128">As configurações de clutter não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="eeec2-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="eeec2-129">Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="eeec2-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="eeec2-130">Tanto o Clutter quanto a Caixa de Entrada Focada aparecem como opções na caixa de correio do usuário Configurações</span><span class="sxs-lookup"><span data-stu-id="eeec2-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="eeec2-131">**Se você estiver usando Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="eeec2-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="eeec2-132">Se o usuário tiver Atualmente o Clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="eeec2-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="eeec2-133">As configurações de clutter são exibidas</span><span class="sxs-lookup"><span data-stu-id="eeec2-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="eeec2-134">Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada:</span><span class="sxs-lookup"><span data-stu-id="eeec2-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="eeec2-135">As configurações de clutter não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="eeec2-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="eeec2-136">Se o Clutter ou a Caixa de Entrada Focalizada não estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="eeec2-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="eeec2-137">Tanto o Clutter quanto a Caixa de Entrada Focada aparecem como opções na caixa de correio do usuário Configurações</span><span class="sxs-lookup"><span data-stu-id="eeec2-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="eeec2-138">Se o usuário habilitar a Caixa de Entrada Focada em algum ponto do passado:</span><span class="sxs-lookup"><span data-stu-id="eeec2-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="eeec2-139">As configurações de clutter nunca serão exibidas</span><span class="sxs-lookup"><span data-stu-id="eeec2-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="eeec2-140">Caso contrário,</span><span class="sxs-lookup"><span data-stu-id="eeec2-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="eeec2-141">As configurações de clutter serão exibidas</span><span class="sxs-lookup"><span data-stu-id="eeec2-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="eeec2-142">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="eeec2-142">Related content</span></span>

<span data-ttu-id="eeec2-143">[Use o Clutter para classificar mensagens de baixa prioridade Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (artigo)</span><span class="sxs-lookup"><span data-stu-id="eeec2-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="eeec2-144">[Use o Clutter para classificar mensagens de baixa prioridade no OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artigo)</span><span class="sxs-lookup"><span data-stu-id="eeec2-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)</span></span>\
<span data-ttu-id="eeec2-145">[Desativar o Clutter no Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artigo)</span><span class="sxs-lookup"><span data-stu-id="eeec2-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>
