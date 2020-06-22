---
title: Configurar a Caixa de Entrada Destaques para todos em sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Aprenda a configurar a Caixa de Entrada Destaques para todos ou usuários específicos da sua organização. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779924"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="bdcb1-103">Configurar a Caixa de Entrada Destaques para todos na sua organização</span><span class="sxs-lookup"><span data-stu-id="bdcb1-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="bdcb1-104">Se você é responsável por configurar como o e-mail funciona para TODOS em uma empresa, este artigo é para você! </span><span class="sxs-lookup"><span data-stu-id="bdcb1-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="bdcb1-105">Ele explica como personalizá-lo ou desativá-lo para a sua empresa e responde a perguntas sobre [Perguntas frequentes](#faq-for-focused-inbox).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="bdcb1-106">Se você quiser desligar a Caixa de Entrada Destaques por si mesmo, confira [Desativar a Caixa de Entrada Destaques](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  
   
<span data-ttu-id="bdcb1-107">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-107">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view.</span></span> <span data-ttu-id="bdcb1-108">You can also control whether users in your organization see the Focused Inbox in their mailbox.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-108">You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="bdcb1-109">Ativar ou desativar a Caixa de Entrada Destaques na sua organização</span><span class="sxs-lookup"><span data-stu-id="bdcb1-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="bdcb1-110">Usar o PowerShell para ativar ou desativar a Caixa de Entrada Destaques para todos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="bdcb1-111">Você quer fazer isso no centro de administração do Office 365?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="bdcb1-112">Informe nossa equipe de engenharia.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-112">Let our Engineering team know.</span></span> <span data-ttu-id="bdcb1-113">**[Vote aqui!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="bdcb1-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="bdcb1-114">**Para desativar a Caixa de Entrada Destaques:**</span><span class="sxs-lookup"><span data-stu-id="bdcb1-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="bdcb1-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span></span> <span data-ttu-id="bdcb1-116">However, it doesn't block the availability of the feature for your users.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-116">However, it doesn't block the availability of the feature for your users.</span></span> <span data-ttu-id="bdcb1-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="bdcb1-118">[Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="bdcb1-119">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="bdcb1-120">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-120">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="bdcb1-121">Execute o cmdlet **Get-OrganizationConfig**.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="bdcb1-122">Procure **FocusedInboxOn** para ver a configuração atual:</span><span class="sxs-lookup"><span data-stu-id="bdcb1-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![Resposta do PowerShell no estado da Caixa de Entrada Destaques.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="bdcb1-124">Execute o cmdlet a seguir para desativar a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="bdcb1-125">Execute o cmdlet **Get-OrganizationConfig** novamente e você verá que FocusedInboxOn está definido como $false, o que significa que ele está desativado.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="bdcb1-126">**Para ativar a Caixa de Entrada Destaques:**</span><span class="sxs-lookup"><span data-stu-id="bdcb1-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="bdcb1-127">Na Etapa 5 acima, execute o cmdlet a seguir para ativar a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="bdcb1-128">O que os usuários veem depois que ativo a Caixa de Entrada Destaques? </span><span class="sxs-lookup"><span data-stu-id="bdcb1-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="bdcb1-129">Your users will see the Focused view only after they close and restart Outlook.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-129">Your users will see the Focused view only after they close and restart Outlook.</span></span> <span data-ttu-id="bdcb1-130">When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-130">When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![Uma imagem da aparência da Caixa de Entrada Destaques quando um usuário abre pela primeira vez o Outlook na Web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="bdcb1-132">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-132">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature.</span></span> <span data-ttu-id="bdcb1-133">If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-133">If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one.</span></span> <span data-ttu-id="bdcb1-134">The tip looks like this:</span><span class="sxs-lookup"><span data-stu-id="bdcb1-134">The tip looks like this:</span></span>
  
![Imagem mostrando a aparência da Caixa de Entrada Destaques quando ela é implantada para os usuários e o Outlook é reaberto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="bdcb1-136">When a user decides to start using Focused Inbox, Clutter gets disabled automatically.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-136">When a user decides to start using Focused Inbox, Clutter gets disabled automatically.</span></span> <span data-ttu-id="bdcb1-137">The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-137">The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="bdcb1-138">Ative ou desative a Caixa de Entrada Destaques para determinados usuários</span><span class="sxs-lookup"><span data-stu-id="bdcb1-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="bdcb1-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="bdcb1-140">However, it doesn't block the availability of the feature to him.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="bdcb1-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="bdcb1-142">[Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="bdcb1-143">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-143">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="bdcb1-144">To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-144">To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="bdcb1-145">Execute o cmdlet **Get-FocusedInbox**, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bdcb1-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="bdcb1-146">Procure FocusedInboxOn para ver a configuração atual:</span><span class="sxs-lookup"><span data-stu-id="bdcb1-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![Resposta do PowerShell no estado da Caixa de Entrada Destaques.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="bdcb1-148">Execute o cmdlet a seguir para desativar a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="bdcb1-149">OU, execute o cmdlet a seguir para ativá-la:</span><span class="sxs-lookup"><span data-stu-id="bdcb1-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="bdcb1-150">Use a interface do usuário para criar uma regra de transporte para direcionar mensagens de e-mail ao modo de exibição Destaques para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="bdcb1-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="bdcb1-151">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="bdcb1-152">Navegue até **Regras de** \> **fluxo de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="bdcb1-153">Clique em ![Ícone Adicionar EAC](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) e clique em **Criar uma nova regra...**.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="bdcb1-154">Quando concluir a criação da nova regra, clique em **Salvar** para iniciá-la.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="bdcb1-155">A imagem a seguir mostra um exemplo em que todas as mensagens com o assunto "Departamento da Folha de Pagamento" são entregues na Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![folha de pagamento focusedinbox](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="bdcb1-157">Use o PowerShell para criar uma regra de transporte para direcionar mensagens de e-mail ao modo de exibição Destaques para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="bdcb1-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="bdcb1-158">[Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="bdcb1-159">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-159">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="bdcb1-160">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-160">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="bdcb1-161">Execute o comando a seguir para permitir que todas as mensagens do "Departamento da Folha de Pagamento", por exemplo, sejam entregues na Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="bdcb1-162">Neste exemplo, tanto "X-MS-Exchange-Organization-BypassFocusedInbox" quanto "true" diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="bdcb1-163">Além disso, a Caixa de Entrada Destaques respeitará o cabeçalho X que ignora o Clutter, portanto, se você usar essa configuração no Clutter, ela será usada na Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="bdcb1-164">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bdcb1-165">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-165">How do you know this worked?</span></span>

<span data-ttu-id="bdcb1-166">Você pode verificar os cabeçalhos das mensagens de email para conferir se elas estão chegando na Caixa de Entrada por ignorar a regra de transporte da Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="bdcb1-167">Escolha uma mensagem de email de uma caixa de correio na sua organização que tenha a regra de transporte da Caixa de Entrada Destaques aplicada.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="bdcb1-168">Examine os cabeçalhos marcados na mensagem e você verá o cabeçalho **X-MS-Exchange-Organization-BypassFocusedInbox: true**.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="bdcb1-169">Isso significa que a regra está sendo ignorada.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-169">This means the bypass is working.</span></span> <span data-ttu-id="bdcb1-170">Confira o artigo [Exibir as informações de cabeçalho de Internet por uma mensagem de e-mail](https://go.microsoft.com/fwlink/p/?LinkId=822530) para obter mais informações sobre como encontrar as informações de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="bdcb1-171">Ativar/desativar o Clutter</span><span class="sxs-lookup"><span data-stu-id="bdcb1-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="bdcb1-172">We've received reports that Clutter suddenly stopped working for some users.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-172">We've received reports that Clutter suddenly stopped working for some users.</span></span> <span data-ttu-id="bdcb1-173">If this happens, you can enable it again for specific users.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-173">If this happens, you can enable it again for specific users.</span></span> <span data-ttu-id="bdcb1-174">See [Configure Clutter for your organization](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-174">See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="bdcb1-175">Perguntas frequentes sobre a Caixa de Entrada Destaques</span><span class="sxs-lookup"><span data-stu-id="bdcb1-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="bdcb1-176">Aqui estão respostas para Perguntas frequentes sobre a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="bdcb1-177">Posso controlar como distribuir a Caixa de Entrada Destaque na minha organização?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="bdcb1-178">Yes.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-178">Yes.</span></span> <span data-ttu-id="bdcb1-179">You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-179">You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users.</span></span> <span data-ttu-id="bdcb1-180">See above.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-180">See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="bdcb1-181">O recurso Caixa de Entrada Destaques está disponível APENAS para clientes do Office 2016?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="bdcb1-182">Sim, somente usuários com o Office 2016 são afetados.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="bdcb1-183">O recurso não será disponibilizado para o Outlook 2013 e versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="bdcb1-184">Quanto tempo leva para as alterações da Caixa de Entrada Destaques serem feitas no Outlook?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="bdcb1-185">Depois que você ativar ou desativar a Caixa de Entrada Destaques, as configurações serão efetivadas quando os usuários fecharem e reiniciarem o Outlook.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="bdcb1-186">O que acontece com o Email Secundário depois que eu ativar a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="bdcb1-187">After switching, you'll no longer receive less actionable email in the Clutter folder.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-187">After switching, you'll no longer receive less actionable email in the Clutter folder.</span></span> <span data-ttu-id="bdcb1-188">Instead, email will be split between the Focused and Other tabs in your inbox.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-188">Instead, email will be split between the Focused and Other tabs in your inbox.</span></span> <span data-ttu-id="bdcb1-189">The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-189">The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other.</span></span> <span data-ttu-id="bdcb1-190">Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-190">Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="bdcb1-191">Confira esta postagem de [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP da Microsoft: [Como a Caixa de Entrada Destaques substituirá o Email Secundário no Office 365](https://www.petri.com/focused-inbox-office-365).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="bdcb1-192">Posso manter os usuários no Clutter?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="bdcb1-193">O que a Microsoft recomenda sobre o uso do Email Secundário e da Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="bdcb1-194">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-194">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now.</span></span> <span data-ttu-id="bdcb1-195">To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span><span class="sxs-lookup"><span data-stu-id="bdcb1-195">To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="bdcb1-196">Devo desabilitar o Clutter dos meus usuários finais se migrarmos para a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="bdcb1-197">No.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-197">No.</span></span> <span data-ttu-id="bdcb1-198">It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-198">It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet.</span></span> <span data-ttu-id="bdcb1-199">However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-199">However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox.</span></span> <span data-ttu-id="bdcb1-200">It's therefore best not to disable Clutter until the upgraded clients are available.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-200">It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="bdcb1-201">Por que há dois cmdlets diferentes para gerenciar a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="bdcb1-202">Há dois estados associados à Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="bdcb1-203">**Nível da Organização**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="bdcb1-204">**Nível da Caixa de Correio**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="bdcb1-205">Como o Outlook decide mostrar a experiência da Caixa de Entrada Destaques com esses dois estados?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="bdcb1-206">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-206">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp.</span></span> <span data-ttu-id="bdcb1-207">By default, both time stamps are "null" and in this case, the feature is enabled.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-207">By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="bdcb1-208">Por que o cmdlet Get-FocusedInbox retorna "true" quando eu desativo a Caixa de Entrada Destaques na minha organização?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="bdcb1-209">There are two cmdlets for controlling Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-209">There are two cmdlets for controlling Focused Inbox.</span></span> <span data-ttu-id="bdcb1-210">When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-210">When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature.</span></span> <span data-ttu-id="bdcb1-211">The experience in Outlook is chosen based on which cmdlet state was last modified.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-211">The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="bdcb1-212">Posso executar um script para ver quem ativou a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="bdcb1-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="bdcb1-213">No, and this is by design.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-213">No, and this is by design.</span></span> <span data-ttu-id="bdcb1-214">Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-214">Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience.</span></span> <span data-ttu-id="bdcb1-215">It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span><span class="sxs-lookup"><span data-stu-id="bdcb1-215">It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
