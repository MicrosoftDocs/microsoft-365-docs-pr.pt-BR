---
title: Alterar nameservers para configurar Microsoft 365 com qualquer registrador de domínios
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Saiba como adicionar e configurar seu domínio no Microsoft 365 para que seus serviços, como email e Skype for Business Online, usem seu próprio nome de domínio.
ms.openlocfilehash: c6394b505e025c565713aae753879601f5a6aecf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635433"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="fc6c9-103">Alterar nameservers para configurar Microsoft 365 com qualquer registrador de domínios</span><span class="sxs-lookup"><span data-stu-id="fc6c9-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="fc6c9-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fc6c9-105">Siga estas instruções para adicionar e configurar seu domínio no Microsoft 365 para que seus serviços como email e Teams usem seu próprio nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="fc6c9-106">Para fazer isso, você verificará seu domínio e alterará os nameservers do seu domínio para Microsoft 365 para que os registros DNS corretos possam ser definidos para você.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="fc6c9-107">Siga estas etapas se as instruções a seguir descreverem sua situação:</span><span class="sxs-lookup"><span data-stu-id="fc6c9-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="fc6c9-108">Você tem seu próprio domínio e deseja defini-lo para trabalhar com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="fc6c9-109">Você deseja Microsoft 365 gerenciar seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="fc6c9-110">Se preferir, é possível[ gerenciar seus próprios registros DNS ](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="fc6c9-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="fc6c9-111">Adicionar um registro TXT ou MX para verificação</span><span class="sxs-lookup"><span data-stu-id="fc6c9-111">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="fc6c9-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fc6c9-112"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="fc6c9-p103">Você criará apenas um desses registros. O TXT é o tipo de registro preferencial, mas alguns provedores de host DNS não são compatíveis com ele. Nesse caso, você pode criar um registro MX como alternativa.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="fc6c9-p104">Antes de usar o seu domínio com o Microsoft 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova ao Microsoft 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc6c9-p105">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="fc6c9-119">Encontre a área no site do provedor de hospedagem DNS onde você pode criar um novo registro</span><span class="sxs-lookup"><span data-stu-id="fc6c9-119">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="fc6c9-120">Entre no site do seu provedor de hospedagem DNS.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-120">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="fc6c9-121">Escolha seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-121">Choose your domain.</span></span>
    
3. <span data-ttu-id="fc6c9-122">Localize a página na qual você pode editar registros DNS para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-122">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="fc6c9-123">Criar o registro</span><span class="sxs-lookup"><span data-stu-id="fc6c9-123">Create the record</span></span>

<span data-ttu-id="fc6c9-124">Caso esteja criando um registro TXT ou um registro MX, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fc6c9-124">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="fc6c9-125">**Se você criar um registro TXT, use estes valores:**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-125">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc6c9-126">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-126">**Record Type**</span></span> <br/> |<span data-ttu-id="fc6c9-127">**Alias** ou **Nome do host**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-127">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="fc6c9-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-128">**Value**</span></span> <br/> |<span data-ttu-id="fc6c9-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="fc6c9-130">TXT</span><span class="sxs-lookup"><span data-stu-id="fc6c9-130">TXT</span></span>  <br/> |<span data-ttu-id="fc6c9-131">Siga um destes procedimentos: Digite **@**, deixe o campo vazio ou digite o seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-131">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="fc6c9-132">> [!NOTE]> Hosts DNS diferentes têm requisitos diferentes para este campo.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-132">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="fc6c9-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fc6c9-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fc6c9-134">> [!NOTE]> Esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-134">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="fc6c9-135">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-135">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="fc6c9-136">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="fc6c9-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fc6c9-137">Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-137">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="fc6c9-138">**Se você criar um registro MX, use estes valores:**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-138">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc6c9-139">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-139">**Record Type**</span></span>|<span data-ttu-id="fc6c9-140">**Alias** ou **Nome do host**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-140">**Alias** or **Host Name**</span></span>|<span data-ttu-id="fc6c9-141">**Valor**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-141">**Value**</span></span>|<span data-ttu-id="fc6c9-142">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-142">**Priority**</span></span>|<span data-ttu-id="fc6c9-143">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-143">**TTL**</span></span>|
|<span data-ttu-id="fc6c9-144">MX</span><span class="sxs-lookup"><span data-stu-id="fc6c9-144">MX</span></span>|<span data-ttu-id="fc6c9-145">Digite **@** ou seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-145">Type either **@** or your domain name.</span></span> |<span data-ttu-id="fc6c9-146">MS = ms *XXXXXXXX* > [!NOTE]> Esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-146">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="fc6c9-147">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-147">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="fc6c9-148">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="fc6c9-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fc6c9-149">Para **Priority**, para evitar conflitos com o registro MX usado para o fluxo de email, use uma prioridade menor do que a prioridade de qualquer registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-149">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="fc6c9-150">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="fc6c9-150">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="fc6c9-151">Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-151">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="fc6c9-152">Salvar o registro</span><span class="sxs-lookup"><span data-stu-id="fc6c9-152">Save the record</span></span>

