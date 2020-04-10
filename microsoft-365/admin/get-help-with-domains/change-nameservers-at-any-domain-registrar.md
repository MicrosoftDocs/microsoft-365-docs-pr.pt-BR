---
title: Alterar os servidores de nomes para configurar o Office 365 com qualquer registrador de domínios
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Saiba como adicionar e configurar seu domínio no Office 365 para que seus serviços como o email e o Skype for Business online usem seu próprio nome de domínio.
ms.custom: okr_smb
ms.openlocfilehash: 838025002443ec35787ea91775c60d3829545af4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210487"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="04b00-103">Alterar os servidores de nomes para configurar o Office 365 com qualquer registrador de domínios</span><span class="sxs-lookup"><span data-stu-id="04b00-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="04b00-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="04b00-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="04b00-105">Confira primeiro [configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para ver se temos instruções para o seu registrador.</span><span class="sxs-lookup"><span data-stu-id="04b00-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="04b00-106">Siga estas instruções para adicionar e configurar seu domínio no Office 365 para que seus serviços, como o email e o Skype for Business Online, usem seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="04b00-107">Para fazer isso, você precisa verificar o domínio e alterar os servidores de nomes do domínio no Office 365 para que os registros DNS corretos possam ser configurados para você.</span><span class="sxs-lookup"><span data-stu-id="04b00-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="04b00-108">Siga estas etapas se as instruções a seguir descrevem sua situação:</span><span class="sxs-lookup"><span data-stu-id="04b00-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="04b00-109">Se você tiver seu próprio domínio e quiser configurá-lo para funcionar com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="04b00-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="04b00-p102">Se você quiser que o Office 365 gerencie seus registros DNS. Se preferir, é possível[ gerenciar seus próprios registros DNS ](../setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="04b00-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="04b00-112">Adicionar um registro TXT ou MX para verificação</span><span class="sxs-lookup"><span data-stu-id="04b00-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="04b00-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="04b00-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="04b00-p103">Você criará apenas um desses registros. O TXT é o tipo de registro preferencial, mas alguns provedores de host DNS não são compatíveis com ele. Nesse caso, você pode criar um registro MX como alternativa.</span><span class="sxs-lookup"><span data-stu-id="04b00-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="04b00-p104">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04b00-p105">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="04b00-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="04b00-120">Encontre a área no site do provedor de Hospedagem de DNS onde você pode criar um novo registro</span><span class="sxs-lookup"><span data-stu-id="04b00-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="04b00-121">Entre no site do seu provedor de hospedagem DNS.</span><span class="sxs-lookup"><span data-stu-id="04b00-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="04b00-122">Escolha seu domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="04b00-123">Localize a página na qual você pode editar registros DNS para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="04b00-124">Criar o registro</span><span class="sxs-lookup"><span data-stu-id="04b00-124">Create the record</span></span>

<span data-ttu-id="04b00-125">Caso esteja criando um registro TXT ou um registro MX, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="04b00-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="04b00-126">**Se você criar um registro TXT, use estes valores:**</span><span class="sxs-lookup"><span data-stu-id="04b00-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04b00-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="04b00-127">**Record Type**</span></span> <br/> |<span data-ttu-id="04b00-128">**Alias** ou **Nome do host**</span><span class="sxs-lookup"><span data-stu-id="04b00-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="04b00-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="04b00-129">**Value**</span></span> <br/> |<span data-ttu-id="04b00-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="04b00-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="04b00-131">TXT</span><span class="sxs-lookup"><span data-stu-id="04b00-131">TXT</span></span>  <br/> |<span data-ttu-id="04b00-132">Siga um destes procedimentos: Digite **@**, deixe o campo vazio ou digite o seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="04b00-133">> [!NOTE]> Hosts DNS diferentes têm requisitos diferentes para este campo.</span><span class="sxs-lookup"><span data-stu-id="04b00-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="04b00-134">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="04b00-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="04b00-p106">> [!NOTE]> Esse é um exemplo. Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.          [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="04b00-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="04b00-138">Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="04b00-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="04b00-139">**Se você criar um registro MX, use estes valores:**</span><span class="sxs-lookup"><span data-stu-id="04b00-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04b00-140">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="04b00-140">**Record Type**</span></span>|<span data-ttu-id="04b00-141">**Alias** ou **Nome do host**</span><span class="sxs-lookup"><span data-stu-id="04b00-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="04b00-142">**Valor**</span><span class="sxs-lookup"><span data-stu-id="04b00-142">**Value**</span></span>|<span data-ttu-id="04b00-143">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="04b00-143">**Priority**</span></span>|<span data-ttu-id="04b00-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="04b00-144">**TTL**</span></span>|
|<span data-ttu-id="04b00-145">MX</span><span class="sxs-lookup"><span data-stu-id="04b00-145">MX</span></span>|<span data-ttu-id="04b00-146">Digite **@** ou seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="04b00-p107">MS = ms *XXXXXXXX* > [!NOTE]> Esse é um exemplo. Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.          [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="04b00-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="04b00-150">Para **Priority**, para evitar conflitos com o registro MX usado para o fluxo de email, use uma prioridade menor do que a prioridade de qualquer registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="04b00-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="04b00-151">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="04b00-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="04b00-152">Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.</span><span class="sxs-lookup"><span data-stu-id="04b00-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="04b00-153">Salvar o registro</span><span class="sxs-lookup"><span data-stu-id="04b00-153">Save the record</span></span>

<span data-ttu-id="04b00-154">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="04b00-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="04b00-155">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="04b00-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="04b00-156">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="04b00-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="04b00-157">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="04b00-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="04b00-158">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="04b00-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="04b00-159">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="04b00-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="04b00-p109">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="04b00-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="04b00-163">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="04b00-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="04b00-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="04b00-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="04b00-p110">Quando você chegar à última etapa do assistente de configuração de domínios no Office 365, haverá uma tarefa restante. Para configurar seu domínio com os serviços do Office 365, como email, altere os registros do servidor de nome do seu domínio (ou NS) no seu registrador de domínios para apontar para os servidores de nome primário e secundário do Office 365. Depois, como o Office 365 hospeda seu DNS, os registros DNS necessários para seus serviços são configurados automaticamente para você. Você pode atualizar os registros de servidor de nome por conta própria seguindo as etapas que o seu registrador de domínio provavelmente descreve no conteúdo de ajuda do próprio site. Se você não estiver familiarizado com DNS, contate o suporte no registrador de domínios.</span><span class="sxs-lookup"><span data-stu-id="04b00-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="04b00-170">Para alterar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04b00-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="04b00-171">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="04b00-172">Crie dois registros de servidor de nomes ou edite os registros de servidor de nomes existentes para que eles correspondam aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="04b00-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="04b00-173">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="04b00-173">First nameserver</span></span>  <br/> |<span data-ttu-id="04b00-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="04b00-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="04b00-175">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="04b00-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="04b00-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="04b00-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="04b00-177">Você deve usar pelo menos dois registros de nameserver.</span><span class="sxs-lookup"><span data-stu-id="04b00-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="04b00-178">Se houver outros nameservers listados, você poderá excluí-los ou alterá-los para **NS3.bdm.microsoftonline.com** e **NS4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="04b00-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="04b00-179">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="04b00-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="04b00-p112">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nome do Office 365, todos os serviços que estão atualmente associados a seu domínio serão afetados. Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias. Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.</span><span class="sxs-lookup"><span data-stu-id="04b00-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="04b00-183">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="04b00-184">Crie dois registros de servidor de nomes ou edite os registros de servidor de nomes existentes para que eles correspondam aos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="04b00-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="04b00-185">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="04b00-185">First nameserver</span></span>  <br/> |<span data-ttu-id="04b00-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="04b00-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="04b00-187">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="04b00-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="04b00-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="04b00-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="04b00-189">Você deve usar pelo menos dois registros de nameserver.</span><span class="sxs-lookup"><span data-stu-id="04b00-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="04b00-190">Se houver outros nameservers listados, você poderá excluí-los ou alterá-los para **NS3.DNS.Partner.microsoftonline.cn** e **NS4.DNS.Partner.microsoftonline.cn**.</span><span class="sxs-lookup"><span data-stu-id="04b00-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="04b00-191">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="04b00-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="04b00-192">Quando você alterar os registros NS do seu domínio para apontar para o Office 365 operado pelos nameservers da 21Vianet, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="04b00-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="04b00-193">Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="04b00-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="04b00-194">Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível.</span><span class="sxs-lookup"><span data-stu-id="04b00-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="04b00-195">Por exemplo, aqui estão algumas etapas adicionais que podem ser necessárias para a hospedagem de email e de site:</span><span class="sxs-lookup"><span data-stu-id="04b00-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="04b00-196">Mova todos os endereços de email usados em seu domínio para o Office 365 antes de alterar seus registros NS.</span><span class="sxs-lookup"><span data-stu-id="04b00-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="04b00-197">Você deseja adicionar um domínio atualmente usado com um site da Web, como www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="04b00-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="04b00-198">Você pode seguir as etapas ao adicionar o domínio para manter seu site hospedado onde o site está hospedado agora para que as pessoas possam acessar o site depois de alterar os registros NS do domínio para apontar para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="04b00-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="04b00-199">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="04b00-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="04b00-200">Selecione um domínio na página Domínios.</span><span class="sxs-lookup"><span data-stu-id="04b00-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="04b00-201">Em **configurações de DNS**, selecione **registros personalizados**e, em seguida, escolha **novo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="04b00-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="04b00-202">Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.</span><span class="sxs-lookup"><span data-stu-id="04b00-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="04b00-203">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04b00-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="04b00-p116">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="04b00-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

