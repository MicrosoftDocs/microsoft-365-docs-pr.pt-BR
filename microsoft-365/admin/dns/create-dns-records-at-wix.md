---
title: Criar registros DNS no WiX para o Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no WiX para o Office 365.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211057"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="6e90f-103">Criar registros DNS no WiX para o Office 365</span><span class="sxs-lookup"><span data-stu-id="6e90f-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="6e90f-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6e90f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6e90f-105">Se o WiX for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6e90f-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6e90f-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="6e90f-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="6e90f-107">[Adicionar um registro txt para verificação](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="6e90f-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="6e90f-108">[Adicionar um registro MX para que o email do seu domínio seja fornecido para o Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="6e90f-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="6e90f-109">[Adicione os cinco registros CNAME necessários para o Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="6e90f-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="6e90f-110">[Adicione um registro txt para o SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="6e90f-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="6e90f-111">[Adicione os dois registros SRV necessários para o Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="6e90f-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="6e90f-112">Depois que você adicionar esses registros no WiX, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e90f-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6e90f-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6e90f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6e90f-116">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="6e90f-116">Add a TXT record for verification</span></span>
<span data-ttu-id="6e90f-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="6e90f-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="6e90f-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6e90f-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e90f-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="6e90f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6e90f-122">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="6e90f-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6e90f-123">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="6e90f-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6e90f-124">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="6e90f-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6e90f-125">Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="6e90f-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6e90f-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6e90f-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6e90f-127">**Host Name**</span></span> <br/> |<span data-ttu-id="6e90f-128">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="6e90f-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="6e90f-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6e90f-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="6e90f-130">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="6e90f-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="6e90f-131">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6e90f-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6e90f-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="6e90f-132">**Note:** This is an example.</span></span> <span data-ttu-id="6e90f-133">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e90f-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="6e90f-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="6e90f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="6e90f-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="6e90f-136">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6e90f-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6e90f-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6e90f-138">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="6e90f-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6e90f-139">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="6e90f-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6e90f-140">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="6e90f-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6e90f-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="6e90f-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="6e90f-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="6e90f-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="6e90f-143">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="6e90f-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6e90f-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6e90f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6e90f-147">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="6e90f-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6e90f-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="6e90f-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="6e90f-149">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="6e90f-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6e90f-150">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="6e90f-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6e90f-151">Na página **meus domínios** , na área **caixas de correio** , selecione o link **configurar seus registros MX** .</span><span class="sxs-lookup"><span data-stu-id="6e90f-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="6e90f-152">Escolha **outro** na lista suspensa **provedor de email** .</span><span class="sxs-lookup"><span data-stu-id="6e90f-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="6e90f-153">Selecione **+ Adicionar outro**.</span><span class="sxs-lookup"><span data-stu-id="6e90f-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="6e90f-154">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="6e90f-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6e90f-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6e90f-155">**Host Name**</span></span>|<span data-ttu-id="6e90f-156">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="6e90f-156">**Points to**</span></span>|<span data-ttu-id="6e90f-157">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="6e90f-157">**Priority**</span></span>|<span data-ttu-id="6e90f-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6e90f-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e90f-159">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="6e90f-159">Automatically populated</span></span> <br/> | <span data-ttu-id="6e90f-160">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6e90f-161">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e90f-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="6e90f-162">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="6e90f-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="6e90f-163">,0</span><span class="sxs-lookup"><span data-stu-id="6e90f-163">0</span></span>  <br/> <span data-ttu-id="6e90f-164">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span><span class="sxs-lookup"><span data-stu-id="6e90f-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="6e90f-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-165">1 Hour</span></span>|
   
6. <span data-ttu-id="6e90f-166">Se houver outros registros MX listados, exclua cada um deles.</span><span class="sxs-lookup"><span data-stu-id="6e90f-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="6e90f-167">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e90f-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="6e90f-168">Na caixa de diálogo de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e90f-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6e90f-169">Adicionar os cinco registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="6e90f-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="6e90f-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="6e90f-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="6e90f-171">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="6e90f-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6e90f-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="6e90f-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="6e90f-173">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="6e90f-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6e90f-174">Selecione **+ Adicionar outro** na linha **CNAME (alias)** do editor DNS para cada registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="6e90f-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="6e90f-175">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="6e90f-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6e90f-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6e90f-176">**Host Name**</span></span>|<span data-ttu-id="6e90f-177">**Pontos de**</span><span class="sxs-lookup"><span data-stu-id="6e90f-177">**Points to**</span></span>|<span data-ttu-id="6e90f-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6e90f-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e90f-179">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="6e90f-179">autodiscover</span></span>  <br/> |<span data-ttu-id="6e90f-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="6e90f-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="6e90f-182">sip</span><span class="sxs-lookup"><span data-stu-id="6e90f-182">sip</span></span>  <br/> |<span data-ttu-id="6e90f-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6e90f-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="6e90f-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6e90f-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6e90f-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="6e90f-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="6e90f-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6e90f-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6e90f-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6e90f-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="6e90f-190">1 hora</span><span class="sxs-lookup"><span data-stu-id="6e90f-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="6e90f-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6e90f-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6e90f-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="6e90f-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="6e90f-194">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6e90f-195">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6e90f-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6e90f-196">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="6e90f-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6e90f-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="6e90f-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e90f-198">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="6e90f-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6e90f-199">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="6e90f-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6e90f-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e90f-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6e90f-201">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="6e90f-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="6e90f-202">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="6e90f-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6e90f-203">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="6e90f-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6e90f-204">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="6e90f-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6e90f-205">Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="6e90f-206">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="6e90f-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6e90f-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6e90f-207">**Host Name**</span></span>|<span data-ttu-id="6e90f-208">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="6e90f-208">**TXT Value**</span></span>|<span data-ttu-id="6e90f-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6e90f-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e90f-210">[deixe em branco]</span><span class="sxs-lookup"><span data-stu-id="6e90f-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="6e90f-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6e90f-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6e90f-212">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="6e90f-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="6e90f-213">TXT</span><span class="sxs-lookup"><span data-stu-id="6e90f-213">TXT</span></span>  <br/> | <span data-ttu-id="6e90f-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-214">1 Hour</span></span> |
   
5. <span data-ttu-id="6e90f-215">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6e90f-216">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6e90f-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6e90f-217">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="6e90f-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6e90f-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="6e90f-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="6e90f-219">Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="6e90f-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6e90f-220">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="6e90f-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6e90f-221">Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** .</span><span class="sxs-lookup"><span data-stu-id="6e90f-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6e90f-222">Selecione **+ Adicionar outro** na linha **SRV** do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="6e90f-223">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="6e90f-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6e90f-224">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="6e90f-224">**Service**</span></span>|<span data-ttu-id="6e90f-225">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="6e90f-225">**Protocol**</span></span>|<span data-ttu-id="6e90f-226">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6e90f-226">**Name**</span></span>|<span data-ttu-id="6e90f-227">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="6e90f-227">**Weight**</span></span>|<span data-ttu-id="6e90f-228">**Porta**</span><span class="sxs-lookup"><span data-stu-id="6e90f-228">**Port**</span></span>|<span data-ttu-id="6e90f-229">**Destino**</span><span class="sxs-lookup"><span data-stu-id="6e90f-229">**Target**</span></span>|<span data-ttu-id="6e90f-230">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="6e90f-230">**Priority**</span></span>|<span data-ttu-id="6e90f-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6e90f-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e90f-232">sip</span><span class="sxs-lookup"><span data-stu-id="6e90f-232">sip</span></span>  |<span data-ttu-id="6e90f-233">tls</span><span class="sxs-lookup"><span data-stu-id="6e90f-233">tls</span></span>  |<span data-ttu-id="6e90f-234">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="6e90f-234">Automatically populated</span></span> |<span data-ttu-id="6e90f-235">1</span><span class="sxs-lookup"><span data-stu-id="6e90f-235">1</span></span>  |<span data-ttu-id="6e90f-236">443</span><span class="sxs-lookup"><span data-stu-id="6e90f-236">443</span></span>   |<span data-ttu-id="6e90f-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="6e90f-238">100</span><span class="sxs-lookup"><span data-stu-id="6e90f-238">100</span></span> |<span data-ttu-id="6e90f-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-239">1 Hour</span></span> |
|<span data-ttu-id="6e90f-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="6e90f-240">sipfed</span></span>|<span data-ttu-id="6e90f-241">tcp</span><span class="sxs-lookup"><span data-stu-id="6e90f-241">tcp</span></span> |<span data-ttu-id="6e90f-242">Preenchido automaticamente</span><span class="sxs-lookup"><span data-stu-id="6e90f-242">Automatically populated</span></span>|<span data-ttu-id="6e90f-243">1</span><span class="sxs-lookup"><span data-stu-id="6e90f-243">1</span></span> |<span data-ttu-id="6e90f-244">5061</span><span class="sxs-lookup"><span data-stu-id="6e90f-244">5061</span></span> |<span data-ttu-id="6e90f-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6e90f-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="6e90f-246">100</span><span class="sxs-lookup"><span data-stu-id="6e90f-246">100</span></span> | <span data-ttu-id="6e90f-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6e90f-247">1 Hour</span></span> |
   
5. <span data-ttu-id="6e90f-248">Selecione o botão **salvar DNS** na parte superior do editor de DNS.</span><span class="sxs-lookup"><span data-stu-id="6e90f-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6e90f-249">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6e90f-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6e90f-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6e90f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

