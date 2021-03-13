---
title: Criar registros DNS no 123-reg.co.uk para a Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços 123-reg.co.uk para a Microsoft.
ms.openlocfilehash: 3c9af6909f37082a63170adac94ac3d92b717ad1
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758899"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="d665a-103">Criar registros DNS no 123-reg.co.uk para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d665a-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="d665a-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="d665a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d665a-105">Se você usa a 123-reg.co.uk como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="d665a-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d665a-106">Depois de adicionar esses registros no 123-reg.co.uk, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d665a-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="d665a-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d665a-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d665a-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d665a-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d665a-109">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d665a-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d665a-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d665a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d665a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d665a-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d665a-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="d665a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d665a-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="d665a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d665a-p104">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d665a-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d665a-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="d665a-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d665a-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d665a-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="d665a-120">Na página **Gerenciar seu DNS,** selecione a **guia DNS** Avançado.</span><span class="sxs-lookup"><span data-stu-id="d665a-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="d665a-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d665a-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d665a-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d665a-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="d665a-123">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d665a-123">**Hostname**</span></span> <br/> |<span data-ttu-id="d665a-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d665a-124">**Type**</span></span> <br/> |<span data-ttu-id="d665a-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="d665a-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="d665a-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="d665a-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="d665a-127">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d665a-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d665a-128">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d665a-128">**Note:** This is an example.</span></span> <span data-ttu-id="d665a-129">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="d665a-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d665a-130">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d665a-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="d665a-131">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d665a-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="d665a-132">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="d665a-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d665a-133">Agora que você adicionou o registro no site do registrador de domínios, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="d665a-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="d665a-134">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="d665a-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d665a-135">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="d665a-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d665a-136">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="d665a-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d665a-137">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d665a-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d665a-138">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d665a-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d665a-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d665a-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d665a-140">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d665a-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d665a-141">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d665a-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d665a-142">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d665a-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d665a-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d665a-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d665a-p107">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d665a-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d665a-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="d665a-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d665a-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d665a-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="d665a-148">Na página **Gerenciar seu DNS,** selecione a **guia DNS** Avançado.</span><span class="sxs-lookup"><span data-stu-id="d665a-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="d665a-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d665a-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d665a-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d665a-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d665a-151">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d665a-151">**Hostname**</span></span>|<span data-ttu-id="d665a-152">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d665a-152">**Type**</span></span>|<span data-ttu-id="d665a-153">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d665a-153">**Priority**</span></span>|<span data-ttu-id="d665a-154">**MX de destino**</span><span class="sxs-lookup"><span data-stu-id="d665a-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d665a-155">MX</span><span class="sxs-lookup"><span data-stu-id="d665a-155">MX</span></span>  <br/> |<span data-ttu-id="d665a-156">1</span><span class="sxs-lookup"><span data-stu-id="d665a-156">1</span></span>  <br/> <span data-ttu-id="d665a-157">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="d665a-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="d665a-158">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d665a-159">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d665a-160">**Observação:** Obtenha a sua \<domain-key\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d665a-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="d665a-161">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d665a-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar valores da tabela](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="d665a-163">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d665a-163">Select **Add**.</span></span>
    
    ![Captura de tela da caixa de diálogo com o botão Adicionar sendo selecionado](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="d665a-165">Se houver outros registros MX, remova cada um deles escolhendo o ícone **Excluir (Lixeira)** do registro.</span><span class="sxs-lookup"><span data-stu-id="d665a-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Selecione Excluir (o ícone da lixeira)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d665a-167">Adicionar os cinco registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d665a-167">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d665a-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d665a-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d665a-p109">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d665a-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d665a-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="d665a-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d665a-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d665a-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="d665a-173">Na página **Gerenciar seu DNS,** selecione a **guia DNS** Avançado.</span><span class="sxs-lookup"><span data-stu-id="d665a-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="d665a-174">Adicione o primeiro dos cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d665a-174">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="d665a-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d665a-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d665a-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d665a-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d665a-177">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d665a-177">**Hostname**</span></span>|<span data-ttu-id="d665a-178">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d665a-178">**Type**</span></span>|<span data-ttu-id="d665a-179">**CNAME de destino**</span><span class="sxs-lookup"><span data-stu-id="d665a-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d665a-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d665a-180">autodiscover</span></span>  <br/> |<span data-ttu-id="d665a-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="d665a-181">CNAME</span></span>  <br/> |<span data-ttu-id="d665a-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d665a-183">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d665a-184">sip</span><span class="sxs-lookup"><span data-stu-id="d665a-184">sip</span></span>  <br/> |<span data-ttu-id="d665a-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="d665a-185">CNAME</span></span>  <br/> |<span data-ttu-id="d665a-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d665a-187">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d665a-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d665a-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d665a-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="d665a-189">CNAME</span></span>  <br/> |<span data-ttu-id="d665a-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d665a-191">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d665a-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d665a-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d665a-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="d665a-193">CNAME</span></span>  <br/> |<span data-ttu-id="d665a-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d665a-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d665a-195">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d665a-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d665a-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d665a-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="d665a-197">CNAME</span></span>  <br/> |<span data-ttu-id="d665a-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d665a-199">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Captura de tela com CNAME de destino para copiar e colar](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="d665a-201">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d665a-201">Select **Add**.</span></span>
    
    ![Captura de tela para adicionar CNAME de destino](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="d665a-203">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d665a-203">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="d665a-204">Na seção **DNS Avançado,** crie um registro usando os valores da próxima  linha na tabela e selecione Adicionar novamente para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="d665a-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="d665a-205">Repita esse processo até que você tenha criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d665a-205">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d665a-206">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="d665a-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d665a-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d665a-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d665a-208">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="d665a-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d665a-209">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="d665a-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d665a-210">Se você já tiver um registro SPF para seu domínio, não crie um novo para Microsfot.</span><span class="sxs-lookup"><span data-stu-id="d665a-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="d665a-211">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d665a-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d665a-212">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="d665a-212">Need examples?</span></span> <span data-ttu-id="d665a-213">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="d665a-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="d665a-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="d665a-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="d665a-215">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="d665a-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="d665a-216">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d665a-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d665a-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="d665a-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d665a-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d665a-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="d665a-219">Na página **Gerenciar seu DNS,** selecione a **guia DNS** Avançado.</span><span class="sxs-lookup"><span data-stu-id="d665a-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="d665a-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d665a-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d665a-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d665a-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d665a-222">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d665a-222">**Hostname**</span></span>|<span data-ttu-id="d665a-223">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d665a-223">**Type**</span></span>|<span data-ttu-id="d665a-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="d665a-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d665a-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="d665a-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="d665a-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d665a-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d665a-227">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d665a-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="d665a-229">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d665a-229">Select **Add**.</span></span>
    
    ![Captura de tela com destino TXT/SPF](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d665a-231">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d665a-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d665a-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d665a-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d665a-p112">Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d665a-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d665a-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="d665a-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d665a-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d665a-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="d665a-237">Na página **Gerenciar seu DNS,** selecione a **guia DNS** Avançado.</span><span class="sxs-lookup"><span data-stu-id="d665a-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="d665a-238">Adicione o primeiro dos dois registros SRV:</span><span class="sxs-lookup"><span data-stu-id="d665a-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="d665a-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d665a-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d665a-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d665a-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d665a-241">Nome do host</span><span class="sxs-lookup"><span data-stu-id="d665a-241">Hostname</span></span>|<span data-ttu-id="d665a-242">Tipo</span><span class="sxs-lookup"><span data-stu-id="d665a-242">Type</span></span>|<span data-ttu-id="d665a-243">Prioridade</span><span class="sxs-lookup"><span data-stu-id="d665a-243">Priority</span></span>|<span data-ttu-id="d665a-244">TTL</span><span class="sxs-lookup"><span data-stu-id="d665a-244">TTL</span></span>|<span data-ttu-id="d665a-245">SRV de destino</span><span class="sxs-lookup"><span data-stu-id="d665a-245">Destination SRV</span></span>|
    |<span data-ttu-id="d665a-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d665a-246">_sip._tls</span></span>|<span data-ttu-id="d665a-247">SRV</span><span class="sxs-lookup"><span data-stu-id="d665a-247">SRV</span></span>|<span data-ttu-id="d665a-248">100</span><span class="sxs-lookup"><span data-stu-id="d665a-248">100</span></span>|<span data-ttu-id="d665a-249">3600</span><span class="sxs-lookup"><span data-stu-id="d665a-249">3600</span></span>|<span data-ttu-id="d665a-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="d665a-251">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="d665a-252">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d665a-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="d665a-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d665a-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="d665a-254">SRV</span><span class="sxs-lookup"><span data-stu-id="d665a-254">SRV</span></span>|<span data-ttu-id="d665a-255">100</span><span class="sxs-lookup"><span data-stu-id="d665a-255">100</span></span>|<span data-ttu-id="d665a-256">3600</span><span class="sxs-lookup"><span data-stu-id="d665a-256">3600</span></span>|<span data-ttu-id="d665a-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d665a-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="d665a-258">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d665a-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="d665a-259">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d665a-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Captura de tela com valores DNS da tabela](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="d665a-261">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d665a-261">Select **Add**.</span></span>
    
    ![Captura de tela para adicionar SRV de destino](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="d665a-263">Para adicionar o outro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="d665a-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="d665a-264">Na seção **DNS avançado,** crie um registro usando os valores da segunda  linha da tabela e selecione Adicionar novamente para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="d665a-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d665a-265">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d665a-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d665a-266">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d665a-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d665a-267">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d665a-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
