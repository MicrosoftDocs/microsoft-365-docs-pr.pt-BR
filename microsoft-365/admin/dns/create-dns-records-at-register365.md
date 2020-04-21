---
title: Criar registros DNS no Register365 para Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Register365 para a Microsoft.
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629258"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="ce0cd-103">Criar registros DNS no Register365 para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="ce0cd-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ce0cd-105">Se você usa o Register365 como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="ce0cd-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="ce0cd-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="ce0cd-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="ce0cd-108">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="ce0cd-109">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ce0cd-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="ce0cd-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ce0cd-111">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ce0cd-112">Depois que você adicionar esses registros à Microsoft, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="ce0cd-113">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ce0cd-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ce0cd-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ce0cd-117">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="ce0cd-117">Add a TXT record for verification</span></span>
<span data-ttu-id="ce0cd-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ce0cd-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ce0cd-119">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="ce0cd-120">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce0cd-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ce0cd-p104">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="ce0cd-126">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ce0cd-127">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-127">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="ce0cd-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce0cd-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ce0cd-131">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ce0cd-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ce0cd-133">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-133">**Host name**</span></span>|<span data-ttu-id="ce0cd-134">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-134">**Type**</span></span>|<span data-ttu-id="ce0cd-135">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ce0cd-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ce0cd-137">TXT</span><span class="sxs-lookup"><span data-stu-id="ce0cd-137">TXT</span></span>  <br/> |<span data-ttu-id="ce0cd-138">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ce0cd-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ce0cd-139">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-139">**Note:** This is an example.</span></span> <span data-ttu-id="ce0cd-140">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="ce0cd-141">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ce0cd-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="ce0cd-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-143">Select **Save**.</span></span>
    
    <span data-ttu-id="ce0cd-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-144">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="ce0cd-146">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ce0cd-147">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ce0cd-148">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ce0cd-149">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ce0cd-150">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ce0cd-151">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ce0cd-152">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ce0cd-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ce0cd-156">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ce0cd-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ce0cd-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ce0cd-p107">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="ce0cd-161">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ce0cd-162">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-162">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="ce0cd-164">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros MX**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce0cd-165">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ce0cd-166">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-166">**Host name**</span></span>|<span data-ttu-id="ce0cd-167">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-167">**Priority**</span></span>|<span data-ttu-id="ce0cd-168">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ce0cd-169">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ce0cd-170">1</span><span class="sxs-lookup"><span data-stu-id="ce0cd-170">1</span></span>  <br/> <span data-ttu-id="ce0cd-171">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="ce0cd-172">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ce0cd-173">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-173">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="ce0cd-174">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ce0cd-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="ce0cd-176">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-176">Select **Save**.</span></span>
    
    <span data-ttu-id="ce0cd-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-177">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="ce0cd-179">Se houver outros registros MX na seção **Registros MX**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="ce0cd-181">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-181">Select **Save**.</span></span>
    
    <span data-ttu-id="ce0cd-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-182">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ce0cd-184">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-184">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ce0cd-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ce0cd-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ce0cd-p109">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="ce0cd-189">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ce0cd-190">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-190">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="ce0cd-192">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros A, CNAME, AAAA, TXT e NS**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce0cd-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ce0cd-194">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ce0cd-195">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ce0cd-196">\*\*\*\*Nome do host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ce0cd-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="ce0cd-197">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ce0cd-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="ce0cd-198">\*\*\*\*Resultado\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ce0cd-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ce0cd-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ce0cd-199">autodiscover</span></span>  <br/> |<span data-ttu-id="ce0cd-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce0cd-200">CNAME</span></span>  <br/> |<span data-ttu-id="ce0cd-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ce0cd-202">sip</span><span class="sxs-lookup"><span data-stu-id="ce0cd-202">sip</span></span>  <br/> |<span data-ttu-id="ce0cd-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce0cd-203">CNAME</span></span>  <br/> |<span data-ttu-id="ce0cd-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ce0cd-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ce0cd-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ce0cd-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce0cd-206">CNAME</span></span>  <br/> |<span data-ttu-id="ce0cd-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ce0cd-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ce0cd-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ce0cd-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce0cd-209">CNAME</span></span>  <br/> |<span data-ttu-id="ce0cd-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ce0cd-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ce0cd-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ce0cd-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ce0cd-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce0cd-212">CNAME</span></span>  <br/> |<span data-ttu-id="ce0cd-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="ce0cd-215">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-215">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ce0cd-217">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="ce0cd-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ce0cd-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ce0cd-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce0cd-219">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ce0cd-220">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ce0cd-221">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ce0cd-222">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="ce0cd-p111">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="ce0cd-226">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ce0cd-227">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-227">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="ce0cd-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce0cd-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ce0cd-231">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ce0cd-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ce0cd-233">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-233">**Host name**</span></span>|<span data-ttu-id="ce0cd-234">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-234">**Type**</span></span>|<span data-ttu-id="ce0cd-235">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ce0cd-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ce0cd-237">TXT</span><span class="sxs-lookup"><span data-stu-id="ce0cd-237">TXT</span></span>  <br/> |<span data-ttu-id="ce0cd-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ce0cd-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="ce0cd-239">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="ce0cd-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-241">Select **Save**.</span></span>
    
    <span data-ttu-id="ce0cd-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-242">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ce0cd-244">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce0cd-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ce0cd-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ce0cd-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ce0cd-p112">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="ce0cd-249">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ce0cd-250">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-250">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="ce0cd-252">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ce0cd-253">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ce0cd-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-254">**Name**</span></span>|<span data-ttu-id="ce0cd-255">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-255">**Priority**</span></span>|<span data-ttu-id="ce0cd-256">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-256">**Weight**</span></span>|<span data-ttu-id="ce0cd-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-257">**Port**</span></span>|<span data-ttu-id="ce0cd-258">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="ce0cd-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce0cd-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="ce0cd-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="ce0cd-260">100</span><span class="sxs-lookup"><span data-stu-id="ce0cd-260">100</span></span>  <br/> |<span data-ttu-id="ce0cd-261">1</span><span class="sxs-lookup"><span data-stu-id="ce0cd-261">1</span></span>  <br/> |<span data-ttu-id="ce0cd-262">443</span><span class="sxs-lookup"><span data-stu-id="ce0cd-262">443</span></span>  <br/> |<span data-ttu-id="ce0cd-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ce0cd-264">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="ce0cd-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ce0cd-265">100</span><span class="sxs-lookup"><span data-stu-id="ce0cd-265">100</span></span>  <br/> |<span data-ttu-id="ce0cd-266">1</span><span class="sxs-lookup"><span data-stu-id="ce0cd-266">1</span></span>  <br/> |<span data-ttu-id="ce0cd-267">5061</span><span class="sxs-lookup"><span data-stu-id="ce0cd-267">5061</span></span>  <br/> |<span data-ttu-id="ce0cd-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ce0cd-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Inserindo valores na seção registros de serviço](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="ce0cd-270">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce0cd-270">Select **Save**.</span></span>
    
    <span data-ttu-id="ce0cd-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ce0cd-271">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="ce0cd-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce0cd-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
