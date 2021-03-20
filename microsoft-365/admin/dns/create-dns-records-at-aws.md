---
title: Criar registros DNS no Amazon Web Services (AWS) para a Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Amazon Web Services (AWS) para a Microsoft.
ms.openlocfilehash: 12f9341ab381324266cf2da1ca6b5423df9973dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910409"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="14746-103">Criar registros DNS no Amazon Web Services (AWS) para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="14746-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="14746-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="14746-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="14746-105">Se o AWS for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype Online para Empresas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="14746-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="14746-106">Depois de adicionar esses registros na AWS, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14746-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="14746-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="14746-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="14746-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="14746-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="14746-109">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14746-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="14746-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="14746-110">Add a TXT record for verification</span></span>
<span data-ttu-id="14746-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="14746-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="14746-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="14746-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14746-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="14746-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="14746-p104">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="14746-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="14746-118">Na página **Recursos,** selecione **Zonas Hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="14746-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="14746-119">Na página **Zonas Hospedadas,** na coluna **Nome** de Domínio, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="14746-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="14746-120">Selecione **Criar Conjunto de Registros**.</span><span class="sxs-lookup"><span data-stu-id="14746-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="14746-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="14746-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="14746-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="14746-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="14746-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="14746-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14746-125">**Nome**</span><span class="sxs-lookup"><span data-stu-id="14746-125">**Name**</span></span> <br/> |<span data-ttu-id="14746-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14746-126">**Type**</span></span> <br/> |<span data-ttu-id="14746-127">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14746-127">**Alias**</span></span> <br/> |<span data-ttu-id="14746-128">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="14746-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="14746-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14746-129">**Value**</span></span> <br/> |<span data-ttu-id="14746-130">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="14746-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="14746-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="14746-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="14746-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="14746-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="14746-133">Não</span><span class="sxs-lookup"><span data-stu-id="14746-133">No</span></span>  <br/> |<span data-ttu-id="14746-134">300</span><span class="sxs-lookup"><span data-stu-id="14746-134">300</span></span>  <br/> |<span data-ttu-id="14746-135">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="14746-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="14746-136">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="14746-136">**Note:** This is an example.</span></span> <span data-ttu-id="14746-137">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14746-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="14746-138">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="14746-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="14746-139">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="14746-140">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="14746-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="14746-141">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="14746-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="14746-142">Agora que você adicionou o registro no site do registrador de domínios, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="14746-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="14746-143">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="14746-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="14746-144">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="14746-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="14746-145">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="14746-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="14746-146">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="14746-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="14746-147">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="14746-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14746-148">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="14746-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="14746-149">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="14746-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="14746-150">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14746-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="14746-151">Adicionar um registro MX para que o email para seu domínio venha para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14746-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="14746-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="14746-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="14746-p108">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="14746-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="14746-155">Na página **Recursos,** selecione **Zonas Hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="14746-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="14746-156">Na página **Zonas Hospedadas,** na coluna **Nome** de Domínio, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="14746-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="14746-157">Selecione **Criar Conjunto de Registros**.</span><span class="sxs-lookup"><span data-stu-id="14746-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="14746-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="14746-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="14746-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="14746-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14746-160">**Nome**</span><span class="sxs-lookup"><span data-stu-id="14746-160">**Name**</span></span>|<span data-ttu-id="14746-161">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14746-161">**Type**</span></span>|<span data-ttu-id="14746-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14746-162">**Alias**</span></span>|<span data-ttu-id="14746-163">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="14746-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="14746-164">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14746-164">**Value**</span></span>|<span data-ttu-id="14746-165">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="14746-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14746-166">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="14746-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="14746-167">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="14746-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="14746-168">Não</span><span class="sxs-lookup"><span data-stu-id="14746-168">No</span></span>  <br/> |<span data-ttu-id="14746-169">300</span><span class="sxs-lookup"><span data-stu-id="14746-169">300</span></span>  <br/> |<span data-ttu-id="14746-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="14746-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="14746-p109">O 0 é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="14746-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="14746-173">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="14746-174">**Observação:** Obter o \<*domain-key*\> seu da sua conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14746-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="14746-175">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="14746-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="14746-176">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="14746-178">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="14746-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="14746-180">Se houver quaisquer outros registros MX, remova-os.</span><span class="sxs-lookup"><span data-stu-id="14746-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="14746-181">O AWS armazena registros MX como um conjunto que pode conter vários registros.</span><span class="sxs-lookup"><span data-stu-id="14746-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="14746-182">**NÃO selecione** **Excluir Conjunto de Registros**, pois isso excluirá todos os registros MX, incluindo o que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="14746-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="14746-183">Em vez disso, use as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="14746-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="14746-184">Primeiro, selecione o conjunto de registros MX.</span><span class="sxs-lookup"><span data-stu-id="14746-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="14746-186">Em seguida, na área **Editar Conjunto de Registros**, exclua cada registro MX obsoleto selecionando a entrada na caixa **Valor** e, em seguida, pressione a tecla **Excluir** em seu teclado.</span><span class="sxs-lookup"><span data-stu-id="14746-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="14746-188">Selecione **Salvar Conjunto de Registros**.</span><span class="sxs-lookup"><span data-stu-id="14746-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="14746-190">Adicionar os cinco registros CNAME necessários para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14746-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="14746-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="14746-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="14746-p112">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="14746-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="14746-194">Na página **Recursos,** selecione **Zonas Hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="14746-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="14746-195">Na página **Zonas Hospedadas,** na coluna **Nome** de Domínio, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="14746-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="14746-196">Selecione **Criar Conjunto de Registros**.</span><span class="sxs-lookup"><span data-stu-id="14746-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="14746-197">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="14746-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="14746-198">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="14746-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="14746-199">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="14746-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14746-200">**Nome**</span><span class="sxs-lookup"><span data-stu-id="14746-200">**Name**</span></span>|<span data-ttu-id="14746-201">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14746-201">**Type**</span></span>|<span data-ttu-id="14746-202">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14746-202">**Alias**</span></span>|<span data-ttu-id="14746-203">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="14746-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="14746-204">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14746-204">**Value**</span></span>|<span data-ttu-id="14746-205">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="14746-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14746-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="14746-206">autodiscover</span></span>  <br/> |<span data-ttu-id="14746-207">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="14746-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="14746-208">Não</span><span class="sxs-lookup"><span data-stu-id="14746-208">No</span></span>  <br/> |<span data-ttu-id="14746-209">300</span><span class="sxs-lookup"><span data-stu-id="14746-209">300</span></span>  <br/> |<span data-ttu-id="14746-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="14746-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="14746-211">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14746-212">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="14746-213">sip</span><span class="sxs-lookup"><span data-stu-id="14746-213">sip</span></span>  <br/> |<span data-ttu-id="14746-214">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="14746-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="14746-215">Não</span><span class="sxs-lookup"><span data-stu-id="14746-215">No</span></span>  <br/> |<span data-ttu-id="14746-216">300</span><span class="sxs-lookup"><span data-stu-id="14746-216">300</span></span>  <br/> |<span data-ttu-id="14746-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14746-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="14746-218">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14746-219">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="14746-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="14746-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="14746-221">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="14746-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="14746-222">Não</span><span class="sxs-lookup"><span data-stu-id="14746-222">No</span></span>  <br/> |<span data-ttu-id="14746-223">300</span><span class="sxs-lookup"><span data-stu-id="14746-223">300</span></span>  <br/> |<span data-ttu-id="14746-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14746-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="14746-225">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14746-226">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="14746-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="14746-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="14746-228">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="14746-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="14746-229">Não</span><span class="sxs-lookup"><span data-stu-id="14746-229">No</span></span>  <br/> |<span data-ttu-id="14746-230">300</span><span class="sxs-lookup"><span data-stu-id="14746-230">300</span></span>  <br/> |<span data-ttu-id="14746-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="14746-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="14746-232">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14746-233">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="14746-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="14746-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="14746-235">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="14746-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="14746-236">Não</span><span class="sxs-lookup"><span data-stu-id="14746-236">No</span></span>  <br/> |<span data-ttu-id="14746-237">300</span><span class="sxs-lookup"><span data-stu-id="14746-237">300</span></span>  <br/> |<span data-ttu-id="14746-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="14746-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="14746-239">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="14746-240">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="14746-242">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="14746-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="14746-244">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="14746-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="14746-245">Na página **Zonas Hospedadas,** selecione **Criar** Conjunto de Registros , crie um registro usando  os valores da próxima linha na tabela e selecione Criar para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="14746-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="14746-246">Repita esse processo até que você tenha criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="14746-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="14746-247">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="14746-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="14746-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="14746-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14746-249">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="14746-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="14746-250">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="14746-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="14746-251">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14746-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="14746-252">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="14746-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="14746-253">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="14746-253">Need examples?</span></span> <span data-ttu-id="14746-254">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="14746-254">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="14746-255">Para validar seu registro SPF, você pode usar uma dessas ferramentas de validação[SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="14746-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="14746-256">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="14746-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="14746-257">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="14746-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="14746-258">Na página **Recursos,** selecione **Zonas Hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="14746-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="14746-259">Na página **Zonas Hospedadas,** na coluna **Nome** de Domínio, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="14746-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="14746-260">Selecione o **conjunto de registros TXT.**</span><span class="sxs-lookup"><span data-stu-id="14746-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="14746-p115">Na área **Editar Conjunto de Registros**, ao final da entrada atual na caixa **Valor:** para o registro existente, pressione Enter em seu teclado para criar uma nova linha; e, em seguida, nessa linha nova (sob o valor existente), digite ou copie e cole os valores da tabela a seguir. (Você pode ver um exemplo na ilustração abaixo da tabela).</span><span class="sxs-lookup"><span data-stu-id="14746-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="14746-264">**Valor:**</span><span class="sxs-lookup"><span data-stu-id="14746-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="14746-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="14746-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="14746-p116">(As aspas necessárias para as instruções na tela são fornecidas automaticamente. Não é necessário inseri-las manualmente.)  </span><span class="sxs-lookup"><span data-stu-id="14746-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="14746-268">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="14746-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="14746-270">Selecione **Salvar Conjunto de Registros**.</span><span class="sxs-lookup"><span data-stu-id="14746-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="14746-272">Adicionar os dois registros SRV necessários para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14746-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="14746-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="14746-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="14746-p117">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="14746-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="14746-276">Na página **Recursos,** selecione **Zonas Hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="14746-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="14746-277">Na página **Zonas Hospedadas,** na coluna **Nome** de Domínio, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="14746-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="14746-278">Selecione **Criar Conjunto de Registros**.</span><span class="sxs-lookup"><span data-stu-id="14746-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="14746-279">Adicione o primeiro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="14746-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="14746-280">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="14746-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="14746-281">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="14746-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14746-282">**Nome**</span><span class="sxs-lookup"><span data-stu-id="14746-282">**Name**</span></span>|<span data-ttu-id="14746-283">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14746-283">**Type**</span></span>|<span data-ttu-id="14746-284">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14746-284">**Alias**</span></span>|<span data-ttu-id="14746-285">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="14746-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="14746-286">**Valor**</span><span class="sxs-lookup"><span data-stu-id="14746-286">**Value**</span></span>|<span data-ttu-id="14746-287">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="14746-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14746-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="14746-288">_sip._tls</span></span>|<span data-ttu-id="14746-289">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="14746-289">SRV - Service locator</span></span>|<span data-ttu-id="14746-290">Não</span><span class="sxs-lookup"><span data-stu-id="14746-290">No</span></span>|<span data-ttu-id="14746-291">300</span><span class="sxs-lookup"><span data-stu-id="14746-291">300</span></span>|<span data-ttu-id="14746-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14746-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="14746-293">**Esse valor DEVE terminar com um ponto (.)**></span><span class="sxs-lookup"><span data-stu-id="14746-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="14746-294">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="14746-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="14746-295">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-295">Simple</span></span>|
    |<span data-ttu-id="14746-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="14746-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="14746-297">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="14746-297">SRV - Service locator</span></span>|<span data-ttu-id="14746-298">Não</span><span class="sxs-lookup"><span data-stu-id="14746-298">No</span></span>|<span data-ttu-id="14746-299">300</span><span class="sxs-lookup"><span data-stu-id="14746-299">300</span></span>|<span data-ttu-id="14746-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14746-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="14746-301">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="14746-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="14746-302">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="14746-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="14746-303">Simples</span><span class="sxs-lookup"><span data-stu-id="14746-303">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="14746-305">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="14746-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="14746-307">Para adicionar o outro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="14746-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="14746-308">Na página **Zonas Hospedadas,** selecione **Criar** Conjunto de Registros , crie um registro usando  os valores da próxima linha na tabela e selecione Criar para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="14746-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="14746-309">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="14746-309">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="14746-310">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="14746-310">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="14746-311">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14746-311">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
