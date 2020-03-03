---
title: Criar registros DNS no site Register365 para o Office 365
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Register365 para o Office 365.
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362846"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="631d0-103">Criar registros DNS no site Register365 para o Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="631d0-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="631d0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="631d0-105">Se você usa o Register365 como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="631d0-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="631d0-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="631d0-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="631d0-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="631d0-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="631d0-108">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="631d0-109">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="631d0-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="631d0-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="631d0-111">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="631d0-112">Depois que você adicionar esses registros no Office 365, o domínio é configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="631d0-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="631d0-113">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="631d0-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="631d0-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="631d0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="631d0-117">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="631d0-117">Add a TXT record for verification</span></span>
<span data-ttu-id="631d0-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="631d0-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="631d0-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="631d0-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="631d0-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="631d0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="631d0-p104">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="631d0-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="631d0-126">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="631d0-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="631d0-127">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="631d0-127">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="631d0-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="631d0-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="631d0-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="631d0-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="631d0-131">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="631d0-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="631d0-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="631d0-133">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="631d0-133">**Host name**</span></span>|<span data-ttu-id="631d0-134">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="631d0-134">**Type**</span></span>|<span data-ttu-id="631d0-135">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="631d0-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="631d0-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="631d0-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="631d0-137">TXT</span><span class="sxs-lookup"><span data-stu-id="631d0-137">TXT</span></span>  <br/> |<span data-ttu-id="631d0-138">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="631d0-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="631d0-139">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="631d0-139">**Note:** This is an example.</span></span> <span data-ttu-id="631d0-140">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="631d0-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="631d0-141">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="631d0-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="631d0-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-143">Select **Save**.</span></span>
    
    <span data-ttu-id="631d0-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-144">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="631d0-146">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="631d0-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="631d0-147">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="631d0-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="631d0-148">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="631d0-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="631d0-149">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="631d0-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="631d0-150">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="631d0-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="631d0-151">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="631d0-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="631d0-152">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="631d0-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="631d0-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="631d0-156">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="631d0-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="631d0-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="631d0-p107">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="631d0-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="631d0-161">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="631d0-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="631d0-162">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="631d0-162">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="631d0-164">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros MX**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="631d0-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="631d0-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="631d0-166">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="631d0-166">**Host name**</span></span>|<span data-ttu-id="631d0-167">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="631d0-167">**Priority**</span></span>|<span data-ttu-id="631d0-168">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="631d0-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="631d0-169">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="631d0-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="631d0-170">1</span><span class="sxs-lookup"><span data-stu-id="631d0-170">1</span></span>  <br/> <span data-ttu-id="631d0-171">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="631d0-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="631d0-172">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="631d0-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="631d0-173">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="631d0-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="631d0-174">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="631d0-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="631d0-176">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-176">Select **Save**.</span></span>
    
    <span data-ttu-id="631d0-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-177">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="631d0-179">Se houver outros registros MX na seção **Registros MX**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="631d0-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="631d0-181">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-181">Select **Save**.</span></span>
    
    <span data-ttu-id="631d0-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-182">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="631d0-184">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="631d0-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="631d0-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="631d0-p109">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="631d0-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="631d0-189">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="631d0-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="631d0-190">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="631d0-190">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="631d0-192">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros A, CNAME, AAAA, TXT e NS**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="631d0-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="631d0-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="631d0-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="631d0-194">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="631d0-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="631d0-195">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="631d0-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="631d0-196">\*\*\*\*Nome do host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="631d0-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="631d0-197">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="631d0-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="631d0-198">\*\*\*\*Resultado\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="631d0-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="631d0-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="631d0-199">autodiscover</span></span>  <br/> |<span data-ttu-id="631d0-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="631d0-200">CNAME</span></span>  <br/> |<span data-ttu-id="631d0-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="631d0-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="631d0-202">sip</span><span class="sxs-lookup"><span data-stu-id="631d0-202">sip</span></span>  <br/> |<span data-ttu-id="631d0-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="631d0-203">CNAME</span></span>  <br/> |<span data-ttu-id="631d0-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="631d0-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="631d0-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="631d0-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="631d0-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="631d0-206">CNAME</span></span>  <br/> |<span data-ttu-id="631d0-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="631d0-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="631d0-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="631d0-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="631d0-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="631d0-209">CNAME</span></span>  <br/> |<span data-ttu-id="631d0-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="631d0-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="631d0-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="631d0-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="631d0-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="631d0-212">CNAME</span></span>  <br/> |<span data-ttu-id="631d0-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="631d0-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="631d0-215">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-215">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="631d0-217">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="631d0-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="631d0-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="631d0-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="631d0-219">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="631d0-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="631d0-220">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="631d0-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="631d0-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="631d0-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="631d0-222">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="631d0-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="631d0-p111">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="631d0-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="631d0-226">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="631d0-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="631d0-227">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="631d0-227">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="631d0-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="631d0-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="631d0-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="631d0-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="631d0-231">(Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="631d0-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="631d0-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="631d0-233">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="631d0-233">**Host name**</span></span>|<span data-ttu-id="631d0-234">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="631d0-234">**Type**</span></span>|<span data-ttu-id="631d0-235">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="631d0-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="631d0-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="631d0-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="631d0-237">TXT</span><span class="sxs-lookup"><span data-stu-id="631d0-237">TXT</span></span>  <br/> |<span data-ttu-id="631d0-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="631d0-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="631d0-239">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="631d0-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="631d0-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-241">Select **Save**.</span></span>
    
    <span data-ttu-id="631d0-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-242">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="631d0-244">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="631d0-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="631d0-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="631d0-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="631d0-p112">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="631d0-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="631d0-249">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="631d0-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="631d0-250">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="631d0-250">(You may have to scroll down.)</span></span>
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="631d0-252">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="631d0-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="631d0-253">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="631d0-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="631d0-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="631d0-254">**Name**</span></span>|<span data-ttu-id="631d0-255">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="631d0-255">**Priority**</span></span>|<span data-ttu-id="631d0-256">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="631d0-256">**Weight**</span></span>|<span data-ttu-id="631d0-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="631d0-257">**Port**</span></span>|<span data-ttu-id="631d0-258">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="631d0-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="631d0-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="631d0-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="631d0-260">100</span><span class="sxs-lookup"><span data-stu-id="631d0-260">100</span></span>  <br/> |<span data-ttu-id="631d0-261">1</span><span class="sxs-lookup"><span data-stu-id="631d0-261">1</span></span>  <br/> |<span data-ttu-id="631d0-262">443</span><span class="sxs-lookup"><span data-stu-id="631d0-262">443</span></span>  <br/> |<span data-ttu-id="631d0-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="631d0-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="631d0-264">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="631d0-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="631d0-265">100</span><span class="sxs-lookup"><span data-stu-id="631d0-265">100</span></span>  <br/> |<span data-ttu-id="631d0-266">1</span><span class="sxs-lookup"><span data-stu-id="631d0-266">1</span></span>  <br/> |<span data-ttu-id="631d0-267">5061</span><span class="sxs-lookup"><span data-stu-id="631d0-267">5061</span></span>  <br/> |<span data-ttu-id="631d0-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="631d0-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Inserindo valores na seção registros de serviço](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="631d0-270">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="631d0-270">Select **Save**.</span></span>
    
    <span data-ttu-id="631d0-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="631d0-271">(You may have to scroll down.)</span></span>
    
    ![Selecione salvar](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="631d0-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="631d0-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
