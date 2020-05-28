---
title: Criar registros DNS no WiX para Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em WiX para a Microsoft.
ms.openlocfilehash: b5fe216e65954bbcbdd9a1da223258a8362743ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400287"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="e0400-103">Criar registros DNS no WiX para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0400-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="e0400-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="e0400-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e0400-105">Se o WiX for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e0400-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e0400-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="e0400-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="e0400-107">[Adicionar um registro txt para verificação](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="e0400-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="e0400-108">[Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e0400-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="e0400-109">[Adicione os cinco registros CNAME necessários para a Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e0400-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="e0400-110">[Adicione um registro txt para o SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="e0400-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="e0400-111">[Adicione os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e0400-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="e0400-112">Depois que você adicionar esses registros no WiX, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0400-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e0400-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e0400-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e0400-116">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="e0400-116">Add a TXT record for verification</span></span>
<span data-ttu-id="e0400-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e0400-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="e0400-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="e0400-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e0400-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="e0400-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e0400-122">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e0400-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e0400-123">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e0400-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e0400-124">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e0400-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e0400-125">Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="e0400-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e0400-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="e0400-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="e0400-127">**Host Name**</span></span> <br/> |<span data-ttu-id="e0400-128">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="e0400-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="e0400-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0400-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="e0400-130">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e0400-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="e0400-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e0400-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e0400-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0400-132">**Note:** This is an example.</span></span> <span data-ttu-id="e0400-133">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="e0400-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="e0400-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="e0400-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="e0400-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="e0400-136">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e0400-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e0400-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e0400-138">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="e0400-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e0400-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="e0400-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e0400-140">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="e0400-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e0400-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="e0400-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="e0400-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e0400-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="e0400-143">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="e0400-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e0400-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e0400-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e0400-147">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0400-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e0400-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e0400-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="e0400-149">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e0400-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e0400-150">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e0400-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e0400-151">Na página **meus domínios** , na área **caixas de correio** , selecione o link **configurar seus registros MX** .</span><span class="sxs-lookup"><span data-stu-id="e0400-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="e0400-152">Escolha **outro** na lista suspensa **provedor de email** .</span><span class="sxs-lookup"><span data-stu-id="e0400-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="e0400-153">Selecione **+ Adicionar outro**.</span><span class="sxs-lookup"><span data-stu-id="e0400-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="e0400-154">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e0400-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="e0400-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="e0400-155">**Host Name**</span></span>|<span data-ttu-id="e0400-156">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="e0400-156">**Points to**</span></span>|<span data-ttu-id="e0400-157">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="e0400-157">**Priority**</span></span>|<span data-ttu-id="e0400-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0400-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0400-159">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e0400-159">Automatically populated</span></span> <br/> | <span data-ttu-id="e0400-160">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e0400-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e0400-161">**Observação:** Acesse sua *\<domain-key\>* conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0400-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="e0400-162">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="e0400-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="e0400-163">,0</span><span class="sxs-lookup"><span data-stu-id="e0400-163">0</span></span>  <br/> <span data-ttu-id="e0400-164">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e0400-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="e0400-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-165">1 Hour</span></span>|
   
6. <span data-ttu-id="e0400-166">Se houver outros registros MX listados, exclua cada um deles.</span><span class="sxs-lookup"><span data-stu-id="e0400-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="e0400-167">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0400-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="e0400-168">Na caixa de diálogo de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0400-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e0400-169">Adicionar os cinco registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0400-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e0400-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e0400-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="e0400-171">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e0400-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e0400-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="e0400-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="e0400-173">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e0400-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e0400-174">Selecione **+ Adicionar outro** na linha **CNAME (alias)** do editor DNS para cada registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="e0400-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="e0400-175">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e0400-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="e0400-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="e0400-176">**Host Name**</span></span>|<span data-ttu-id="e0400-177">**Pontos de**</span><span class="sxs-lookup"><span data-stu-id="e0400-177">**Points to**</span></span>|<span data-ttu-id="e0400-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0400-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e0400-179">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="e0400-179">autodiscover</span></span>  <br/> |<span data-ttu-id="e0400-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e0400-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="e0400-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="e0400-182">sip</span><span class="sxs-lookup"><span data-stu-id="e0400-182">sip</span></span>  <br/> |<span data-ttu-id="e0400-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0400-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e0400-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="e0400-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e0400-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e0400-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0400-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="e0400-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="e0400-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e0400-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e0400-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e0400-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="e0400-190">1 hora</span><span class="sxs-lookup"><span data-stu-id="e0400-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="e0400-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e0400-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e0400-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e0400-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="e0400-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="e0400-194">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e0400-195">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e0400-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e0400-196">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="e0400-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e0400-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e0400-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0400-198">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="e0400-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e0400-199">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="e0400-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e0400-200">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0400-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e0400-201">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e0400-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="e0400-202">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e0400-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e0400-203">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e0400-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e0400-204">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e0400-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e0400-205">Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="e0400-206">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e0400-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="e0400-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="e0400-207">**Host Name**</span></span>|<span data-ttu-id="e0400-208">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="e0400-208">**TXT Value**</span></span>|<span data-ttu-id="e0400-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0400-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e0400-210">[deixe em branco]</span><span class="sxs-lookup"><span data-stu-id="e0400-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="e0400-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e0400-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e0400-212">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="e0400-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="e0400-213">TXT</span><span class="sxs-lookup"><span data-stu-id="e0400-213">TXT</span></span>  <br/> | <span data-ttu-id="e0400-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-214">1 Hour</span></span> |
   
5. <span data-ttu-id="e0400-215">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e0400-216">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e0400-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e0400-217">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0400-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e0400-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="e0400-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="e0400-219">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="e0400-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="e0400-220">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e0400-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e0400-221">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="e0400-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="e0400-222">Selecione **+ Adicionar outro** na linha **SRV** do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="e0400-223">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e0400-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="e0400-224">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="e0400-224">**Service**</span></span>|<span data-ttu-id="e0400-225">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="e0400-225">**Protocol**</span></span>|<span data-ttu-id="e0400-226">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e0400-226">**Name**</span></span>|<span data-ttu-id="e0400-227">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="e0400-227">**Weight**</span></span>|<span data-ttu-id="e0400-228">**Porta**</span><span class="sxs-lookup"><span data-stu-id="e0400-228">**Port**</span></span>|<span data-ttu-id="e0400-229">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e0400-229">**Target**</span></span>|<span data-ttu-id="e0400-230">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="e0400-230">**Priority**</span></span>|<span data-ttu-id="e0400-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0400-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0400-232">sip</span><span class="sxs-lookup"><span data-stu-id="e0400-232">sip</span></span>  |<span data-ttu-id="e0400-233">tls</span><span class="sxs-lookup"><span data-stu-id="e0400-233">tls</span></span>  |<span data-ttu-id="e0400-234">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e0400-234">Automatically populated</span></span> |<span data-ttu-id="e0400-235">1 </span><span class="sxs-lookup"><span data-stu-id="e0400-235">1</span></span>  |<span data-ttu-id="e0400-236">443</span><span class="sxs-lookup"><span data-stu-id="e0400-236">443</span></span>   |<span data-ttu-id="e0400-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0400-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="e0400-238">100</span><span class="sxs-lookup"><span data-stu-id="e0400-238">100</span></span> |<span data-ttu-id="e0400-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-239">1 Hour</span></span> |
|<span data-ttu-id="e0400-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="e0400-240">sipfed</span></span>|<span data-ttu-id="e0400-241">tcp</span><span class="sxs-lookup"><span data-stu-id="e0400-241">tcp</span></span> |<span data-ttu-id="e0400-242">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="e0400-242">Automatically populated</span></span>|<span data-ttu-id="e0400-243">1 </span><span class="sxs-lookup"><span data-stu-id="e0400-243">1</span></span> |<span data-ttu-id="e0400-244">5061</span><span class="sxs-lookup"><span data-stu-id="e0400-244">5061</span></span> |<span data-ttu-id="e0400-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0400-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="e0400-246">100</span><span class="sxs-lookup"><span data-stu-id="e0400-246">100</span></span> | <span data-ttu-id="e0400-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e0400-247">1 Hour</span></span> |
   
5. <span data-ttu-id="e0400-248">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="e0400-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="e0400-249">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e0400-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e0400-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e0400-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