<span data-ttu-id="fc6c9-153">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="fc6c9-154">Quando o Microsoft 365 encontrar o registros TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-154">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="fc6c9-155">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fc6c9-156">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="fc6c9-157">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-157">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="fc6c9-158">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fc6c9-p109">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fc6c9-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="fc6c9-162">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="fc6c9-162">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="fc6c9-163"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="fc6c9-163"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="fc6c9-164">Quando você chegar à última etapa do assistente de configuração de domínios no Microsoft 365, você terá uma tarefa restante.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-164">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="fc6c9-165">Para configurar seu domínio com serviços Microsoft 365, como email, você altera os registros de nameserver (ou NS Microsoft 365) do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-165">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="fc6c9-166">Em seguida, como Microsoft 365 hospeda seu DNS, os registros DNS necessários para seus serviços são definidos automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-166">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="fc6c9-167">Você pode atualizar os registros de servidor de nomes por conta própria seguindo as etapas que seu registrador de domínio pode fornecer no conteúdo de Ajuda no site deles.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-167">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="fc6c9-168">Se você não estiver familiarizado com DNS, contate o suporte no registrador de domínios.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-168">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="fc6c9-169">Para alterar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="fc6c9-169">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="fc6c9-170">Encontre a área no site do registrador de domínios onde você pode alterar os nameservers para seu domínio ou uma área onde você pode usar nameservers personalizados.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-170">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="fc6c9-171">Crie registros de nameserver ou edite os registros de nameserver existentes para corresponder aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fc6c9-171">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="fc6c9-172">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="fc6c9-172">First nameserver</span></span>  <br/> |<span data-ttu-id="fc6c9-173">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc6c9-173">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc6c9-174">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="fc6c9-174">Second nameserver</span></span>  <br/> |<span data-ttu-id="fc6c9-175">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc6c9-175">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc6c9-176">Terceiro nameserver</span><span class="sxs-lookup"><span data-stu-id="fc6c9-176">Third nameserver</span></span>  <br/> |<span data-ttu-id="fc6c9-177">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc6c9-177">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc6c9-178">Quarto nameserver</span><span class="sxs-lookup"><span data-stu-id="fc6c9-178">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="fc6c9-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc6c9-179">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="fc6c9-180">É melhor adicionar todos os quatro registros, mas se o registrador tiver suporte apenas para dois, adicione ns1.bdm.microsoftonline.com **e** **ns2.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-180">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="fc6c9-181">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-181">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="fc6c9-182">Quando você altera os registros NS do seu domínio para apontar para os Microsoft 365 de nomes, todos os serviços associados ao seu domínio são afetados.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-182">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="fc6c9-183">Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-183">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="fc6c9-184">Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-184">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="fc6c9-185">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-185">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="fc6c9-186">Crie dois registros de servidor de nomes ou edite os registros de servidor de nomes existentes para que eles correspondam aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fc6c9-186">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="fc6c9-187">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="fc6c9-187">First nameserver</span></span>  <br/> |<span data-ttu-id="fc6c9-188">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="fc6c9-188">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="fc6c9-189">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="fc6c9-189">Second nameserver</span></span>  <br/> |<span data-ttu-id="fc6c9-190">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="fc6c9-190">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="fc6c9-191">Você deve usar pelo menos dois registros de nameserver.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-191">You should use at least two nameserver records.</span></span> <span data-ttu-id="fc6c9-192">Se houver outros servidores de nomes listados, você poderá excluí-los ou alterá-los para ns3.dns.partner.microsoftonline.cn **e** **ns4.dns.partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-192">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="fc6c9-193">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-193">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="fc6c9-194">Quando você altera os registros NS do seu domínio para apontar para o Office 365 operado por servidores de nomes da 21Vianet, todos os serviços associados ao seu domínio são afetados.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-194">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="fc6c9-195">Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-195">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="fc6c9-196">Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-196">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="fc6c9-197">Por exemplo, aqui estão algumas etapas adicionais que podem ser necessárias para a hospedagem de email e de site:</span><span class="sxs-lookup"><span data-stu-id="fc6c9-197">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="fc6c9-198">Mova todos os endereços de email que usam seu domínio para Microsoft 365 antes de alterar seus registros NS.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-198">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="fc6c9-199">Você deseja adicionar um domínio atualmente usado com um site da Web, como www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="fc6c9-199">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="fc6c9-200">Você pode seguir as etapas enquanto adiciona o domínio para manter seu site hospedado onde o site está hospedado agora para que as pessoas ainda possam chegar ao site depois que você alterar os registros NS do domínio para apontar para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-200">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="fc6c9-201">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-201">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="fc6c9-202">Selecione um domínio na página **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-202">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="fc6c9-203">Na página detalhes do domínio, selecione a **guia Registros DNS.**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-203">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="fc6c9-204">Selecione **Adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-204">Select **Add record**.</span></span>

