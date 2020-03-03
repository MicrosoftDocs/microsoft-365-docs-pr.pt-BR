---
title: Criar registros DNS na AWS (Amazon Web Services) para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Amazon Web Services (AWS) para o Office 365.
ms.openlocfilehash: baba7bb7275303604d241166f4dc1d2af77b3f17
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351472"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="ce55d-103">Criar registros DNS na AWS (Amazon Web Services) para Office 365</span><span class="sxs-lookup"><span data-stu-id="ce55d-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="ce55d-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ce55d-105">Se o AWS for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype online for Business e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ce55d-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="ce55d-106">Depois que você adicionar esses registros no AWS, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce55d-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ce55d-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ce55d-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce55d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ce55d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ce55d-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="ce55d-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ce55d-110">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce55d-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ce55d-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="ce55d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="ce55d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ce55d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ce55d-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ce55d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce55d-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ce55d-117">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="ce55d-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="ce55d-118">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ce55d-119">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ce55d-120">Na página \* \* zonas hospedadas \* \*, na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ce55d-121">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ce55d-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ce55d-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce55d-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="ce55d-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ce55d-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="ce55d-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce55d-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ce55d-126">**Name**</span></span> <br/> |<span data-ttu-id="ce55d-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce55d-127">**Type**</span></span> <br/> |<span data-ttu-id="ce55d-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ce55d-128">**Alias**</span></span> <br/> |<span data-ttu-id="ce55d-129">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="ce55d-130">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ce55d-130">**Value**</span></span> <br/> |<span data-ttu-id="ce55d-131">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="ce55d-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="ce55d-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ce55d-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ce55d-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="ce55d-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="ce55d-134">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-134">No</span></span>  <br/> |<span data-ttu-id="ce55d-135">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-135">300</span></span>  <br/> |<span data-ttu-id="ce55d-136">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ce55d-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="ce55d-137">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="ce55d-137">**Note:** This is an example.</span></span> <span data-ttu-id="ce55d-138">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce55d-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="ce55d-139">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ce55d-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ce55d-140">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="ce55d-141">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="ce55d-142">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="ce55d-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ce55d-143">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ce55d-144">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="ce55d-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ce55d-145">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="ce55d-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ce55d-146">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="ce55d-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ce55d-147">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ce55d-148">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ce55d-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ce55d-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ce55d-150">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="ce55d-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ce55d-151">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce55d-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ce55d-152">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce55d-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ce55d-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ce55d-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ce55d-p108">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ce55d-156">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ce55d-157">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ce55d-158">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ce55d-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ce55d-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce55d-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="ce55d-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ce55d-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ce55d-161">**Name**</span></span>|<span data-ttu-id="ce55d-162">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce55d-162">**Type**</span></span>|<span data-ttu-id="ce55d-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ce55d-163">**Alias**</span></span>|<span data-ttu-id="ce55d-164">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="ce55d-165">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ce55d-165">**Value**</span></span>|<span data-ttu-id="ce55d-166">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="ce55d-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce55d-167">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="ce55d-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ce55d-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="ce55d-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="ce55d-169">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-169">No</span></span>  <br/> |<span data-ttu-id="ce55d-170">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-170">300</span></span>  <br/> |<span data-ttu-id="ce55d-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ce55d-p109">O 0 é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="ce55d-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="ce55d-174">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="ce55d-175">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce55d-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="ce55d-176">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="ce55d-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ce55d-177">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="ce55d-179">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="ce55d-181">Se houver quaisquer outros registros MX, remova-os.</span><span class="sxs-lookup"><span data-stu-id="ce55d-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ce55d-182">O AWS armazena registros MX como um conjunto que pode conter vários registros.</span><span class="sxs-lookup"><span data-stu-id="ce55d-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="ce55d-183">**Não** selecione **excluir conjunto de registros**, pois isso excluirá todos os seus registros MX, incluindo aquele que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="ce55d-184">Em vez disso, use as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce55d-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="ce55d-185">Primeiro, selecione o conjunto de registros MX.</span><span class="sxs-lookup"><span data-stu-id="ce55d-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="ce55d-187">Em seguida, na área **Editar Conjunto de Registros**, exclua cada registro MX obsoleto selecionando a entrada na caixa **Valor** e, em seguida, pressione a tecla **Excluir** em seu teclado.</span><span class="sxs-lookup"><span data-stu-id="ce55d-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="ce55d-189">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ce55d-191">Adicionar os cinco registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce55d-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ce55d-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ce55d-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ce55d-p112">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ce55d-195">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ce55d-196">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ce55d-197">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ce55d-198">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="ce55d-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="ce55d-199">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce55d-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ce55d-200">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="ce55d-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ce55d-201">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ce55d-201">**Name**</span></span>|<span data-ttu-id="ce55d-202">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce55d-202">**Type**</span></span>|<span data-ttu-id="ce55d-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ce55d-203">**Alias**</span></span>|<span data-ttu-id="ce55d-204">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="ce55d-205">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ce55d-205">**Value**</span></span>|<span data-ttu-id="ce55d-206">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="ce55d-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce55d-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ce55d-207">autodiscover</span></span>  <br/> |<span data-ttu-id="ce55d-208">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="ce55d-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ce55d-209">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-209">No</span></span>  <br/> |<span data-ttu-id="ce55d-210">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-210">300</span></span>  <br/> |<span data-ttu-id="ce55d-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="ce55d-212">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ce55d-213">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="ce55d-214">sip</span><span class="sxs-lookup"><span data-stu-id="ce55d-214">sip</span></span>  <br/> |<span data-ttu-id="ce55d-215">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="ce55d-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ce55d-216">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-216">No</span></span>  <br/> |<span data-ttu-id="ce55d-217">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-217">300</span></span>  <br/> |<span data-ttu-id="ce55d-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ce55d-219">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ce55d-220">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="ce55d-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ce55d-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ce55d-222">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="ce55d-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ce55d-223">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-223">No</span></span>  <br/> |<span data-ttu-id="ce55d-224">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-224">300</span></span>  <br/> |<span data-ttu-id="ce55d-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ce55d-226">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ce55d-227">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="ce55d-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ce55d-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ce55d-229">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="ce55d-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ce55d-230">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-230">No</span></span>  <br/> |<span data-ttu-id="ce55d-231">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-231">300</span></span>  <br/> |<span data-ttu-id="ce55d-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="ce55d-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="ce55d-233">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ce55d-234">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="ce55d-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ce55d-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ce55d-236">CNAME - Nome canônico</span><span class="sxs-lookup"><span data-stu-id="ce55d-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ce55d-237">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-237">No</span></span>  <br/> |<span data-ttu-id="ce55d-238">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-238">300</span></span>  <br/> |<span data-ttu-id="ce55d-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="ce55d-240">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ce55d-241">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="ce55d-243">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="ce55d-245">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="ce55d-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="ce55d-246">Na página **zonas hospedadas** , selecione **criar conjunto de registros**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="ce55d-247">Repita esse processo até ter criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="ce55d-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ce55d-248">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="ce55d-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ce55d-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ce55d-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce55d-250">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="ce55d-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ce55d-251">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="ce55d-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ce55d-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce55d-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ce55d-253">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ce55d-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ce55d-254">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="ce55d-254">Need examples?</span></span> <span data-ttu-id="ce55d-255">Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). </span><span class="sxs-lookup"><span data-stu-id="ce55d-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="ce55d-256">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="ce55d-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="ce55d-257">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="ce55d-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="ce55d-258">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ce55d-259">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ce55d-260">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ce55d-261">Selecione o conjunto de registros **txt** .</span><span class="sxs-lookup"><span data-stu-id="ce55d-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="ce55d-p115">Na área **Editar Conjunto de Registros**, ao final da entrada atual na caixa **Valor:** para o registro existente, pressione Enter em seu teclado para criar uma nova linha; e, em seguida, nessa linha nova (sob o valor existente), digite ou copie e cole os valores da tabela a seguir. (Você pode ver um exemplo na ilustração abaixo da tabela).</span><span class="sxs-lookup"><span data-stu-id="ce55d-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="ce55d-265">**Valor:**</span><span class="sxs-lookup"><span data-stu-id="ce55d-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="ce55d-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ce55d-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ce55d-p116">(As aspas necessárias para as instruções na tela são fornecidas automaticamente. Não é necessário inseri-las manualmente.)  </span><span class="sxs-lookup"><span data-stu-id="ce55d-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="ce55d-269">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="ce55d-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="ce55d-271">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ce55d-273">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="ce55d-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ce55d-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ce55d-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ce55d-p117">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ce55d-277">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ce55d-278">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce55d-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ce55d-279">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ce55d-280">Adicione o primeiro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="ce55d-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="ce55d-281">Na área **Criar Conjunto de Registros**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce55d-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ce55d-282">Escolha os valores **Tipo** e **Política de Roteamento** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="ce55d-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ce55d-283">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ce55d-283">**Name**</span></span>|<span data-ttu-id="ce55d-284">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce55d-284">**Type**</span></span>|<span data-ttu-id="ce55d-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ce55d-285">**Alias**</span></span>|<span data-ttu-id="ce55d-286">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="ce55d-287">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ce55d-287">**Value**</span></span>|<span data-ttu-id="ce55d-288">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="ce55d-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce55d-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="ce55d-289">_sip._tls</span></span>|<span data-ttu-id="ce55d-290">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="ce55d-290">SRV - Service locator</span></span>|<span data-ttu-id="ce55d-291">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-291">No</span></span>|<span data-ttu-id="ce55d-292">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-292">300</span></span>|<span data-ttu-id="ce55d-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="ce55d-294">**Esse valor deve terminar com um ponto (.)**></span><span class="sxs-lookup"><span data-stu-id="ce55d-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="ce55d-295">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="ce55d-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="ce55d-296">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-296">Simple</span></span>|
    |<span data-ttu-id="ce55d-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="ce55d-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ce55d-298">SRV - Localizador de serviço</span><span class="sxs-lookup"><span data-stu-id="ce55d-298">SRV - Service locator</span></span>|<span data-ttu-id="ce55d-299">Não</span><span class="sxs-lookup"><span data-stu-id="ce55d-299">No</span></span>|<span data-ttu-id="ce55d-300">300</span><span class="sxs-lookup"><span data-stu-id="ce55d-300">300</span></span>|<span data-ttu-id="ce55d-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce55d-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="ce55d-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ce55d-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="ce55d-303">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="ce55d-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="ce55d-304">Simples</span><span class="sxs-lookup"><span data-stu-id="ce55d-304">Simple</span></span>|
   
    ![AWS-BP-configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="ce55d-306">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ce55d-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="ce55d-308">Para adicionar o outro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="ce55d-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="ce55d-309">Na página **zonas hospedadas** , selecione **criar conjunto de registros**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="ce55d-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ce55d-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ce55d-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ce55d-311">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="ce55d-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ce55d-312">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce55d-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
