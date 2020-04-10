---
title: Criar registros DNS no site 123-reg.co.uk para Office 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em 123-reg.co.uk para o Office 365.
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211854"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="4a578-103">Criar registros DNS no site 123-reg.co.uk para Office 365</span><span class="sxs-lookup"><span data-stu-id="4a578-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="4a578-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="4a578-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4a578-105">Se você usa a 123-reg.co.uk como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="4a578-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4a578-106">Depois que você adicionar esses registros na 123-reg.co.uk, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a578-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="4a578-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="4a578-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a578-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4a578-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4a578-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="4a578-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4a578-110">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a578-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4a578-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="4a578-111">Add a TXT record for verification</span></span>
<span data-ttu-id="4a578-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4a578-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4a578-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="4a578-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a578-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="4a578-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4a578-117">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="4a578-117">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="4a578-118">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="4a578-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a578-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4a578-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4a578-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4a578-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4a578-121">Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** .</span><span class="sxs-lookup"><span data-stu-id="4a578-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4a578-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4a578-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4a578-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4a578-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="4a578-124">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="4a578-124">**Hostname**</span></span> <br/> |<span data-ttu-id="4a578-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4a578-125">**Type**</span></span> <br/> |<span data-ttu-id="4a578-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="4a578-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="4a578-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="4a578-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="4a578-128">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4a578-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4a578-129">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="4a578-129">**Note:** This is an example.</span></span> <span data-ttu-id="4a578-130">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a578-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="4a578-131">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="4a578-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="4a578-132">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a578-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="4a578-133">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="4a578-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4a578-134">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="4a578-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4a578-135">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="4a578-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4a578-136">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="4a578-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4a578-137">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="4a578-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4a578-138">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="4a578-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4a578-139">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="4a578-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4a578-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4a578-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4a578-141">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="4a578-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4a578-142">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a578-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="4a578-143">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="4a578-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="4a578-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4a578-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4a578-p107">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="4a578-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a578-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4a578-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4a578-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4a578-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4a578-149">Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** .</span><span class="sxs-lookup"><span data-stu-id="4a578-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4a578-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4a578-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4a578-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4a578-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4a578-152">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="4a578-152">**Hostname**</span></span>|<span data-ttu-id="4a578-153">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4a578-153">**Type**</span></span>|<span data-ttu-id="4a578-154">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="4a578-154">**Priority**</span></span>|<span data-ttu-id="4a578-155">**MX de destino**</span><span class="sxs-lookup"><span data-stu-id="4a578-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4a578-156">MX</span><span class="sxs-lookup"><span data-stu-id="4a578-156">MX</span></span>  <br/> |<span data-ttu-id="4a578-157">1</span><span class="sxs-lookup"><span data-stu-id="4a578-157">1</span></span>  <br/> <span data-ttu-id="4a578-158">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a578-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="4a578-159">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="4a578-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="4a578-161">**Observação:** Obtenha a sua \<chave-de-domínio\> através da conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a578-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="4a578-162">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="4a578-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar valores da tabela](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="4a578-164">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a578-164">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="4a578-166">Se houver outros registros MX, remova cada um deles escolhendo o ícone **Excluir (Lixeira)** do registro.</span><span class="sxs-lookup"><span data-stu-id="4a578-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Selecionar Delete (o ícone lixeira)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="4a578-168">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="4a578-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="4a578-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4a578-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4a578-p109">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="4a578-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a578-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4a578-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4a578-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4a578-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4a578-174">Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** .</span><span class="sxs-lookup"><span data-stu-id="4a578-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4a578-175">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="4a578-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="4a578-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4a578-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4a578-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4a578-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4a578-178">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="4a578-178">**Hostname**</span></span>|<span data-ttu-id="4a578-179">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4a578-179">**Type**</span></span>|<span data-ttu-id="4a578-180">**CNAME de destino**</span><span class="sxs-lookup"><span data-stu-id="4a578-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4a578-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4a578-181">autodiscover</span></span>  <br/> |<span data-ttu-id="4a578-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="4a578-182">CNAME</span></span>  <br/> |<span data-ttu-id="4a578-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="4a578-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4a578-185">sip</span><span class="sxs-lookup"><span data-stu-id="4a578-185">sip</span></span>  <br/> |<span data-ttu-id="4a578-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="4a578-186">CNAME</span></span>  <br/> |<span data-ttu-id="4a578-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4a578-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4a578-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4a578-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4a578-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="4a578-190">CNAME</span></span>  <br/> |<span data-ttu-id="4a578-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4a578-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4a578-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4a578-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4a578-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="4a578-194">CNAME</span></span>  <br/> |<span data-ttu-id="4a578-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="4a578-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="4a578-196">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4a578-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4a578-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4a578-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="4a578-198">CNAME</span></span>  <br/> |<span data-ttu-id="4a578-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="4a578-200">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Copiar e colar os valores da tabela](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="4a578-202">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a578-202">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="4a578-204">Adicione os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="4a578-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="4a578-205">Na seção **DNS avançado** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="4a578-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="4a578-206">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="4a578-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4a578-207">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="4a578-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4a578-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4a578-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a578-209">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="4a578-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4a578-210">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="4a578-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4a578-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a578-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4a578-212">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="4a578-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="4a578-213">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="4a578-213">Need examples?</span></span> <span data-ttu-id="4a578-214">Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). </span><span class="sxs-lookup"><span data-stu-id="4a578-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="4a578-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4a578-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="4a578-216">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="4a578-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="4a578-217">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="4a578-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a578-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4a578-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4a578-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4a578-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4a578-220">Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** .</span><span class="sxs-lookup"><span data-stu-id="4a578-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4a578-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4a578-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4a578-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4a578-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4a578-223">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="4a578-223">**Hostname**</span></span>|<span data-ttu-id="4a578-224">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4a578-224">**Type**</span></span>|<span data-ttu-id="4a578-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="4a578-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4a578-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="4a578-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="4a578-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4a578-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4a578-228">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="4a578-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="4a578-230">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a578-230">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="4a578-232">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="4a578-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="4a578-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4a578-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4a578-p112">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="4a578-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a578-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4a578-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4a578-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4a578-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4a578-238">Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** .</span><span class="sxs-lookup"><span data-stu-id="4a578-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4a578-239">Adicione o primeiro dos dois registros SRV:</span><span class="sxs-lookup"><span data-stu-id="4a578-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="4a578-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4a578-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4a578-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4a578-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a578-242">Nome do host</span><span class="sxs-lookup"><span data-stu-id="4a578-242">Hostname</span></span>|<span data-ttu-id="4a578-243">Tipo</span><span class="sxs-lookup"><span data-stu-id="4a578-243">Type</span></span>|<span data-ttu-id="4a578-244">Prioridade</span><span class="sxs-lookup"><span data-stu-id="4a578-244">Priority</span></span>|<span data-ttu-id="4a578-245">TTL</span><span class="sxs-lookup"><span data-stu-id="4a578-245">TTL</span></span>|<span data-ttu-id="4a578-246">SRV de destino</span><span class="sxs-lookup"><span data-stu-id="4a578-246">Destination SRV</span></span>|
    |<span data-ttu-id="4a578-247">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="4a578-247">_sip._tls</span></span>|<span data-ttu-id="4a578-248">SRV</span><span class="sxs-lookup"><span data-stu-id="4a578-248">SRV</span></span>|<span data-ttu-id="4a578-249">100</span><span class="sxs-lookup"><span data-stu-id="4a578-249">100</span></span>|<span data-ttu-id="4a578-250">3600</span><span class="sxs-lookup"><span data-stu-id="4a578-250">3600</span></span>|<span data-ttu-id="4a578-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="4a578-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="4a578-253">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="4a578-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="4a578-254">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="4a578-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4a578-255">SRV</span><span class="sxs-lookup"><span data-stu-id="4a578-255">SRV</span></span>|<span data-ttu-id="4a578-256">100</span><span class="sxs-lookup"><span data-stu-id="4a578-256">100</span></span>|<span data-ttu-id="4a578-257">3600</span><span class="sxs-lookup"><span data-stu-id="4a578-257">3600</span></span>|<span data-ttu-id="4a578-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4a578-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="4a578-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4a578-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="4a578-260">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="4a578-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar e colar os valores da tabela](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="4a578-262">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a578-262">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="4a578-264">Para adicionar o outro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="4a578-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="4a578-265">Na seção **DNS avançado** , crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="4a578-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="4a578-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4a578-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4a578-267">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="4a578-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4a578-268">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a578-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
