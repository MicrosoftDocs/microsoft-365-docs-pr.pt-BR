---
title: Alterar os nameservers para configurar o Microsoft 365 com qualquer registrador de domínios
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Saiba como adicionar e configurar seu domínio no Microsoft 365 para que seus serviços como o email e o Skype for Business online usem seu próprio nome de domínio.
ms.openlocfilehash: 6a99ee90db3bb71038309175b32bd4d96097aa5a
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662227"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="70d89-103">Alterar os nameservers para configurar o Microsoft 365 com qualquer registrador de domínios</span><span class="sxs-lookup"><span data-stu-id="70d89-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="70d89-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="70d89-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="70d89-105">Confira primeiro [configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para ver se temos instruções para o seu registrador.</span><span class="sxs-lookup"><span data-stu-id="70d89-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="70d89-106">Siga estas instruções para adicionar e configurar seu domínio no Microsoft 365 para que seus serviços, como o email e o Microsoft Teams, usem seu próprio nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="70d89-107">Para fazer isso, verifique seu domínio e altere os nameservers do seu domínio para o Microsoft 365 para que os registros DNS corretos possam ser configurados para você.</span><span class="sxs-lookup"><span data-stu-id="70d89-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="70d89-108">Siga estas etapas se as instruções a seguir descrevem sua situação:</span><span class="sxs-lookup"><span data-stu-id="70d89-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="70d89-109">Você tem seu próprio domínio e deseja configurá-lo para funcionar com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70d89-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="70d89-110">Você deseja que a Microsoft 365 gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="70d89-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="70d89-111">Se preferir, é possível[ gerenciar seus próprios registros DNS ](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="70d89-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="70d89-112">Adicionar um registro TXT ou MX para verificação</span><span class="sxs-lookup"><span data-stu-id="70d89-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="70d89-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="70d89-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="70d89-p103">Você criará apenas um desses registros. O TXT é o tipo de registro preferencial, mas alguns provedores de host DNS não são compatíveis com ele. Nesse caso, você pode criar um registro MX como alternativa.</span><span class="sxs-lookup"><span data-stu-id="70d89-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="70d89-p104">Antes de usar o seu domínio com o Microsoft 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova ao Microsoft 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70d89-p105">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="70d89-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="70d89-120">Encontre a área no site do provedor de Hospedagem de DNS onde você pode criar um novo registro</span><span class="sxs-lookup"><span data-stu-id="70d89-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="70d89-121">Entre no site do seu provedor de hospedagem DNS.</span><span class="sxs-lookup"><span data-stu-id="70d89-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="70d89-122">Escolha seu domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="70d89-123">Localize a página na qual você pode editar registros DNS para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="70d89-124">Criar o registro</span><span class="sxs-lookup"><span data-stu-id="70d89-124">Create the record</span></span>

<span data-ttu-id="70d89-125">Caso esteja criando um registro TXT ou um registro MX, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="70d89-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="70d89-126">**Se você criar um registro TXT, use estes valores:**</span><span class="sxs-lookup"><span data-stu-id="70d89-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="70d89-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="70d89-127">**Record Type**</span></span> <br/> |<span data-ttu-id="70d89-128">**Alias** ou **Nome do host**</span><span class="sxs-lookup"><span data-stu-id="70d89-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="70d89-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="70d89-129">**Value**</span></span> <br/> |<span data-ttu-id="70d89-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="70d89-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="70d89-131">TXT</span><span class="sxs-lookup"><span data-stu-id="70d89-131">TXT</span></span>  <br/> |<span data-ttu-id="70d89-132">Siga um destes procedimentos: Digite **@**, deixe o campo vazio ou digite o seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="70d89-133">> [!NOTE]> Hosts DNS diferentes têm requisitos diferentes para este campo.</span><span class="sxs-lookup"><span data-stu-id="70d89-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="70d89-134">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="70d89-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="70d89-135">> [!NOTE]> Esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="70d89-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="70d89-136">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70d89-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="70d89-137">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="70d89-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="70d89-138">Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="70d89-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="70d89-139">**Se você criar um registro MX, use estes valores:**</span><span class="sxs-lookup"><span data-stu-id="70d89-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="70d89-140">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="70d89-140">**Record Type**</span></span>|<span data-ttu-id="70d89-141">**Alias** ou **Nome do host**</span><span class="sxs-lookup"><span data-stu-id="70d89-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="70d89-142">**Valor**</span><span class="sxs-lookup"><span data-stu-id="70d89-142">**Value**</span></span>|<span data-ttu-id="70d89-143">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="70d89-143">**Priority**</span></span>|<span data-ttu-id="70d89-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="70d89-144">**TTL**</span></span>|
|<span data-ttu-id="70d89-145">MX</span><span class="sxs-lookup"><span data-stu-id="70d89-145">MX</span></span>|<span data-ttu-id="70d89-146">Digite **@** ou seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="70d89-147">MS = ms *XXXXXXXX* > [!NOTE]> Esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="70d89-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="70d89-148">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70d89-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="70d89-149">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="70d89-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="70d89-150">Para **Priority**, para evitar conflitos com o registro MX usado para o fluxo de email, use uma prioridade menor do que a prioridade de qualquer registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="70d89-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="70d89-151">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="70d89-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="70d89-152">Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="70d89-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="70d89-153">Salvar o registro</span><span class="sxs-lookup"><span data-stu-id="70d89-153">Save the record</span></span>

<span data-ttu-id="70d89-154">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="70d89-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="70d89-155">Quando o Microsoft 365 encontrar o registros TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="70d89-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="70d89-156">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="70d89-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="70d89-157">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="70d89-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="70d89-158">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="70d89-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="70d89-159">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="70d89-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="70d89-p109">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="70d89-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="70d89-163">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="70d89-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="70d89-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="70d89-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="70d89-165">Ao chegar na última etapa do assistente de configuração de domínios no Microsoft 365, você tem uma tarefa restante.</span><span class="sxs-lookup"><span data-stu-id="70d89-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="70d89-166">Para configurar seu domínio com os serviços do Microsoft 365, como email, você altera os registros de nameserver (ou NS) do seu domínio no seu registrador de domínio para apontar para os nameservers primários e secundários da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70d89-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="70d89-167">Então, como a Microsoft 365 hospeda seu DNS, os registros DNS necessários para seus serviços são configurados automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="70d89-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="70d89-168">Você pode atualizar os registros de servidor de nomes por conta própria seguindo as etapas que seu registrador de domínio pode fornecer no conteúdo de Ajuda no site deles.</span><span class="sxs-lookup"><span data-stu-id="70d89-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="70d89-169">Se você não estiver familiarizado com DNS, contate o suporte no registrador de domínios.</span><span class="sxs-lookup"><span data-stu-id="70d89-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="70d89-170">Para alterar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="70d89-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="70d89-171">Encontre a área no site do registrador de domínio onde você pode alterar os nameservers para seu domínio ou uma área onde você pode usar nameservers personalizados.</span><span class="sxs-lookup"><span data-stu-id="70d89-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="70d89-172">Crie registros nameserver ou edite os registros de nameserver existentes para coincidir com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="70d89-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="70d89-173">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="70d89-173">First nameserver</span></span>  <br/> |<span data-ttu-id="70d89-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="70d89-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="70d89-175">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="70d89-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="70d89-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="70d89-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="70d89-177">Terceiro nameserver</span><span class="sxs-lookup"><span data-stu-id="70d89-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="70d89-178">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="70d89-178">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="70d89-179">Quarto nameserver</span><span class="sxs-lookup"><span data-stu-id="70d89-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="70d89-180">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="70d89-180">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="70d89-181">É melhor adicionar todos os quatro registros, mas se o registrador suportar apenas dois, adicione **ns1.bdm.microsoftonline.com** e **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="70d89-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="70d89-182">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="70d89-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="70d89-183">Quando você alterar os registros NS do seu domínio para apontar para os nameservers da Microsoft 365, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="70d89-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="70d89-184">Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="70d89-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="70d89-185">Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.</span><span class="sxs-lookup"><span data-stu-id="70d89-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="70d89-186">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="70d89-187">Crie dois registros de servidor de nomes ou edite os registros de servidor de nomes existentes para que eles correspondam aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="70d89-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="70d89-188">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="70d89-188">First nameserver</span></span>  <br/> |<span data-ttu-id="70d89-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="70d89-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="70d89-190">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="70d89-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="70d89-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="70d89-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="70d89-192">Você deve usar pelo menos dois registros de nameserver.</span><span class="sxs-lookup"><span data-stu-id="70d89-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="70d89-193">Se houver outros nameservers listados, você poderá excluí-los ou alterá-los para **NS3.DNS.Partner.microsoftonline.cn** e **NS4.DNS.Partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="70d89-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="70d89-194">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="70d89-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="70d89-195">Quando você alterar os registros NS do seu domínio para apontar para o Office 365 operado pelos nameservers da 21Vianet, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="70d89-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="70d89-196">Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="70d89-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="70d89-197">Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.</span><span class="sxs-lookup"><span data-stu-id="70d89-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="70d89-198">Por exemplo, aqui estão algumas etapas adicionais que podem ser necessárias para a hospedagem de email e de site:</span><span class="sxs-lookup"><span data-stu-id="70d89-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="70d89-199">Mova todos os endereços de email que usam seu domínio para a Microsoft 365 antes de alterar seus registros NS.</span><span class="sxs-lookup"><span data-stu-id="70d89-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="70d89-200">Você deseja adicionar um domínio atualmente usado com um site da Web, como www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="70d89-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="70d89-201">Você pode seguir as etapas ao adicionar o domínio para manter seu site hospedado onde o site está hospedado agora para que as pessoas possam acessar o site depois de alterar os registros NS do domínio para apontar para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70d89-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="70d89-202">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="70d89-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="70d89-203">Na página **domínios** , selecione o domínio e, em seguida, escolha **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="70d89-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="70d89-204">Em **configurações de DNS**, selecione **registros personalizados**e, em seguida, escolha **novo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="70d89-204">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="70d89-205">Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.</span><span class="sxs-lookup"><span data-stu-id="70d89-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="70d89-206">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="70d89-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="70d89-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="70d89-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="70d89-208">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="70d89-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
