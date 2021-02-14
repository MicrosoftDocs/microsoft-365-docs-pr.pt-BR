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
description: 'Saiba como habilitar ou desabilitar o recurso Desorganização para todos ou usuários específicos em sua organização usando o Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780272"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="d3211-103">Configurar o Clutter para sua organização</span><span class="sxs-lookup"><span data-stu-id="d3211-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="d3211-104">[A Caixa de Entrada](../setup/configure-focused-inbox.md) Focada substituirá o Clutter.</span><span class="sxs-lookup"><span data-stu-id="d3211-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="d3211-105">Saiba mais: [atualização na Caixa de Entrada Focada e nossos planos para o Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="d3211-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="d3211-106">Como administrador, você pode ter que gerenciar o recurso Desorganização no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3211-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="d3211-107">Para ativar/desativar o recurso Desorganização para usuários em sua organização, você deve usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3211-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="d3211-108">(Os indivíduos podem a ativar/desativar usando estas instruções: [Desativar/ativar o Clutter no Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="d3211-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="d3211-109">Confira o [uso do PowerShell com o Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) e [conecte-se ao PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) do Exchange Online para obter detalhes sobre como usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3211-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="d3211-110">Você precisa ter uma conta que tenha pelo menos a função de administrador do Serviço do Exchange e a capacidade de se conectar ao Exchange Online com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3211-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="d3211-111">Ativar o Clutter usando o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3211-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="d3211-112">Você pode habilitar o Email Desorganizou manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446)</span><span class="sxs-lookup"><span data-stu-id="d3211-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="d3211-113">Você também pode exibir as configurações de Email de Email de sua organização executando o cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759)</span><span class="sxs-lookup"><span data-stu-id="d3211-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="d3211-114">Ativar o Clutter para um único usuário chamado Allie Bellew</span><span class="sxs-lookup"><span data-stu-id="d3211-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="d3211-115">Desativar o Clutter usando o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3211-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="d3211-116">Você pode desabilitar o Email Desorganizar manualmente para uma caixa de correio executando o cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446)</span><span class="sxs-lookup"><span data-stu-id="d3211-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="d3211-117">Você também pode exibir as **configurações** de Email de Email de sua organização executando o cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759)</span><span class="sxs-lookup"><span data-stu-id="d3211-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="d3211-118">Desativar o Clutter para uma única usuária chamada Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="d3211-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="d3211-119">Se você usar o PowerShell para criar seus usuários em massa, precisará executar [o Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) na caixa de correio de cada usuário para gerenciar o Clutter.</span><span class="sxs-lookup"><span data-stu-id="d3211-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="d3211-120">Quando a opção Desorganização é exibida para os usuários no Outlook na Web?</span><span class="sxs-lookup"><span data-stu-id="d3211-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="d3211-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="d3211-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="d3211-122">Como administrador, você pode reabilitar o Clutter usando o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3211-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="d3211-123">Quando isso for feito, a Caixa de Entrada Focada será desligada e o Clutter estará ativo novamente.</span><span class="sxs-lookup"><span data-stu-id="d3211-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="d3211-124">**Se você estiver usando o Outlook na Web com uma assinatura do Microsoft 365 Business Premium:**</span><span class="sxs-lookup"><span data-stu-id="d3211-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="d3211-125">Se o usuário atualmente tiver o Clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="d3211-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="d3211-126">As configurações de desorganização são exibidas</span><span class="sxs-lookup"><span data-stu-id="d3211-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="d3211-127">Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada:</span><span class="sxs-lookup"><span data-stu-id="d3211-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="d3211-128">As configurações de desorganização não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="d3211-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="d3211-129">Se nem o Clutter ou a Caixa de Entrada Focada estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="d3211-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="d3211-130">O Email e a Caixa de Entrada Focada aparecem como opções nas Configurações de Email do usuário</span><span class="sxs-lookup"><span data-stu-id="d3211-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="d3211-131">**Se você estiver usando Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="d3211-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="d3211-132">Se o usuário atualmente tiver o Clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="d3211-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="d3211-133">As configurações de desorganização são exibidas</span><span class="sxs-lookup"><span data-stu-id="d3211-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="d3211-134">Se o usuário atualmente tiver a Caixa de Entrada Focada habilitada:</span><span class="sxs-lookup"><span data-stu-id="d3211-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="d3211-135">As configurações de desorganização não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="d3211-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="d3211-136">Se nem o Clutter ou a Caixa de Entrada Focada estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="d3211-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="d3211-137">O Email e a Caixa de Entrada Focada aparecem como opções nas Configurações de Email do usuário</span><span class="sxs-lookup"><span data-stu-id="d3211-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="d3211-138">Se o usuário tiver habilitado a Caixa de Entrada Focada em algum momento no passado:</span><span class="sxs-lookup"><span data-stu-id="d3211-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="d3211-139">As configurações de desorganização nunca serão exibidas</span><span class="sxs-lookup"><span data-stu-id="d3211-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="d3211-140">Caso contrário,</span><span class="sxs-lookup"><span data-stu-id="d3211-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="d3211-141">As configurações de desorganização serão exibidas</span><span class="sxs-lookup"><span data-stu-id="d3211-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="d3211-142">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d3211-142">Related articles</span></span>
<span data-ttu-id="d3211-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="d3211-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="d3211-144">Usar o Clutter para classificar mensagens de baixa prioridade no Outlook</span><span class="sxs-lookup"><span data-stu-id="d3211-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="d3211-145">Usar o Clutter para classificar mensagens de baixa prioridade no OWA</span><span class="sxs-lookup"><span data-stu-id="d3211-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="d3211-146">Desativar o Clutter no Outlook</span><span class="sxs-lookup"><span data-stu-id="d3211-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

