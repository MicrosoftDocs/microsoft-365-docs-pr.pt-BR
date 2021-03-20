---
title: Criar registros DNS no Register365 para a Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Register365 para Microsoft.
ms.openlocfilehash: a0bf077a6e034add48e9745711fb37d59e2c8203
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910001"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="a068c-103">Criar registros DNS no Register365 para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a068c-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="a068c-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="a068c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a068c-105">Se você usa o Register365 como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="a068c-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="a068c-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="a068c-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="a068c-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a068c-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="a068c-108">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a068c-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="a068c-109">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a068c-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="a068c-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="a068c-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a068c-111">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a068c-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="a068c-112">Depois de adicionar esses registros na Microsoft, seu domínio será definido para trabalhar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a068c-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a068c-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a068c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a068c-116">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a068c-116">Add a TXT record for verification</span></span>
<span data-ttu-id="a068c-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a068c-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a068c-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="a068c-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a068c-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="a068c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a068c-p104">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a068c-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="a068c-125">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a068c-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="a068c-126">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="a068c-126">(You may have to scroll down.)</span></span>
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="a068c-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a068c-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a068c-129">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a068c-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="a068c-130">(Se precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="a068c-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="a068c-131">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="a068c-132">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="a068c-132">**Host name**</span></span>|<span data-ttu-id="a068c-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a068c-133">**Type**</span></span>|<span data-ttu-id="a068c-134">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="a068c-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a068c-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a068c-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a068c-136">TXT</span><span class="sxs-lookup"><span data-stu-id="a068c-136">TXT</span></span>  <br/> |<span data-ttu-id="a068c-137">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a068c-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a068c-138">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a068c-138">**Note:** This is an example.</span></span> <span data-ttu-id="a068c-139">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="a068c-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a068c-140">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a068c-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="a068c-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-142">Select **Save**.</span></span>
    
    <span data-ttu-id="a068c-143">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-143">(You may have to scroll down.)</span></span>
    
    ![Selecione Salvar.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="a068c-145">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="a068c-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a068c-146">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="a068c-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a068c-147">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="a068c-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a068c-148">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="a068c-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a068c-149">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="a068c-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a068c-150">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="a068c-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a068c-151">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a068c-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a068c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a068c-155">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a068c-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a068c-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a068c-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a068c-p107">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a068c-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="a068c-160">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a068c-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="a068c-161">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="a068c-161">(You may have to scroll down.)</span></span>
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="a068c-163">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros MX**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a068c-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a068c-164">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="a068c-165">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="a068c-165">**Host name**</span></span>|<span data-ttu-id="a068c-166">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a068c-166">**Priority**</span></span>|<span data-ttu-id="a068c-167">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="a068c-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a068c-168">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="a068c-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a068c-169">1</span><span class="sxs-lookup"><span data-stu-id="a068c-169">1</span></span>  <br/> <span data-ttu-id="a068c-170">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="a068c-170">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="a068c-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a068c-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a068c-172">**Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a068c-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="a068c-173">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a068c-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="a068c-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-175">Select **Save**.</span></span>
    
    <span data-ttu-id="a068c-176">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-176">(You may have to scroll down.)</span></span>
    
    ![Selecione Salvar.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="a068c-178">Se houver outros registros MX na seção **Registros MX**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="a068c-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="a068c-180">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-180">Select **Save**.</span></span>
    
    <span data-ttu-id="a068c-181">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-181">(You may have to scroll down.)</span></span>
    
    ![Selecione Salvar.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a068c-183">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a068c-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a068c-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a068c-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a068c-p109">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a068c-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="a068c-188">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a068c-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="a068c-189">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="a068c-189">(You may have to scroll down.)</span></span>
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="a068c-191">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros A, CNAME, AAAA, TXT e NS**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a068c-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a068c-192">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a068c-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="a068c-193">(Se precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="a068c-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="a068c-194">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="a068c-195">\*\*\*\*Nome do host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a068c-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="a068c-196">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a068c-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="a068c-197">\*\*\*\*Resultado\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a068c-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a068c-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a068c-198">autodiscover</span></span>  <br/> |<span data-ttu-id="a068c-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a068c-199">CNAME</span></span>  <br/> |<span data-ttu-id="a068c-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a068c-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a068c-201">sip</span><span class="sxs-lookup"><span data-stu-id="a068c-201">sip</span></span>  <br/> |<span data-ttu-id="a068c-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="a068c-202">CNAME</span></span>  <br/> |<span data-ttu-id="a068c-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a068c-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a068c-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a068c-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a068c-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="a068c-205">CNAME</span></span>  <br/> |<span data-ttu-id="a068c-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a068c-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a068c-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a068c-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a068c-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="a068c-208">CNAME</span></span>  <br/> |<span data-ttu-id="a068c-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a068c-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a068c-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a068c-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a068c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a068c-211">CNAME</span></span>  <br/> |<span data-ttu-id="a068c-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a068c-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="a068c-214">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-214">Select **Save**.</span></span>
    
    ![Selecione Salvar.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a068c-216">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="a068c-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a068c-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a068c-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a068c-218">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="a068c-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a068c-219">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="a068c-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a068c-220">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a068c-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a068c-221">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a068c-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a068c-p111">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a068c-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="a068c-225">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a068c-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="a068c-226">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="a068c-226">(You may have to scroll down.)</span></span>
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="a068c-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a068c-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a068c-229">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a068c-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="a068c-230">(Se precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)</span><span class="sxs-lookup"><span data-stu-id="a068c-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="a068c-231">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="a068c-232">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="a068c-232">**Host name**</span></span>|<span data-ttu-id="a068c-233">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a068c-233">**Type**</span></span>|<span data-ttu-id="a068c-234">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="a068c-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a068c-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a068c-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a068c-236">TXT</span><span class="sxs-lookup"><span data-stu-id="a068c-236">TXT</span></span>  <br/> |<span data-ttu-id="a068c-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a068c-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="a068c-238">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a068c-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="a068c-240">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-240">Select **Save**.</span></span>
    
    <span data-ttu-id="a068c-241">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-241">(You may have to scroll down.)</span></span>
    
    ![Selecione Salvar.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a068c-243">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a068c-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a068c-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a068c-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a068c-p112">Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a068c-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="a068c-248">Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a068c-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="a068c-249">Pode ser necessário rolar a tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="a068c-249">(You may have to scroll down.)</span></span>
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="a068c-251">Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a068c-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a068c-252">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="a068c-253">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a068c-253">**Name**</span></span>|<span data-ttu-id="a068c-254">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a068c-254">**Priority**</span></span>|<span data-ttu-id="a068c-255">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="a068c-255">**Weight**</span></span>|<span data-ttu-id="a068c-256">**Porta**</span><span class="sxs-lookup"><span data-stu-id="a068c-256">**Port**</span></span>|<span data-ttu-id="a068c-257">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="a068c-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a068c-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a068c-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="a068c-259">100</span><span class="sxs-lookup"><span data-stu-id="a068c-259">100</span></span>  <br/> |<span data-ttu-id="a068c-260">1</span><span class="sxs-lookup"><span data-stu-id="a068c-260">1</span></span>  <br/> |<span data-ttu-id="a068c-261">443</span><span class="sxs-lookup"><span data-stu-id="a068c-261">443</span></span>  <br/> |<span data-ttu-id="a068c-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a068c-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a068c-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a068c-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a068c-264">100</span><span class="sxs-lookup"><span data-stu-id="a068c-264">100</span></span>  <br/> |<span data-ttu-id="a068c-265">1</span><span class="sxs-lookup"><span data-stu-id="a068c-265">1</span></span>  <br/> |<span data-ttu-id="a068c-266">5061</span><span class="sxs-lookup"><span data-stu-id="a068c-266">5061</span></span>  <br/> |<span data-ttu-id="a068c-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a068c-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Inserindo valores na seção Registros de serviço](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="a068c-269">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a068c-269">Select **Save**.</span></span>
    
    <span data-ttu-id="a068c-270">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="a068c-270">(You may have to scroll down.)</span></span>
    
    ![Selecione Salvar.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="a068c-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a068c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
