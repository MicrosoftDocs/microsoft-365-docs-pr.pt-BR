---
title: Criar registros DNS no eNomCentral para Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em eNomCentral para a Microsoft.
ms.openlocfilehash: 601ae58b2b5e196f8bd58cd508ac5722d7f999e4
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049042"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="7dacb-103">Criar registros DNS no eNomCentral para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dacb-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="7dacb-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7dacb-105">Se você usa a eNomCentral como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="7dacb-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7dacb-106">Depois que você adicionar esses registros no eNomCentral, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dacb-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="7dacb-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7dacb-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7dacb-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="7dacb-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7dacb-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7dacb-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7dacb-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7dacb-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="7dacb-116">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7dacb-116">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7dacb-p104">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="7dacb-120">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7dacb-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="7dacb-122">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="7dacb-124">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="7dacb-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7dacb-125">Escolha o valor **tipo de registro** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7dacb-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="7dacb-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="7dacb-126">**Host Name**</span></span> <br/> |<span data-ttu-id="7dacb-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="7dacb-127">**Record Type**</span></span> <br/> |<span data-ttu-id="7dacb-128">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="7dacb-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="7dacb-129">TXT</span><span class="sxs-lookup"><span data-stu-id="7dacb-129">TXT</span></span>  <br/> |<span data-ttu-id="7dacb-130">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7dacb-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7dacb-131">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="7dacb-131">**Note:** This is an example.</span></span> <span data-ttu-id="7dacb-132">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="7dacb-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7dacb-133">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="7dacb-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="7dacb-135">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-135">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="7dacb-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="7dacb-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7dacb-138">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="7dacb-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="7dacb-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="7dacb-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7dacb-140">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="7dacb-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7dacb-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="7dacb-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7dacb-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7dacb-143">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7dacb-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7dacb-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7dacb-147">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dacb-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7dacb-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7dacb-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7dacb-149">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7dacb-149">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7dacb-p107">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="7dacb-153">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7dacb-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="7dacb-155">Na lista suspensa **Gerenciar Domínio**, escolha **Configurações de Email**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="7dacb-157">Na lista suspensa **Seleção de Serviço**, escolha **Usuário (MX)**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="7dacb-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7dacb-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7dacb-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="7dacb-160">**Host Name**</span></span>|<span data-ttu-id="7dacb-161">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="7dacb-161">**Address**</span></span>|<span data-ttu-id="7dacb-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="7dacb-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="7dacb-163">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7dacb-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7dacb-165">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dacb-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="7dacb-166">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="7dacb-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7dacb-167">10 </span><span class="sxs-lookup"><span data-stu-id="7dacb-167">10</span></span>  <br/> <span data-ttu-id="7dacb-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="7dacb-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom-BP-configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="7dacb-170">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-170">Select **save**.</span></span>
    
    ![eNom-BP-configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="7dacb-172">Se houver outros registros MX existentes, marque as caixas de seleção desses registros para escolhê-los.</span><span class="sxs-lookup"><span data-stu-id="7dacb-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="7dacb-174">Selecione **excluir verificado**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7dacb-176">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dacb-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="7dacb-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7dacb-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7dacb-178">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7dacb-178">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7dacb-p109">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="7dacb-182">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7dacb-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="7dacb-184">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="7dacb-186">Selecione **nova linha**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-186">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="7dacb-188">Nas caixas dos seis novos registros, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="7dacb-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="7dacb-189">Escolha o valor **tipo de registro** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7dacb-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="7dacb-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="7dacb-190">**Host Name**</span></span>|<span data-ttu-id="7dacb-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="7dacb-191">**Record Type**</span></span>|<span data-ttu-id="7dacb-192">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="7dacb-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7dacb-193">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="7dacb-193">autodiscover</span></span>  <br/> |<span data-ttu-id="7dacb-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="7dacb-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7dacb-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7dacb-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dacb-197">sip</span><span class="sxs-lookup"><span data-stu-id="7dacb-197">sip</span></span>  <br/> |<span data-ttu-id="7dacb-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="7dacb-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7dacb-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7dacb-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dacb-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7dacb-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7dacb-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="7dacb-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7dacb-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7dacb-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dacb-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7dacb-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7dacb-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="7dacb-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7dacb-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7dacb-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7dacb-208">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dacb-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7dacb-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7dacb-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="7dacb-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7dacb-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7dacb-212">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="7dacb-213">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-213">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7dacb-215">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="7dacb-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7dacb-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7dacb-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dacb-217">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="7dacb-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7dacb-218">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="7dacb-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7dacb-219">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dacb-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7dacb-220">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="7dacb-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="7dacb-221">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7dacb-221">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7dacb-p111">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="7dacb-225">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7dacb-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="7dacb-227">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="7dacb-229">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="7dacb-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="7dacb-230">Escolha o valor **tipo de registro** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7dacb-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="7dacb-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="7dacb-231">**Host Name**</span></span>|<span data-ttu-id="7dacb-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="7dacb-232">**Record Type**</span></span>|<span data-ttu-id="7dacb-233">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="7dacb-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7dacb-234">TXT</span><span class="sxs-lookup"><span data-stu-id="7dacb-234">TXT</span></span>  <br/> |<span data-ttu-id="7dacb-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7dacb-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="7dacb-236">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="7dacb-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="7dacb-238">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-238">Select **save**.</span></span>
    
    ![eNom-BP-configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7dacb-240">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dacb-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7dacb-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7dacb-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7dacb-242">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="7dacb-242">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="7dacb-p112">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="7dacb-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="7dacb-246">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7dacb-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="7dacb-248">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="7dacb-250">À direita da **nova linha**, selecione **adicionar registro SRV ou SPF**.</span><span class="sxs-lookup"><span data-stu-id="7dacb-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="7dacb-252">Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="7dacb-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7dacb-253">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="7dacb-253">**Service**</span></span>|<span data-ttu-id="7dacb-254">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="7dacb-254">**Protocol**</span></span>|<span data-ttu-id="7dacb-255">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="7dacb-255">**Priority**</span></span>|<span data-ttu-id="7dacb-256">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="7dacb-256">**Weight**</span></span>|<span data-ttu-id="7dacb-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="7dacb-257">**Port**</span></span>|<span data-ttu-id="7dacb-258">**Destino          (Nome do host)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7dacb-259">_sip</span><span class="sxs-lookup"><span data-stu-id="7dacb-259">_sip</span></span>  <br/> |<span data-ttu-id="7dacb-260">_tls</span><span class="sxs-lookup"><span data-stu-id="7dacb-260">_tls</span></span>  <br/> |<span data-ttu-id="7dacb-261">100</span><span class="sxs-lookup"><span data-stu-id="7dacb-261">100</span></span>  <br/> |<span data-ttu-id="7dacb-262">1</span><span class="sxs-lookup"><span data-stu-id="7dacb-262">1</span></span>  <br/> |<span data-ttu-id="7dacb-263">443</span><span class="sxs-lookup"><span data-stu-id="7dacb-263">443</span></span>  <br/> |<span data-ttu-id="7dacb-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7dacb-265">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dacb-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7dacb-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7dacb-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="7dacb-267">_tcp</span></span>  <br/> |<span data-ttu-id="7dacb-268">100</span><span class="sxs-lookup"><span data-stu-id="7dacb-268">100</span></span>  <br/> |<span data-ttu-id="7dacb-269">1</span><span class="sxs-lookup"><span data-stu-id="7dacb-269">1</span></span>  <br/> |<span data-ttu-id="7dacb-270">5061</span><span class="sxs-lookup"><span data-stu-id="7dacb-270">5061</span></span>  <br/> |<span data-ttu-id="7dacb-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dacb-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="7dacb-272">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="7dacb-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="7dacb-274">Selecione **salvar**</span><span class="sxs-lookup"><span data-stu-id="7dacb-274">Select **save**</span></span>
    
    ![eNom-BP-configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="7dacb-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7dacb-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

