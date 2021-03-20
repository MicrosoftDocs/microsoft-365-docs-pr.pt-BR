---
title: Criar registros DNS no Names.co.uk para a Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços Names.co.uk para a Microsoft.
ms.openlocfilehash: ddd7286d983a0f180c9aefdbf5218eb9765c8669
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910037"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="d8760-103">Criar registros DNS no Names.co.uk para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8760-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="d8760-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="d8760-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d8760-105">Se você usa a Names.co.uk como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="d8760-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="d8760-106">Depois de adicionar esses registros Names.co.uk, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8760-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="d8760-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8760-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d8760-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d8760-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d8760-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d8760-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d8760-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="d8760-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8760-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="d8760-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d8760-p104">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d8760-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8760-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8760-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8760-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8760-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8760-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d8760-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8760-123">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="d8760-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d8760-124">(Se precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="d8760-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d8760-125">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="d8760-126">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d8760-126">**Host name**</span></span>|<span data-ttu-id="d8760-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8760-127">**Type**</span></span>|<span data-ttu-id="d8760-128">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d8760-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8760-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d8760-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d8760-130">TXT</span><span class="sxs-lookup"><span data-stu-id="d8760-130">TXT</span></span>  <br/> |<span data-ttu-id="d8760-131">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d8760-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d8760-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d8760-132">**Note:** This is an example.</span></span> <span data-ttu-id="d8760-133">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="d8760-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d8760-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d8760-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="d8760-136">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-136">Select **Save**.</span></span>
    
    <span data-ttu-id="d8760-137">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="d8760-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="d8760-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d8760-140">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="d8760-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d8760-141">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="d8760-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d8760-142">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="d8760-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d8760-143">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="d8760-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d8760-144">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d8760-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d8760-145">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d8760-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8760-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d8760-149">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8760-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d8760-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d8760-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d8760-p107">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d8760-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8760-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8760-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8760-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8760-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8760-157">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros mail exchange**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d8760-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8760-158">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8760-159">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d8760-159">**Host name**</span></span>|<span data-ttu-id="d8760-160">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d8760-160">**Priority**</span></span>|<span data-ttu-id="d8760-161">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d8760-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8760-162">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="d8760-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d8760-163">1</span><span class="sxs-lookup"><span data-stu-id="d8760-163">1</span></span>  <br/> <span data-ttu-id="d8760-164">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="d8760-164">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="d8760-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d8760-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d8760-166">> [!NOTE]> Obter sua  *\<domain-key\>*  conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8760-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="d8760-167">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d8760-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="d8760-169">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-169">Select **Save**.</span></span>
    
    <span data-ttu-id="d8760-170">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="d8760-172">Se houver outros registros MX listados na seção **Registros mail exchange**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="d8760-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="d8760-174">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-174">Select **Save**.</span></span>
    
    <span data-ttu-id="d8760-175">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d8760-177">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8760-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d8760-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d8760-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d8760-p109">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d8760-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8760-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8760-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8760-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8760-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8760-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d8760-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8760-186">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="d8760-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d8760-187">(Se precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="d8760-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d8760-188">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8760-189">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="d8760-189">**Host Name**</span></span>|<span data-ttu-id="d8760-190">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8760-190">**Type**</span></span>|<span data-ttu-id="d8760-191">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d8760-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8760-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d8760-192">autodiscover</span></span>  <br/> |<span data-ttu-id="d8760-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8760-193">CNAME</span></span>  <br/> |<span data-ttu-id="d8760-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d8760-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d8760-195">sip</span><span class="sxs-lookup"><span data-stu-id="d8760-195">sip</span></span>  <br/> |<span data-ttu-id="d8760-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8760-196">CNAME</span></span>  <br/> |<span data-ttu-id="d8760-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8760-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d8760-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d8760-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d8760-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8760-199">CNAME</span></span>  <br/> |<span data-ttu-id="d8760-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8760-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d8760-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d8760-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d8760-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8760-202">CNAME</span></span>  <br/> |<span data-ttu-id="d8760-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d8760-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d8760-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d8760-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d8760-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="d8760-205">CNAME</span></span>  <br/> |<span data-ttu-id="d8760-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d8760-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="d8760-208">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d8760-210">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="d8760-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d8760-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d8760-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8760-212">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="d8760-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d8760-213">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="d8760-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d8760-214">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8760-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d8760-215">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d8760-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="d8760-p111">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d8760-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8760-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8760-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8760-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8760-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8760-222">Na página **Zonas DNS na Conta,** na coluna **Nome de** domínio, selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="d8760-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="d8760-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d8760-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8760-225">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="d8760-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d8760-226">(Se precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="d8760-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d8760-227">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8760-228">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d8760-228">**Host name**</span></span>|<span data-ttu-id="d8760-229">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8760-229">**Type**</span></span>|<span data-ttu-id="d8760-230">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d8760-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8760-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d8760-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d8760-232">TXT</span><span class="sxs-lookup"><span data-stu-id="d8760-232">TXT</span></span>  <br/> |<span data-ttu-id="d8760-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d8760-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d8760-234">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d8760-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="d8760-236">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-236">Select **Save**.</span></span>
    
    <span data-ttu-id="d8760-237">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d8760-239">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8760-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d8760-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d8760-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d8760-p112">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d8760-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="d8760-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="d8760-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d8760-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d8760-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="d8760-247">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores da tabela a seguir nas caixas do novo registro.</span><span class="sxs-lookup"><span data-stu-id="d8760-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d8760-248">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d8760-249">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d8760-249">**Name**</span></span>|<span data-ttu-id="d8760-250">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d8760-250">**Priority**</span></span>|<span data-ttu-id="d8760-251">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="d8760-251">**Weight**</span></span>|<span data-ttu-id="d8760-252">**Porta**</span><span class="sxs-lookup"><span data-stu-id="d8760-252">**Port**</span></span>|<span data-ttu-id="d8760-253">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="d8760-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d8760-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d8760-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="d8760-255">100</span><span class="sxs-lookup"><span data-stu-id="d8760-255">100</span></span>  <br/> |<span data-ttu-id="d8760-256">1</span><span class="sxs-lookup"><span data-stu-id="d8760-256">1</span></span>  <br/> |<span data-ttu-id="d8760-257">443</span><span class="sxs-lookup"><span data-stu-id="d8760-257">443</span></span>  <br/> |<span data-ttu-id="d8760-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8760-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d8760-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d8760-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d8760-260">100</span><span class="sxs-lookup"><span data-stu-id="d8760-260">100</span></span>  <br/> |<span data-ttu-id="d8760-261">1</span><span class="sxs-lookup"><span data-stu-id="d8760-261">1</span></span>  <br/> |<span data-ttu-id="d8760-262">5061</span><span class="sxs-lookup"><span data-stu-id="d8760-262">5061</span></span>  <br/> |<span data-ttu-id="d8760-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d8760-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="d8760-265">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8760-265">Select **Save**.</span></span>
    
    <span data-ttu-id="d8760-266">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="d8760-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="d8760-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8760-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
