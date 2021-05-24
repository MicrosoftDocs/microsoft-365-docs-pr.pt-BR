---
title: Configurar a Caixa de Entrada Destaques para todos em sua organização
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: Se você é responsável por definir as configurações de email para todos em uma empresa, este artigo explica como configurar a Caixa de entrada Destaques para os usuários.
ms.openlocfilehash: ddd0886988072139a199bfc3f6e8adbbf25ad58b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623696"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="b51c9-103">Configurar a Caixa de Entrada Destaques para todos na sua organização</span><span class="sxs-lookup"><span data-stu-id="b51c9-103">Configure Focused Inbox for everyone in your organization</span></span>

<span data-ttu-id="b51c9-104">Se você é responsável por configurar como o e-mail funciona para TODOS em uma empresa, este artigo é para você! </span><span class="sxs-lookup"><span data-stu-id="b51c9-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="b51c9-105">Ele explica como personalizá-lo ou desativá-lo para a sua empresa e responde a perguntas sobre [Perguntas frequentes](#faq-for-focused-inbox).</span><span class="sxs-lookup"><span data-stu-id="b51c9-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>

<span data-ttu-id="b51c9-106">Se você quiser desligar a Caixa de Entrada Destaques por si mesmo, confira [Desativar a Caixa de Entrada Destaques](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span><span class="sxs-lookup"><span data-stu-id="b51c9-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  

<span data-ttu-id="b51c9-p102">Se quiser garantir que seus usuários recebam mensagens de email específicas de negócios, por exemplo, do RH ou da folha de pagamentos, você pode configurar a Caixa de Entrada Destaques para que essas mensagens alcancem o modo de exibição Destaques. Você também pode controlar se os usuários da sua organização veem a Caixa de Entrada Destaques nas caixas de correio deles.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="b51c9-109">Ativar ou desativar a Caixa de Entrada Destaques na sua organização</span><span class="sxs-lookup"><span data-stu-id="b51c9-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="b51c9-110">Usar o PowerShell para ativar ou desativar a Caixa de Entrada Destaques para todos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b51c9-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="b51c9-111">Você quer fazer isso no centro de administração do Office 365?</span><span class="sxs-lookup"><span data-stu-id="b51c9-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="b51c9-112">Informe nossa equipe de engenharia.</span><span class="sxs-lookup"><span data-stu-id="b51c9-112">Let our Engineering team know.</span></span> <span data-ttu-id="b51c9-113">**[Vote aqui!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="b51c9-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
<span data-ttu-id="b51c9-114">**Para desativar a Caixa de Entrada Destaques:**</span><span class="sxs-lookup"><span data-stu-id="b51c9-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="b51c9-p104">O exemplo a seguir do PowerShell **desativa** a Caixa de Entrada Destaques na organização. No entanto, ele não bloqueia a disponibilidade do recurso para os usuários; ou seja, eles ainda poderão reativar a Caixa de Entrada Destaques em cada um dos respectivos clientes.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="b51c9-118">[Conecte-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b51c9-118">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b51c9-p105">Você deve ter permissões para poder realizar esses procedimentos. Para ver quais são as permissões necessárias, confira a entrada "Regras de transporte" no artigo [Permissões de política e conformidade de mensagens](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="b51c9-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span></span>

3. <span data-ttu-id="b51c9-121">Execute o cmdlet **Get-OrganizationConfig**.</span><span class="sxs-lookup"><span data-stu-id="b51c9-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 

    ```powershell
    Get-OrganizationConfig
    ```

4. <span data-ttu-id="b51c9-122">Procure **FocusedInboxOn** para ver a configuração atual:</span><span class="sxs-lookup"><span data-stu-id="b51c9-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 

    ![Resposta do PowerShell no estado da Caixa de Entrada Destaques.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="b51c9-124">Execute o cmdlet a seguir para desativar a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-124">Run the following cmdlet to turn Focused Inbox off.</span></span>

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. <span data-ttu-id="b51c9-125">Execute o cmdlet **Get-OrganizationConfig** novamente e você verá que FocusedInboxOn está definido como $false, o que significa que ele está desativado.</span><span class="sxs-lookup"><span data-stu-id="b51c9-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 

<span data-ttu-id="b51c9-126">**Para ativar a Caixa de Entrada Destaques:**</span><span class="sxs-lookup"><span data-stu-id="b51c9-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="b51c9-127">Na Etapa 5 acima, execute o cmdlet a seguir para ativar a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="b51c9-128">O que os usuários veem depois que ativo a Caixa de Entrada Destaques? </span><span class="sxs-lookup"><span data-stu-id="b51c9-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="b51c9-p106">Os usuários verão o modo de exibição Destaques somente após fechar e reiniciar o Outlook. Depois disso, eles verão uma dica na interface do usuário do programa mostrando a opção de usar a nova Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![Uma imagem da aparência da Caixa de Entrada Destaques quando um usuário abre pela primeira vez o Outlook na Web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="b51c9-p107&quot;>Se estiver migrando do Email secundário para a Caixa de Entrada Destaques, eles poderão decidir habilitá-la (&quot;Experimente") ou ignorar o recurso. Se o usuário tiver vários clientes (compatíveis), eles poderão ativar/desativar a Caixa de Entrada Destaques individualmente em cada um deles. A dica tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="b51c9-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![Imagem mostrando a aparência da Caixa de Entrada Destaques quando ela é implantada para os usuários e o Outlook é reaberto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="b51c9-p108">Quando um usuário decide começar a usar a Caixa de Entrada Destaques, o Email secundário é desabilitado automaticamente. A pasta Email secundário é convertida em uma pasta padrão, que permite ao usuário renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="b51c9-138">Ative ou desative a Caixa de Entrada Destaques para determinados usuários</span><span class="sxs-lookup"><span data-stu-id="b51c9-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="b51c9-139">Este exemplo **desativa** a Caixa de Entrada Destaques para Henrique Cunha na organização Contoso.</span><span class="sxs-lookup"><span data-stu-id="b51c9-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="b51c9-140">No entanto, ele não bloqueia a disponibilidade do recurso para ele.</span><span class="sxs-lookup"><span data-stu-id="b51c9-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="b51c9-141">Se ele quiser, ainda poderá habilitar novamente a Caixa de Entrada Destaques em cada um dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="b51c9-141">If he wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="b51c9-142">[Conecte-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b51c9-142">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b51c9-p110">Você precisa ter permissões antes de executar estes procedimentos. Para ver quais permissões são necessárias, confira a entrada "Regras de transporte" no tópico Permissões de política e conformidade de mensagens.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>

3. <span data-ttu-id="b51c9-145">Execute o cmdlet **Get-FocusedInbox**, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b51c9-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. <span data-ttu-id="b51c9-146">Procure FocusedInboxOn para ver a configuração atual:</span><span class="sxs-lookup"><span data-stu-id="b51c9-146">Look for FocusedInboxOn to view its current setting:</span></span>

    ![Resposta do PowerShell no estado da Caixa de Entrada Destaques.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="b51c9-148">Execute o cmdlet a seguir para desativar a Caixa de Entrada Destaques:</span><span class="sxs-lookup"><span data-stu-id="b51c9-148">Run the following cmdlet to turn off Focused Inbox:</span></span>

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    <span data-ttu-id="b51c9-149">OU, execute o cmdlet a seguir para ativá-la:</span><span class="sxs-lookup"><span data-stu-id="b51c9-149">OR, run the following cmdlet to turn it on:</span></span>

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="b51c9-150">Use a interface do usuário para criar uma regra de transporte para direcionar mensagens de e-mail ao modo de exibição Destaques para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="b51c9-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="b51c9-151">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="b51c9-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="b51c9-152">Navegue até **Regras de** \> **fluxo de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="b51c9-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="b51c9-153">Clique em ![Ícone Adicionar EAC](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) e clique em **Criar uma nova regra...**.</span><span class="sxs-lookup"><span data-stu-id="b51c9-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 

3. <span data-ttu-id="b51c9-154">Quando concluir a criação da nova regra, clique em **Salvar** para iniciá-la.</span><span class="sxs-lookup"><span data-stu-id="b51c9-154">After you're done creating the new rule, select **Save** to start the rule.</span></span>

    <span data-ttu-id="b51c9-155">A imagem a seguir mostra um exemplo em que todas as mensagens com o assunto "Departamento da Folha de Pagamento" são entregues na Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>

    ![folha de pagamento focusedinbox](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > <span data-ttu-id="b51c9-157">Neste exemplo, o texto do valor de cabeçalho da mensagem é **X-MS-Exchange-Organization-BypassFocusedInbox**.</span><span class="sxs-lookup"><span data-stu-id="b51c9-157">The message header value text in this example is, **X-MS-Exchange-Organization-BypassFocusedInbox**.</span></span>
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="b51c9-158">Use o PowerShell para criar uma regra de transporte para direcionar mensagens de e-mail ao modo de exibição Destaques para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="b51c9-158">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="b51c9-159">[Conecte-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b51c9-159">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b51c9-p112">Você deve ter permissões para poder realizar esses procedimentos. Para ver quais são as permissões necessárias, confira a entrada "Regras de transporte" no artigo [Permissões de política e conformidade de mensagens](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="b51c9-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span></span>

3. <span data-ttu-id="b51c9-162">Execute o comando a seguir para permitir que todas as mensagens do "Departamento da Folha de Pagamento", por exemplo, sejam entregues na Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-162">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> <span data-ttu-id="b51c9-163">Neste exemplo, tanto "X-MS-Exchange-Organization-BypassFocusedInbox" quanto "true" diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b51c9-163">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="b51c9-164">Além disso, a Caixa de Entrada Destaques respeitará o cabeçalho X que ignora o Clutter, portanto, se você usar essa configuração no Clutter, ela será usada na Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-164">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="b51c9-165">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="b51c9-165">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b51c9-166">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="b51c9-166">How do you know this worked?</span></span>

<span data-ttu-id="b51c9-167">Você pode verificar os cabeçalhos das mensagens de email para conferir se elas estão chegando na Caixa de Entrada por ignorar a regra de transporte da Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-167">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="b51c9-168">Escolha uma mensagem de email de uma caixa de correio na sua organização que tenha a regra de transporte da Caixa de Entrada Destaques aplicada.</span><span class="sxs-lookup"><span data-stu-id="b51c9-168">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="b51c9-169">Examine os cabeçalhos marcados na mensagem e você verá o cabeçalho **X-MS-Exchange-Organization-BypassFocusedInbox: true**.</span><span class="sxs-lookup"><span data-stu-id="b51c9-169">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="b51c9-170">Isso significa que a regra está sendo ignorada.</span><span class="sxs-lookup"><span data-stu-id="b51c9-170">This means the bypass is working.</span></span> <span data-ttu-id="b51c9-171">Confira o artigo [Exibir as informações de cabeçalho de Internet por uma mensagem de e-mail](https://go.microsoft.com/fwlink/p/?LinkId=822530) para obter mais informações sobre como encontrar as informações de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b51c9-171">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span>

### <a name="what-will-the-user-see"></a><span data-ttu-id="b51c9-172">O que o usuário verá?</span><span class="sxs-lookup"><span data-stu-id="b51c9-172">What will the user see?</span></span>

<span data-ttu-id="b51c9-173">Se uma regra de transporte estiver em uso, uma notificação para a substituição será exibida.</span><span class="sxs-lookup"><span data-stu-id="b51c9-173">If a transport rule is in place, a notification will be shown for the override.</span></span> <span data-ttu-id="b51c9-174">O Outlook na Web desabilitará a opção "Sempre Mover para Outros" e mostrará uma dica de ferramenta.</span><span class="sxs-lookup"><span data-stu-id="b51c9-174">Outlook on the web will disable the "Always move to Other" and show a tooltip.</span></span> <span data-ttu-id="b51c9-175">Os clientes do Outlook da área de trabalho permitirão a seleção para "Sempre Mover para Outros" e uma caixa de diálogo abrirá.</span><span class="sxs-lookup"><span data-stu-id="b51c9-175">Outlook clients on desktop will allow selection for "Always move to Other" and will pop up a dialog.</span></span>

## <a name="turn-onoff-clutter"></a><span data-ttu-id="b51c9-176">Ativar/desativar o Clutter</span><span class="sxs-lookup"><span data-stu-id="b51c9-176">Turn on/off Clutter</span></span>

<span data-ttu-id="b51c9-p116">Recebemos relatórios informando que o Email secundário subitamente parou de funcionar para alguns usuários. Se isso acontecer, será possível habilitá-lo novamente para usuários específicos. Veja [Configuração do Email secundário para sua organização](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="b51c9-p116">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>

## <a name="faq-for-focused-inbox"></a><span data-ttu-id="b51c9-180">Perguntas frequentes sobre a Caixa de Entrada Destaques</span><span class="sxs-lookup"><span data-stu-id="b51c9-180">FAQ for Focused Inbox</span></span>

<span data-ttu-id="b51c9-181">Aqui estão respostas para Perguntas frequentes sobre a Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-181">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span>

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="b51c9-182">Posso controlar como distribuir a Caixa de Entrada Destaque na minha organização?</span><span class="sxs-lookup"><span data-stu-id="b51c9-182">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="b51c9-p117">Sim. Você pode ativar ou desativar a Caixa de Entrada Destaques para toda a sua organização ou para usuários específicos. Veja acima.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p117">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="b51c9-186">O recurso Caixa de Entrada Destaques está disponível APENAS para clientes do Office 2016?</span><span class="sxs-lookup"><span data-stu-id="b51c9-186">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="b51c9-p118">Sim, somente os usuários com o Office 2016 são afetados. O recurso não será disponibilizado para o Outlook 2013 e versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p118">Yes, only users with Office 2016 are affected. The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="b51c9-189">Quanto tempo leva para as alterações da Caixa de Entrada Destaques serem feitas no Outlook?</span><span class="sxs-lookup"><span data-stu-id="b51c9-189">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="b51c9-190">Depois que você ativar ou desativar a Caixa de Entrada Destaques, as configurações serão efetivadas quando os usuários fecharem e reiniciarem o Outlook.</span><span class="sxs-lookup"><span data-stu-id="b51c9-190">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="b51c9-191">O que acontece com o Email Secundário depois que eu ativar a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="b51c9-191">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="b51c9-p119">Após a mudança, você deixará de receber emails menos importantes na pasta Email secundário. Em vez disso, os emails serão divididos entre as guias Destaques e Outros na Caixa de Entrada. O mesmo algoritmo que movia itens para a pasta de Email secundário agora habilita a Caixa de Entrada Destaques. Isso significa que todos os emails que foram definidos para serem movidos para a pasta de Email secundário agora serão movidos para a pasta Outros. As mensagens que já estão na pasta de Email secundário permanecerão nesse local até que você decida excluí-las ou movê-las.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p119">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="b51c9-196">Confira esta postagem de [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP da Microsoft: [Como a Caixa de Entrada Destaques substituirá o Email Secundário no Office 365](https://www.petri.com/focused-inbox-office-365).</span><span class="sxs-lookup"><span data-stu-id="b51c9-196">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="b51c9-p120">Posso manter os usuários no Email secundário? Qual é a recomendação da Microsoft quando se trata de usar Email secundário vs Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="b51c9-p120">Can I keep users on Clutter? What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="b51c9-p121">Sim, você pode manter os usuários no Email secundário e desabilitar a Caixa de Entrada Destaques; no entanto, futuramente o Email Secundário será totalmente substituído pela Caixa de Entrada Destaques, portanto, a Microsoft recomenda migrar para a Caixa de Entrada Destaques agora. Para saber mais sobre quando usar a pasta Email secundário no Exchange Online, confira a seguinte postagem de blog: [Atualização sobre a Caixa de Entrada Destaques e nossos planos para o Email secundário](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span><span class="sxs-lookup"><span data-stu-id="b51c9-p121">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="b51c9-201">Devo desabilitar o Clutter dos meus usuários finais se migrarmos para a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="b51c9-201">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="b51c9-p122">Não. É possível desabilitar o Email Secundário para uma caixa de correio explicitamente executando o Set-Clutter. No entanto, se fizer isso, o proprietário da caixa de correio verá que mensagens que anteriormente foram redirecionadas para a pasta Email Secundário permanecerão na Caixa de Entrada e será necessário processar essas mensagens até que o cliente seja atualizado para uma versão ofereça suporte para a Caixa de Entrada Destaques. Portanto, é melhor não desabilitar o Email Secundário até que os clientes atualizados estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p122">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="b51c9-206">Por que há dois cmdlets diferentes para gerenciar a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="b51c9-206">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="b51c9-207">Há dois estados associados à Caixa de Entrada Destaques.</span><span class="sxs-lookup"><span data-stu-id="b51c9-207">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="b51c9-208">**Nível da Organização**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado.</span><span class="sxs-lookup"><span data-stu-id="b51c9-208">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span>

- <span data-ttu-id="b51c9-209">**Nível da Caixa de Correio**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado.</span><span class="sxs-lookup"><span data-stu-id="b51c9-209">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="b51c9-210">Como o Outlook decide mostrar a experiência da Caixa de Entrada Destaques com esses dois estados?</span><span class="sxs-lookup"><span data-stu-id="b51c9-210">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="b51c9-p123">O Outlook decide mostrar a experiência escolhendo cmdlet que tem o carimbo de data/hora mais recente. Por padrão, ambos os carimbos são "nulos" e, nesse caso, o recurso é habilitado.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p123">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="b51c9-213">Por que o cmdlet Get-FocusedInbox retorna "true" quando eu desativo a Caixa de Entrada Destaques na minha organização?</span><span class="sxs-lookup"><span data-stu-id="b51c9-213">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="b51c9-p124">Há dois cmdlets para controlar a Caixa de Entrada Destaques. Quando você executa Get-FocusedInbox para uma caixa de correio, ele retorna o estado do nível da caixa de correio do recurso. A experiência do Outlook é escolhida com base em qual estado de cmdlet foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p124">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="b51c9-217">Posso executar um script para ver quem ativou a Caixa de Entrada Destaques?</span><span class="sxs-lookup"><span data-stu-id="b51c9-217">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="b51c9-p125">Não, e isso ocorre por design. A ativação da Caixa de entrada destaques é uma configuração do lado do cliente, portanto, tudo o que o cmdlet pode fazer é informar se a caixa de correio do usuário está qualificada para a experiência do cliente. É possível que seja habilitado simultaneamente em alguns clientes e desabilitado em outros, por exemplo, habilitado no aplicativo Outlook e Outlook Mobile, mas desabilitado no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="b51c9-p125">No, and this is by design. Focused Inbox enablement is a client-side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>

## <a name="related-content"></a><span data-ttu-id="b51c9-221">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b51c9-221">Related content</span></span>

<span data-ttu-id="b51c9-222">[Configure o Email secundário para sua organização ](../email/configure-clutter.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b51c9-222">[Configure Clutter for your organization](../email/configure-clutter.md) (article)</span></span>\
<span data-ttu-id="b51c9-223">[Definir configurações de caixa de correio compartilhada](../email/configure-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b51c9-223">[Configure shared mailbox settings](../email/configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="b51c9-224">[Criar assinaturas e isenções de responsabilidade ](create-signatures-and-disclaimers.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="b51c9-224">[Create signatures and disclaimers](create-signatures-and-disclaimers.md) (video)</span></span>
