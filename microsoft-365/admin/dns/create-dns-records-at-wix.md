---
title: Criar registros DNS no WiX para Microsoft
f1.keywords:
- NOCSH
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em WiX para a Microsoft.
ms.openlocfilehash: 01317f7e2da87b532c93f12269fd65b7d4fe2dd6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656874"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="e2618-103">Criar registros DNS no WiX para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2618-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="e2618-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="e2618-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e2618-105">Se o WiX for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e2618-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="e2618-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="e2618-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="e2618-107">[Adicionar um registro txt para verificação](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="e2618-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="e2618-108">[Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e2618-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="e2618-109">[Adicione os cinco registros CNAME necessários para a Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e2618-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="e2618-110">[Adicione um registro txt para o SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="e2618-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="e2618-111">[Adicione os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e2618-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="e2618-112">Depois que você adicionar esses registros no WiX, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e2618-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e2618-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e2618-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e2618-116">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="e2618-116">Add a TXT record for verification</span></span>
<span data-ttu-id="e2618-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e2618-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="e2618-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="e2618-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2618-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="e2618-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="e2618-122">O WIX não oferece suporte a entradas DNS para subdomínios.</span><span class="sxs-lookup"><span data-stu-id="e2618-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="e2618-123">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e2618-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e2618-124">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e2618-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e2618-125">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e2618-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e2618-126">Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="e2618-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e2618-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="e2618-128">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="e2618-128">Host Name</span></span> <br/> | <span data-ttu-id="e2618-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="e2618-129">TXT Value</span></span> <br/> | <span data-ttu-id="e2618-130">TTL</span><span class="sxs-lookup"><span data-stu-id="e2618-130">TTL</span></span> <br/> |
   |<span data-ttu-id="e2618-131">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e2618-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="e2618-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e2618-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e2618-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e2618-133">**Note:** This is an example.</span></span> <span data-ttu-id="e2618-134">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="e2618-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="e2618-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="e2618-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="e2618-136">1 hora</span><span class="sxs-lookup"><span data-stu-id="e2618-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="e2618-137">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e2618-138">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e2618-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e2618-139">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="e2618-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e2618-140">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="e2618-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e2618-141">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="e2618-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e2618-142">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="e2618-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="e2618-143">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e2618-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="e2618-144">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="e2618-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e2618-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e2618-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e2618-148">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e2618-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e2618-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e2618-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="e2618-150">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e2618-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e2618-151">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e2618-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e2618-152">Na página **meus domínios** , na área **caixas de correio** , selecione o link **configurar seus registros MX** .</span><span class="sxs-lookup"><span data-stu-id="e2618-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="e2618-153">Escolha **outro** na lista suspensa **provedor de email** .</span><span class="sxs-lookup"><span data-stu-id="e2618-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="e2618-154">Selecione **+ Adicionar outro**.</span><span class="sxs-lookup"><span data-stu-id="e2618-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="e2618-155">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e2618-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="e2618-156">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="e2618-156">Host Name</span></span> | <span data-ttu-id="e2618-157">Points to </span><span class="sxs-lookup"><span data-stu-id="e2618-157">Points to</span></span> | <span data-ttu-id="e2618-158">Prioridade</span><span class="sxs-lookup"><span data-stu-id="e2618-158">Priority</span></span> | <span data-ttu-id="e2618-159">TTL</span><span class="sxs-lookup"><span data-stu-id="e2618-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="e2618-160">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e2618-160">Automatically populated</span></span> <br/> | <span data-ttu-id="e2618-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e2618-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e2618-162">**Observação:** Acesse sua  *\<domain-key\>*  conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e2618-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="e2618-163">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="e2618-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="e2618-164">,0</span><span class="sxs-lookup"><span data-stu-id="e2618-164">0</span></span>  <br/> <span data-ttu-id="e2618-165">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e2618-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="e2618-166">1 hora</span><span class="sxs-lookup"><span data-stu-id="e2618-166">1 Hour</span></span>|
   
6. <span data-ttu-id="e2618-167">Se houver outros registros MX listados, exclua cada um deles.</span><span class="sxs-lookup"><span data-stu-id="e2618-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="e2618-168">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2618-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="e2618-169">Na caixa de diálogo de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2618-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e2618-170">Adicionar os cinco registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2618-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e2618-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e2618-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="e2618-172">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e2618-172">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e2618-173">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="e2618-173">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="e2618-174">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e2618-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e2618-175">Selecione **+ Adicionar outro** na linha **CNAME (alias)** do editor DNS para cada registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="e2618-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="e2618-176">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e2618-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="e2618-177">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="e2618-177">Host Name</span></span> | <span data-ttu-id="e2618-178">Points to </span><span class="sxs-lookup"><span data-stu-id="e2618-178">Points to</span></span> | <span data-ttu-id="e2618-179">TTL</span><span class="sxs-lookup"><span data-stu-id="e2618-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="e2618-180">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="e2618-180">autodiscover</span></span>  <br/> |<span data-ttu-id="e2618-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e2618-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="e2618-182">1 hora</span><span class="sxs-lookup"><span data-stu-id="e2618-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="e2618-183">sip</span><span class="sxs-lookup"><span data-stu-id="e2618-183">sip</span></span>  <br/> |<span data-ttu-id="e2618-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2618-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e2618-185">1 hora</span><span class="sxs-lookup"><span data-stu-id="e2618-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="e2618-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e2618-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e2618-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2618-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="e2618-188">1 hora</span><span class="sxs-lookup"><span data-stu-id="e2618-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="e2618-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e2618-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e2618-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e2618-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="e2618-191">1 hora</span><span class="sxs-lookup"><span data-stu-id="e2618-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="e2618-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e2618-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e2618-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e2618-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="e2618-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e2618-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="e2618-195">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e2618-196">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e2618-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e2618-197">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="e2618-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e2618-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e2618-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2618-199">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="e2618-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e2618-200">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="e2618-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e2618-201">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e2618-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e2618-202">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e2618-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="e2618-203">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e2618-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e2618-204">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e2618-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e2618-205">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e2618-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e2618-206">Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="e2618-207">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e2618-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="e2618-208">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="e2618-208">Host Name</span></span> | <span data-ttu-id="e2618-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="e2618-209">TXT Value</span></span> | <span data-ttu-id="e2618-210">TTL</span><span class="sxs-lookup"><span data-stu-id="e2618-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="e2618-211">[deixe em branco]</span><span class="sxs-lookup"><span data-stu-id="e2618-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="e2618-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e2618-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e2618-213">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="e2618-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="e2618-214">TXT</span><span class="sxs-lookup"><span data-stu-id="e2618-214">TXT</span></span>  <br/> | <span data-ttu-id="e2618-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e2618-215">1 Hour</span></span> |
   
5. <span data-ttu-id="e2618-216">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e2618-217">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e2618-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e2618-218">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2618-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e2618-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="e2618-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="e2618-220">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e2618-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e2618-221">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e2618-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e2618-222">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e2618-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e2618-223">Selecione **+ Adicionar outro** na linha **SRV** do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="e2618-224">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e2618-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="e2618-225">Serviço</span><span class="sxs-lookup"><span data-stu-id="e2618-225">Service</span></span> | <span data-ttu-id="e2618-226">Protocolo</span><span class="sxs-lookup"><span data-stu-id="e2618-226">Protocol</span></span> | <span data-ttu-id="e2618-227">Nome</span><span class="sxs-lookup"><span data-stu-id="e2618-227">Name</span></span> | <span data-ttu-id="e2618-228">Peso</span><span class="sxs-lookup"><span data-stu-id="e2618-228">Weight</span></span> | <span data-ttu-id="e2618-229">Porta</span><span class="sxs-lookup"><span data-stu-id="e2618-229">Port</span></span> | <span data-ttu-id="e2618-230">Target</span><span class="sxs-lookup"><span data-stu-id="e2618-230">Target</span></span> | <span data-ttu-id="e2618-231">Prioridade</span><span class="sxs-lookup"><span data-stu-id="e2618-231">Priority</span></span> | <span data-ttu-id="e2618-232">TTL</span><span class="sxs-lookup"><span data-stu-id="e2618-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="e2618-233">sip</span><span class="sxs-lookup"><span data-stu-id="e2618-233">sip</span></span>  |<span data-ttu-id="e2618-234">tls</span><span class="sxs-lookup"><span data-stu-id="e2618-234">tls</span></span>  |<span data-ttu-id="e2618-235">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e2618-235">Automatically populated</span></span> |<span data-ttu-id="e2618-236">1 </span><span class="sxs-lookup"><span data-stu-id="e2618-236">1</span></span>  |<span data-ttu-id="e2618-237">443</span><span class="sxs-lookup"><span data-stu-id="e2618-237">443</span></span>   |<span data-ttu-id="e2618-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2618-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="e2618-239">100</span><span class="sxs-lookup"><span data-stu-id="e2618-239">100</span></span> |<span data-ttu-id="e2618-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e2618-240">1 Hour</span></span> |
   |<span data-ttu-id="e2618-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="e2618-241">sipfed</span></span>|<span data-ttu-id="e2618-242">tcp</span><span class="sxs-lookup"><span data-stu-id="e2618-242">tcp</span></span> |<span data-ttu-id="e2618-243">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e2618-243">Automatically populated</span></span>|<span data-ttu-id="e2618-244">1 </span><span class="sxs-lookup"><span data-stu-id="e2618-244">1</span></span> |<span data-ttu-id="e2618-245">5061</span><span class="sxs-lookup"><span data-stu-id="e2618-245">5061</span></span> |<span data-ttu-id="e2618-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e2618-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="e2618-247">100</span><span class="sxs-lookup"><span data-stu-id="e2618-247">100</span></span> | <span data-ttu-id="e2618-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e2618-248">1 Hour</span></span> |
   
5. <span data-ttu-id="e2618-249">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e2618-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e2618-250">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e2618-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e2618-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e2618-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