5. <span data-ttu-id="fc6c9-205">No painel **Adicionar um registro DNS personalizado,** na lista suspenso **Tipo,** selecione **A (Endereço)**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-205">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="fc6c9-206">Na caixa **Nome do Host ou Alias,** digite **@** .</span><span class="sxs-lookup"><span data-stu-id="fc6c9-206">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="fc6c9-207">Na caixa **Endereço IP,** digite o endereço IP estático para o site onde ele está hospedado no momento.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-207">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="fc6c9-208">Por exemplo, 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-208">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="fc6c9-209">Esse deve ser um _endereço_ IP estático para o site, não um _endereço_ IP dinâmico.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-209">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="fc6c9-210">Para garantir que você possa obter um endereço IP estático para seu site público, verifique com o site que hospeda seu site.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-210">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="fc6c9-211">Se você quiser alterar a configuração TTL do registro, selecione um novo período de tempo na lista suspenso **TTL.**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-211">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="fc6c9-212">Caso contrário, continue para a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-212">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="fc6c9-213">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-213">Select **Save**.</span></span> 
    
<span data-ttu-id="fc6c9-214">Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-214">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="fc6c9-215">Selecione **Adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-215">Select **Add record**.</span></span>

3.  <span data-ttu-id="fc6c9-216">No painel **Adicionar um registro DNS personalizado,** na lista suspenso **Tipo,** selecione **CNAME (Alias)**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-216">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="fc6c9-217">Na caixa **Nome do Host ou Alias,** digite **www**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-217">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="fc6c9-218">Na caixa **Pontos para endereço,** digite o FQDN (nome de domínio totalmente qualificado) para seu site.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-218">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="fc6c9-219">Por exemplo, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-219">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="fc6c9-220">Se você quiser alterar a configuração TTL do registro, selecione um novo período de tempo na lista suspenso **TTL.**</span><span class="sxs-lookup"><span data-stu-id="fc6c9-220">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="fc6c9-221">Caso contrário, continue para a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-221">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="fc6c9-222">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-222">Select **Save**.</span></span>

<span data-ttu-id="fc6c9-223">Depois que os registros do nameserver são atualizados para apontar para a Microsoft, a configuração do domínio é concluída.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-223">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="fc6c9-224">O email é roteado para a Microsoft e o tráfego para seu endereço de site continua a ir para o host do site atual.'</span><span class="sxs-lookup"><span data-stu-id="fc6c9-224">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="fc6c9-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fc6c9-226">Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fc6c9-226">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="fc6c9-227">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="fc6c9-227">Related content</span></span>

<span data-ttu-id="fc6c9-228">[Adicionar registros DNS para conectar seu domínio](create-dns-records-at-any-dns-hosting-provider.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="fc6c9-228">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="fc6c9-229">[Localizar e corrigir problemas após adicionar seu domínio ou registros DNS ](find-and-fix-issues.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="fc6c9-229">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="fc6c9-230">[Gerenciar domínios](index.yml) (página de link)</span><span class="sxs-lookup"><span data-stu-id="fc6c9-230">[Manage domains](index.yml) (link page)</span></span>
