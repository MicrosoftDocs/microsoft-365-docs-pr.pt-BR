---
title: Configurar resíduos para sua organização
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Saiba como habilitar ou desabilitar o recurso de desordem para todos ou usuários específicos em sua organização, usando o Exchange PowerShell. '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250681"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="5d72c-103">Configurar resíduos para sua organização</span><span class="sxs-lookup"><span data-stu-id="5d72c-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="5d72c-104">A [caixa de entrada destaques](../setup/configure-focused-inbox.md) vai substituir resíduos.</span><span class="sxs-lookup"><span data-stu-id="5d72c-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="5d72c-105">Saiba mais: [Atualizar na caixa de entrada destaques e nos nossos planos de email secundário](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="5d72c-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="5d72c-106">Como administrador, você pode ter que gerenciar o recurso de desordem no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d72c-106">As an admin, you may have to manage the Clutter feature in Office 365.</span></span> <span data-ttu-id="5d72c-107">Para ativar/desativar o recurso de aglomeração para usuários em sua organização, você deve usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d72c-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="5d72c-108">(As pessoas podem ativá-la/desligar usando estas instruções: [desative/desobstruída no Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span><span class="sxs-lookup"><span data-stu-id="5d72c-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="5d72c-109">Confira [usando o PowerShell com o Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) e [Conecte-se ao PowerShell do Exchange Online](https://go.microsoft.com/fwlink/?LinkID=722415) para obter detalhes sobre como usar o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d72c-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="5d72c-110">Você precisa ter uma conta que tenha pelo menos a função Administrador de serviços do Exchange e a capacidade de se conectar ao Exchange Online com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d72c-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="5d72c-111">Tornar o email secundário usando o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d72c-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="5d72c-112">Você pode habilitar resíduos manualmente para uma caixa de correio executando o cmdlet [set-desordem](https://go.microsoft.com/fwlink/?LinkID=834446) .</span><span class="sxs-lookup"><span data-stu-id="5d72c-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="5d72c-113">Você também pode exibir configurações de resíduos para caixas de correio em sua organização executando o cmdlet de [obtenção-desordem](https://go.microsoft.com/fwlink/?LinkID=834759) .</span><span class="sxs-lookup"><span data-stu-id="5d72c-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="5d72c-114">Ative o email secundário para um único usuário chamado Leonor Marques</span><span class="sxs-lookup"><span data-stu-id="5d72c-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="5d72c-115">Desligar resíduos usando o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d72c-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="5d72c-116">Você pode desabilitar a desordem manualmente para uma caixa de correio executando o cmdlet [set-desordem](https://go.microsoft.com/fwlink/?LinkID=834446) .</span><span class="sxs-lookup"><span data-stu-id="5d72c-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="5d72c-117">Você também pode exibir configurações de **resíduos** para caixas de correio em sua organização executando o cmdlet de [obtenção-desordem](https://go.microsoft.com/fwlink/?LinkID=834759) .</span><span class="sxs-lookup"><span data-stu-id="5d72c-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="5d72c-118">Desative o email secundário para um único usuário chamado Leonor Marques:</span><span class="sxs-lookup"><span data-stu-id="5d72c-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="5d72c-119">Se você usar o PowerShell para criar seus usuários em massa, será necessário executar [set-desordem](https://go.microsoft.com/fwlink/?LinkID=834446) em relação à caixa de correio de cada usuário para gerenciar o email secundário.</span><span class="sxs-lookup"><span data-stu-id="5d72c-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="5d72c-120">Quando a opção de truncar/desligar aparece para os usuários no Outlook na Web?</span><span class="sxs-lookup"><span data-stu-id="5d72c-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="5d72c-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="5d72c-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="5d72c-122">Como administrador, você pode reabilitar resíduos usando o Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d72c-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="5d72c-123">Depois disso, a caixa de entrada destaques será desativada e a desordem ficará ativa novamente.</span><span class="sxs-lookup"><span data-stu-id="5d72c-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="5d72c-124">**Se você estiver usando o Outlook na Web com uma assinatura de negócios do Office 365:**</span><span class="sxs-lookup"><span data-stu-id="5d72c-124">**If you're using Outlook on the web with an Office 365 business subscription:**</span></span>
  
- <span data-ttu-id="5d72c-125">Se o usuário está com aglomeração habilitada:</span><span class="sxs-lookup"><span data-stu-id="5d72c-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="5d72c-126">As configurações de resíduos aparecem</span><span class="sxs-lookup"><span data-stu-id="5d72c-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="5d72c-127">Se o usuário tem atualmente a caixa de entrada destaques habilitada:</span><span class="sxs-lookup"><span data-stu-id="5d72c-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="5d72c-128">Configurações de resíduos não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="5d72c-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="5d72c-129">Se nenhuma caixa de entrada de email secundário ou prioritário estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="5d72c-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="5d72c-130">A desordem e a caixa de entrada destaques aparecem como opções nas configurações de email do usuário</span><span class="sxs-lookup"><span data-stu-id="5d72c-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="5d72c-131">**Se você estiver usando o Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="5d72c-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="5d72c-132">Se o usuário está com aglomeração habilitada:</span><span class="sxs-lookup"><span data-stu-id="5d72c-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="5d72c-133">As configurações de resíduos aparecem</span><span class="sxs-lookup"><span data-stu-id="5d72c-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="5d72c-134">Se o usuário tem atualmente a caixa de entrada destaques habilitada:</span><span class="sxs-lookup"><span data-stu-id="5d72c-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="5d72c-135">Configurações de resíduos não serão exibidas</span><span class="sxs-lookup"><span data-stu-id="5d72c-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="5d72c-136">Se nenhuma caixa de entrada de email secundário ou prioritário estiver habilitada:</span><span class="sxs-lookup"><span data-stu-id="5d72c-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="5d72c-137">A desordem e a caixa de entrada destaques aparecem como opções nas configurações de email do usuário</span><span class="sxs-lookup"><span data-stu-id="5d72c-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="5d72c-138">Se o usuário habilitou a caixa de entrada destaques em algum momento no passado:</span><span class="sxs-lookup"><span data-stu-id="5d72c-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="5d72c-139">As configurações de resíduos nunca serão exibidas</span><span class="sxs-lookup"><span data-stu-id="5d72c-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="5d72c-140">Outro</span><span class="sxs-lookup"><span data-stu-id="5d72c-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="5d72c-141">As configurações de resíduos serão exibidas</span><span class="sxs-lookup"><span data-stu-id="5d72c-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="5d72c-142">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="5d72c-142">Related articles</span></span>
<span data-ttu-id="5d72c-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="5d72c-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="5d72c-144">Usar email secundário para classificar mensagens de baixa prioridade no Outlook</span><span class="sxs-lookup"><span data-stu-id="5d72c-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[<span data-ttu-id="5d72c-145">Usar email secundário para classificar mensagens de baixa prioridade no OWA</span><span class="sxs-lookup"><span data-stu-id="5d72c-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="5d72c-146">Desligar resíduos no Outlook</span><span class="sxs-lookup"><span data-stu-id="5d72c-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

