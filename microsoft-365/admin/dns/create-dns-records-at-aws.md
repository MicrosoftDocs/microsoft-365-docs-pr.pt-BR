---
title: Criar registros DNS no Amazon Web Services (AWS) para o Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Amazon Web Services (AWS) para Microsoft.
ms.openlocfilehash: dbbf82c9c776108c4d5e34e2eb639f9c36e9f28b
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307062"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="a3f24-103">Criar registros DNS no Amazon Web Services (AWS) para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3f24-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="a3f24-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a3f24-105">Se o AWS for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype online for Business e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a3f24-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="a3f24-106">Depois que você adicionar esses registros no AWS, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3f24-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="a3f24-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a3f24-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a3f24-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="a3f24-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a3f24-109">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a3f24-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a3f24-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a3f24-110">Add a TXT record for verification</span></span>
<span data-ttu-id="a3f24-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f24-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a3f24-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3f24-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a3f24-p104">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a3f24-118">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="a3f24-119">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="a3f24-120">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="a3f24-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a3f24-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a3f24-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="a3f24-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="a3f24-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3f24-125">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a3f24-125">**Name**</span></span> <br/> |<span data-ttu-id="a3f24-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a3f24-126">**Type**</span></span> <br/> |<span data-ttu-id="a3f24-127">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a3f24-127">**Alias**</span></span> <br/> |<span data-ttu-id="a3f24-128">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="a3f24-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a3f24-129">**Value**</span></span> <br/> |<span data-ttu-id="a3f24-130">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="a3f24-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="a3f24-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a3f24-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a3f24-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="a3f24-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="a3f24-133">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-133">No</span></span>  <br/> |<span data-ttu-id="a3f24-134">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-134">300</span></span>  <br/> |<span data-ttu-id="a3f24-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a3f24-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="a3f24-136">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a3f24-136">**Note:** This is an example.</span></span> <span data-ttu-id="a3f24-137">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3f24-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="a3f24-138">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a3f24-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a3f24-139">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="a3f24-140">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="a3f24-141">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="a3f24-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a3f24-142">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="a3f24-143">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="a3f24-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a3f24-144">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="a3f24-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a3f24-145">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="a3f24-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a3f24-146">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a3f24-147">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a3f24-148">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a3f24-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a3f24-149">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="a3f24-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a3f24-150">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a3f24-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="a3f24-151">Adicionar um registro MX para que o email do seu domínio seja fornecido com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3f24-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="a3f24-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f24-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a3f24-p108">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a3f24-155">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="a3f24-156">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="a3f24-157">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="a3f24-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a3f24-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a3f24-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="a3f24-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a3f24-160">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a3f24-160">**Name**</span></span>|<span data-ttu-id="a3f24-161">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a3f24-161">**Type**</span></span>|<span data-ttu-id="a3f24-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a3f24-162">**Alias**</span></span>|<span data-ttu-id="a3f24-163">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="a3f24-164">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a3f24-164">**Value**</span></span>|<span data-ttu-id="a3f24-165">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="a3f24-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3f24-166">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="a3f24-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a3f24-167">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="a3f24-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="a3f24-168">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-168">No</span></span>  <br/> |<span data-ttu-id="a3f24-169">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-169">300</span></span>  <br/> |<span data-ttu-id="a3f24-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a3f24-p109">O 0 é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="a3f24-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="a3f24-173">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a3f24-174">**Observação:** Acesse sua \<*domain-key*\> conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3f24-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="a3f24-175">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="a3f24-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a3f24-176">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="a3f24-178">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="a3f24-180">Se houver quaisquer outros registros MX, remova-os.</span><span class="sxs-lookup"><span data-stu-id="a3f24-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3f24-181">O AWS armazena registros MX como um conjunto que pode conter vários registros.</span><span class="sxs-lookup"><span data-stu-id="a3f24-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="a3f24-182">**Não** selecione **excluir conjunto de registros**, pois isso excluirá todos os seus registros MX, incluindo aquele que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="a3f24-183">Em vez disso, use as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3f24-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="a3f24-184">Primeiro, selecione o conjunto de registros MX.</span><span class="sxs-lookup"><span data-stu-id="a3f24-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="a3f24-186">Em seguida, na área **Editar Conjunto de Registros**, exclua cada registro MX obsoleto selecionando a entrada na caixa **Valor** e, em seguida, pressione a tecla **Excluir** em seu teclado.</span><span class="sxs-lookup"><span data-stu-id="a3f24-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="a3f24-188">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="a3f24-190">Adicionar os cinco registros CNAME necessários para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3f24-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="a3f24-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f24-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a3f24-p112">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a3f24-194">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="a3f24-195">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="a3f24-196">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="a3f24-197">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="a3f24-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="a3f24-198">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3f24-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a3f24-199">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="a3f24-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a3f24-200">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a3f24-200">**Name**</span></span>|<span data-ttu-id="a3f24-201">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a3f24-201">**Type**</span></span>|<span data-ttu-id="a3f24-202">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a3f24-202">**Alias**</span></span>|<span data-ttu-id="a3f24-203">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="a3f24-204">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a3f24-204">**Value**</span></span>|<span data-ttu-id="a3f24-205">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="a3f24-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3f24-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a3f24-206">autodiscover</span></span>  <br/> |<span data-ttu-id="a3f24-207">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="a3f24-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="a3f24-208">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-208">No</span></span>  <br/> |<span data-ttu-id="a3f24-209">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-209">300</span></span>  <br/> |<span data-ttu-id="a3f24-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a3f24-211">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a3f24-212">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="a3f24-213">sip</span><span class="sxs-lookup"><span data-stu-id="a3f24-213">sip</span></span>  <br/> |<span data-ttu-id="a3f24-214">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="a3f24-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="a3f24-215">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-215">No</span></span>  <br/> |<span data-ttu-id="a3f24-216">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-216">300</span></span>  <br/> |<span data-ttu-id="a3f24-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a3f24-218">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a3f24-219">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="a3f24-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a3f24-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a3f24-221">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="a3f24-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="a3f24-222">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-222">No</span></span>  <br/> |<span data-ttu-id="a3f24-223">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-223">300</span></span>  <br/> |<span data-ttu-id="a3f24-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a3f24-225">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a3f24-226">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="a3f24-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a3f24-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a3f24-228">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="a3f24-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="a3f24-229">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-229">No</span></span>  <br/> |<span data-ttu-id="a3f24-230">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-230">300</span></span>  <br/> |<span data-ttu-id="a3f24-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a3f24-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="a3f24-232">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a3f24-233">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="a3f24-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a3f24-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a3f24-235">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="a3f24-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="a3f24-236">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-236">No</span></span>  <br/> |<span data-ttu-id="a3f24-237">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-237">300</span></span>  <br/> |<span data-ttu-id="a3f24-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="a3f24-239">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a3f24-240">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="a3f24-242">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="a3f24-244">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="a3f24-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="a3f24-245">Na página **zonas hospedadas** , selecione **criar conjunto de registros**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="a3f24-246">Repita esse processo até ter criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="a3f24-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a3f24-247">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="a3f24-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a3f24-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f24-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3f24-249">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="a3f24-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a3f24-250">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="a3f24-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a3f24-251">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3f24-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a3f24-252">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a3f24-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="a3f24-253">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="a3f24-253">Need examples?</span></span> <span data-ttu-id="a3f24-254">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="a3f24-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="a3f24-255">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="a3f24-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="a3f24-256">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="a3f24-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="a3f24-257">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a3f24-258">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="a3f24-259">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="a3f24-260">Selecione o conjunto de registros **txt** .</span><span class="sxs-lookup"><span data-stu-id="a3f24-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="a3f24-p115">Na área **Editar Conjunto de Registros**, ao final da entrada atual na caixa **Valor:** para o registro existente, pressione Enter em seu teclado para criar uma nova linha; e, em seguida, nessa linha nova (sob o valor existente), digite ou copie e cole os valores da tabela a seguir. (Você pode ver um exemplo na ilustração abaixo da tabela).</span><span class="sxs-lookup"><span data-stu-id="a3f24-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="a3f24-264">**Valor:**</span><span class="sxs-lookup"><span data-stu-id="a3f24-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="a3f24-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a3f24-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a3f24-p116">(As aspas necessárias para as instruções na tela são fornecidas automaticamente. Não é necessário inseri-las manualmente.)  </span><span class="sxs-lookup"><span data-stu-id="a3f24-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="a3f24-268">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a3f24-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="a3f24-270">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="a3f24-272">Adicionar os dois registros SRV necessários para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3f24-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="a3f24-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f24-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a3f24-p117">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a3f24-276">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="a3f24-277">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a3f24-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="a3f24-278">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="a3f24-279">Adicione o primeiro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="a3f24-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="a3f24-280">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3f24-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a3f24-281">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="a3f24-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a3f24-282">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a3f24-282">**Name**</span></span>|<span data-ttu-id="a3f24-283">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a3f24-283">**Type**</span></span>|<span data-ttu-id="a3f24-284">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a3f24-284">**Alias**</span></span>|<span data-ttu-id="a3f24-285">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="a3f24-286">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a3f24-286">**Value**</span></span>|<span data-ttu-id="a3f24-287">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="a3f24-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3f24-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a3f24-288">_sip._tls</span></span>|<span data-ttu-id="a3f24-289">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="a3f24-289">SRV - Service locator</span></span>|<span data-ttu-id="a3f24-290">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-290">No</span></span>|<span data-ttu-id="a3f24-291">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-291">300</span></span>|<span data-ttu-id="a3f24-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="a3f24-293">**Esse valor deve terminar com um ponto (.)**></span><span class="sxs-lookup"><span data-stu-id="a3f24-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="a3f24-294">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a3f24-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a3f24-295">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-295">Simple</span></span>|
    |<span data-ttu-id="a3f24-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a3f24-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="a3f24-297">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="a3f24-297">SRV - Service locator</span></span>|<span data-ttu-id="a3f24-298">Não</span><span class="sxs-lookup"><span data-stu-id="a3f24-298">No</span></span>|<span data-ttu-id="a3f24-299">300</span><span class="sxs-lookup"><span data-stu-id="a3f24-299">300</span></span>|<span data-ttu-id="a3f24-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a3f24-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="a3f24-301">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a3f24-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="a3f24-302">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a3f24-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a3f24-303">Simples</span><span class="sxs-lookup"><span data-stu-id="a3f24-303">Simple</span></span>|
   
    ![AWS-BP-configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="a3f24-305">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a3f24-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="a3f24-307">Para adicionar o outro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="a3f24-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="a3f24-308">Na página **zonas hospedadas** , selecione **criar conjunto de registros**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="a3f24-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a3f24-309">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a3f24-309">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a3f24-310">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="a3f24-310">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a3f24-311">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a3f24-311">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
