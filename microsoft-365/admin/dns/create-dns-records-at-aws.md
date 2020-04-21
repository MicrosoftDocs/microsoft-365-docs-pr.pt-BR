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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Amazon Web Services (AWS) para Microsoft.
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629726"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="d0ce4-103">Criar registros DNS no Amazon Web Services (AWS) para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ce4-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="d0ce4-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d0ce4-105">Se o AWS for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype online for Business e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="d0ce4-106">Depois que você adicionar esses registros no AWS, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="d0ce4-107">Para saber mais sobre o webhosting e o DNS para sites com o Microsfot, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0ce4-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d0ce4-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d0ce4-110">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d0ce4-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d0ce4-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d0ce4-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d0ce4-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d0ce4-113">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d0ce4-114">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0ce4-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d0ce4-117">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d0ce4-118">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0ce4-119">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0ce4-120">Na página \* \* zonas hospedadas \* \*, na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0ce4-121">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d0ce4-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0ce4-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="d0ce4-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d0ce4-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0ce4-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-126">**Name**</span></span> <br/> |<span data-ttu-id="d0ce4-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-127">**Type**</span></span> <br/> |<span data-ttu-id="d0ce4-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-128">**Alias**</span></span> <br/> |<span data-ttu-id="d0ce4-129">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="d0ce4-130">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-130">**Value**</span></span> <br/> |<span data-ttu-id="d0ce4-131">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="d0ce4-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d0ce4-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0ce4-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="d0ce4-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="d0ce4-134">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-134">No</span></span>  <br/> |<span data-ttu-id="d0ce4-135">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-135">300</span></span>  <br/> |<span data-ttu-id="d0ce4-136">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d0ce4-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="d0ce4-137">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-137">**Note:** This is an example.</span></span> <span data-ttu-id="d0ce4-138">Use o seu **destino específico ou aponte para** o valor de endereço aqui, na tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="d0ce4-139">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="d0ce4-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d0ce4-140">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="d0ce4-141">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="d0ce4-142">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d0ce4-143">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="d0ce4-144">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d0ce4-145">No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="d0ce4-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d0ce4-146">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d0ce4-147">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d0ce4-148">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d0ce4-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d0ce4-150">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d0ce4-151">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="d0ce4-152">Adicionar um registro MX para que o email do seu domínio seja fornecido com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0ce4-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="d0ce4-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d0ce4-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d0ce4-p108">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0ce4-156">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0ce4-157">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0ce4-158">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d0ce4-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0ce4-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="d0ce4-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d0ce4-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-161">**Name**</span></span>|<span data-ttu-id="d0ce4-162">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-162">**Type**</span></span>|<span data-ttu-id="d0ce4-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-163">**Alias**</span></span>|<span data-ttu-id="d0ce4-164">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="d0ce4-165">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-165">**Value**</span></span>|<span data-ttu-id="d0ce4-166">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0ce4-167">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="d0ce4-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0ce4-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="d0ce4-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="d0ce4-169">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-169">No</span></span>  <br/> |<span data-ttu-id="d0ce4-170">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-170">300</span></span>  <br/> |<span data-ttu-id="d0ce4-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d0ce4-p109">O 0 é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="d0ce4-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="d0ce4-174">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d0ce4-175">**Observação:** Obtenha sua \< *chave* \> de domínio de sua conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="d0ce4-176">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="d0ce4-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d0ce4-177">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="d0ce4-179">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="d0ce4-181">Se houver quaisquer outros registros MX, remova-os.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0ce4-182">O AWS armazena registros MX como um conjunto que pode conter vários registros.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="d0ce4-183">**Não** selecione **excluir conjunto de registros**, pois isso excluirá todos os seus registros MX, incluindo aquele que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="d0ce4-184">Em vez disso, use as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="d0ce4-185">Primeiro, selecione o conjunto de registros MX.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="d0ce4-187">Em seguida, na área **Editar Conjunto de Registros**, exclua cada registro MX obsoleto selecionando a entrada na caixa **Valor** e, em seguida, pressione a tecla **Excluir** em seu teclado.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="d0ce4-189">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="d0ce4-191">Adicionar os cinco registros CNAME necessários para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0ce4-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="d0ce4-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d0ce4-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d0ce4-p112">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0ce4-195">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0ce4-196">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0ce4-197">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d0ce4-198">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d0ce4-199">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d0ce4-200">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d0ce4-201">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-201">**Name**</span></span>|<span data-ttu-id="d0ce4-202">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-202">**Type**</span></span>|<span data-ttu-id="d0ce4-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-203">**Alias**</span></span>|<span data-ttu-id="d0ce4-204">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="d0ce4-205">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-205">**Value**</span></span>|<span data-ttu-id="d0ce4-206">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0ce4-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d0ce4-207">autodiscover</span></span>  <br/> |<span data-ttu-id="d0ce4-208">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="d0ce4-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d0ce4-209">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-209">No</span></span>  <br/> |<span data-ttu-id="d0ce4-210">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-210">300</span></span>  <br/> |<span data-ttu-id="d0ce4-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d0ce4-212">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0ce4-213">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="d0ce4-214">sip</span><span class="sxs-lookup"><span data-stu-id="d0ce4-214">sip</span></span>  <br/> |<span data-ttu-id="d0ce4-215">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="d0ce4-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d0ce4-216">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-216">No</span></span>  <br/> |<span data-ttu-id="d0ce4-217">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-217">300</span></span>  <br/> |<span data-ttu-id="d0ce4-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0ce4-219">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0ce4-220">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="d0ce4-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d0ce4-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d0ce4-222">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="d0ce4-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d0ce4-223">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-223">No</span></span>  <br/> |<span data-ttu-id="d0ce4-224">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-224">300</span></span>  <br/> |<span data-ttu-id="d0ce4-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0ce4-226">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0ce4-227">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="d0ce4-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d0ce4-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d0ce4-229">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="d0ce4-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d0ce4-230">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-230">No</span></span>  <br/> |<span data-ttu-id="d0ce4-231">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-231">300</span></span>  <br/> |<span data-ttu-id="d0ce4-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d0ce4-233">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0ce4-234">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="d0ce4-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d0ce4-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d0ce4-236">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="d0ce4-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d0ce4-237">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-237">No</span></span>  <br/> |<span data-ttu-id="d0ce4-238">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-238">300</span></span>  <br/> |<span data-ttu-id="d0ce4-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d0ce4-240">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d0ce4-241">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="d0ce4-243">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="d0ce4-245">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="d0ce4-246">Na página **zonas hospedadas** , selecione **criar conjunto de registros**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="d0ce4-247">Repita esse processo até ter criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d0ce4-248">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="d0ce4-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d0ce4-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d0ce4-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0ce4-250">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d0ce4-251">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d0ce4-252">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d0ce4-253">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d0ce4-254">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="d0ce4-254">Need examples?</span></span> <span data-ttu-id="d0ce4-255">Confira estes [registros de sistema de nomes de domínio externo para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="d0ce4-256">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d0ce4-257">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d0ce4-258">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0ce4-259">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0ce4-260">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0ce4-261">Selecione o conjunto de registros **txt** .</span><span class="sxs-lookup"><span data-stu-id="d0ce4-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="d0ce4-p115">Na área **Editar Conjunto de Registros**, ao final da entrada atual na caixa **Valor:** para o registro existente, pressione Enter em seu teclado para criar uma nova linha; e, em seguida, nessa linha nova (sob o valor existente), digite ou copie e cole os valores da tabela a seguir. (Você pode ver um exemplo na ilustração abaixo da tabela).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="d0ce4-265">**Valor:**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="d0ce4-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d0ce4-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d0ce4-p116">(As aspas necessárias para as instruções na tela são fornecidas automaticamente. Não é necessário inseri-las manualmente.)  </span><span class="sxs-lookup"><span data-stu-id="d0ce4-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="d0ce4-269">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="d0ce4-271">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="d0ce4-273">Adicionar os dois registros SRV necessários para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0ce4-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="d0ce4-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d0ce4-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d0ce4-p117">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d0ce4-277">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d0ce4-278">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d0ce4-279">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d0ce4-280">Adicione o primeiro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="d0ce4-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="d0ce4-281">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d0ce4-282">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d0ce4-283">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-283">**Name**</span></span>|<span data-ttu-id="d0ce4-284">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-284">**Type**</span></span>|<span data-ttu-id="d0ce4-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-285">**Alias**</span></span>|<span data-ttu-id="d0ce4-286">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="d0ce4-287">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-287">**Value**</span></span>|<span data-ttu-id="d0ce4-288">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0ce4-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="d0ce4-289">_sip._tls</span></span>|<span data-ttu-id="d0ce4-290">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="d0ce4-290">SRV - Service locator</span></span>|<span data-ttu-id="d0ce4-291">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-291">No</span></span>|<span data-ttu-id="d0ce4-292">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-292">300</span></span>|<span data-ttu-id="d0ce4-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="d0ce4-294">**Esse valor deve terminar com um ponto (.)**></span><span class="sxs-lookup"><span data-stu-id="d0ce4-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="d0ce4-295">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d0ce4-296">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-296">Simple</span></span>|
    |<span data-ttu-id="d0ce4-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="d0ce4-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="d0ce4-298">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="d0ce4-298">SRV - Service locator</span></span>|<span data-ttu-id="d0ce4-299">Não</span><span class="sxs-lookup"><span data-stu-id="d0ce4-299">No</span></span>|<span data-ttu-id="d0ce4-300">300</span><span class="sxs-lookup"><span data-stu-id="d0ce4-300">300</span></span>|<span data-ttu-id="d0ce4-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="d0ce4-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d0ce4-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="d0ce4-303">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d0ce4-304">Simples</span><span class="sxs-lookup"><span data-stu-id="d0ce4-304">Simple</span></span>|
   
    ![AWS-BP-configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="d0ce4-306">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="d0ce4-308">Para adicionar o outro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="d0ce4-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="d0ce4-309">Na página **zonas hospedadas** , selecione **criar conjunto de registros**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d0ce4-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d0ce4-311">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d0ce4-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d0ce4-312">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0ce4-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
