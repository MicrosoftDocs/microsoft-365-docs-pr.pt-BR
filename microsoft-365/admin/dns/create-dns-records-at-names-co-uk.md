---
title: Criar registros DNS no site Names.co.uk para Office 365
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Names.co.uk para o Office 365.
ms.openlocfilehash: d27cd22b0047cf58def01533a486c7641f50148e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348132"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="41ac4-103">Criar registros DNS no site Names.co.uk para Office 365</span><span class="sxs-lookup"><span data-stu-id="41ac4-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="41ac4-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="41ac4-105">Se você usa a Names.co.uk como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="41ac4-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="41ac4-106">Depois que você adicionar esses registros na Names.co.uk, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="41ac4-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="41ac4-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="41ac4-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="41ac4-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="41ac4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="41ac4-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="41ac4-111">Add a TXT record for verification</span></span>
<span data-ttu-id="41ac4-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="41ac4-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="41ac4-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41ac4-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="41ac4-p104">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="41ac4-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="41ac4-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="41ac4-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="41ac4-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="41ac4-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="41ac4-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="41ac4-125">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="41ac4-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="41ac4-127">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="41ac4-127">**Host name**</span></span>|<span data-ttu-id="41ac4-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41ac4-128">**Type**</span></span>|<span data-ttu-id="41ac4-129">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="41ac4-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="41ac4-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="41ac4-131">TXT</span><span class="sxs-lookup"><span data-stu-id="41ac4-131">TXT</span></span>  <br/> |<span data-ttu-id="41ac4-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="41ac4-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="41ac4-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="41ac4-133">**Note:** This is an example.</span></span> <span data-ttu-id="41ac4-134">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="41ac4-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="41ac4-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="41ac4-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="41ac4-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-137">Select **Save**.</span></span>
    
    <span data-ttu-id="41ac4-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="41ac4-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="41ac4-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="41ac4-141">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="41ac4-142">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="41ac4-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="41ac4-143">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="41ac4-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="41ac4-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="41ac4-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="41ac4-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="41ac4-146">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="41ac4-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="41ac4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="41ac4-150">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41ac4-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="41ac4-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="41ac4-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="41ac4-p107">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="41ac4-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="41ac4-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="41ac4-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="41ac4-158">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros mail exchange**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="41ac4-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="41ac4-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="41ac4-160">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="41ac4-160">**Host name**</span></span>|<span data-ttu-id="41ac4-161">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="41ac4-161">**Priority**</span></span>|<span data-ttu-id="41ac4-162">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="41ac4-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="41ac4-163">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="41ac4-164">1</span><span class="sxs-lookup"><span data-stu-id="41ac4-164">1</span></span>  <br/> <span data-ttu-id="41ac4-165">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="41ac4-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="41ac4-166">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="41ac4-167">> [!NOTE]> obter sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="41ac4-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="41ac4-168">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="41ac4-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="41ac4-170">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-170">Select **Save**.</span></span>
    
    <span data-ttu-id="41ac4-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="41ac4-173">Se houver outros registros MX listados na seção **Registros mail exchange**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="41ac4-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="41ac4-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-175">Select **Save**.</span></span>
    
    <span data-ttu-id="41ac4-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="41ac4-178">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41ac4-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="41ac4-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="41ac4-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="41ac4-p109">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="41ac4-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="41ac4-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="41ac4-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="41ac4-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="41ac4-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="41ac4-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="41ac4-188">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="41ac4-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="41ac4-190">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="41ac4-190">**Host Name**</span></span>|<span data-ttu-id="41ac4-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41ac4-191">**Type**</span></span>|<span data-ttu-id="41ac4-192">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="41ac4-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="41ac4-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="41ac4-193">autodiscover</span></span>  <br/> |<span data-ttu-id="41ac4-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="41ac4-194">CNAME</span></span>  <br/> |<span data-ttu-id="41ac4-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="41ac4-196">sip</span><span class="sxs-lookup"><span data-stu-id="41ac4-196">sip</span></span>  <br/> |<span data-ttu-id="41ac4-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="41ac4-197">CNAME</span></span>  <br/> |<span data-ttu-id="41ac4-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="41ac4-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="41ac4-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="41ac4-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="41ac4-200">CNAME</span></span>  <br/> |<span data-ttu-id="41ac4-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="41ac4-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="41ac4-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="41ac4-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="41ac4-203">CNAME</span></span>  <br/> |<span data-ttu-id="41ac4-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="41ac4-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="41ac4-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="41ac4-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="41ac4-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="41ac4-206">CNAME</span></span>  <br/> |<span data-ttu-id="41ac4-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="41ac4-209">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="41ac4-211">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="41ac4-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="41ac4-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="41ac4-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="41ac4-213">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="41ac4-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="41ac4-214">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="41ac4-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="41ac4-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="41ac4-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="41ac4-216">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="41ac4-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="41ac4-p111">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="41ac4-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="41ac4-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="41ac4-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="41ac4-223">Na página **zonas DNS na conta** , na coluna **nome do domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="41ac4-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="41ac4-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="41ac4-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="41ac4-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="41ac4-227">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="41ac4-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="41ac4-229">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="41ac4-229">**Host name**</span></span>|<span data-ttu-id="41ac4-230">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41ac4-230">**Type**</span></span>|<span data-ttu-id="41ac4-231">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="41ac4-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="41ac4-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="41ac4-233">TXT</span><span class="sxs-lookup"><span data-stu-id="41ac4-233">TXT</span></span>  <br/> |<span data-ttu-id="41ac4-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="41ac4-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="41ac4-235">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="41ac4-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="41ac4-237">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-237">Select **Save**.</span></span>
    
    <span data-ttu-id="41ac4-238">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="41ac4-240">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="41ac4-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="41ac4-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="41ac4-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="41ac4-p112">Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="41ac4-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="41ac4-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="41ac4-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="41ac4-248">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores da tabela a seguir nas caixas do novo registro.</span><span class="sxs-lookup"><span data-stu-id="41ac4-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="41ac4-249">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="41ac4-250">**Nome**</span><span class="sxs-lookup"><span data-stu-id="41ac4-250">**Name**</span></span>|<span data-ttu-id="41ac4-251">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="41ac4-251">**Priority**</span></span>|<span data-ttu-id="41ac4-252">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="41ac4-252">**Weight**</span></span>|<span data-ttu-id="41ac4-253">**Porta**</span><span class="sxs-lookup"><span data-stu-id="41ac4-253">**Port**</span></span>|<span data-ttu-id="41ac4-254">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="41ac4-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="41ac4-255">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="41ac4-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="41ac4-256">100</span><span class="sxs-lookup"><span data-stu-id="41ac4-256">100</span></span>  <br/> |<span data-ttu-id="41ac4-257">1</span><span class="sxs-lookup"><span data-stu-id="41ac4-257">1</span></span>  <br/> |<span data-ttu-id="41ac4-258">443</span><span class="sxs-lookup"><span data-stu-id="41ac4-258">443</span></span>  <br/> |<span data-ttu-id="41ac4-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="41ac4-260">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="41ac4-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="41ac4-261">100</span><span class="sxs-lookup"><span data-stu-id="41ac4-261">100</span></span>  <br/> |<span data-ttu-id="41ac4-262">1</span><span class="sxs-lookup"><span data-stu-id="41ac4-262">1</span></span>  <br/> |<span data-ttu-id="41ac4-263">5061</span><span class="sxs-lookup"><span data-stu-id="41ac4-263">5061</span></span>  <br/> |<span data-ttu-id="41ac4-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="41ac4-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="41ac4-266">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="41ac4-266">Select **Save**.</span></span>
    
    <span data-ttu-id="41ac4-267">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="41ac4-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="41ac4-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="41ac4-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
