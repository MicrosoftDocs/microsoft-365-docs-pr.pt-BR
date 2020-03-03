---
title: Criar registros DNS no site eNomCentral para o Office 365
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em eNomCentral para o Office 365.
ms.openlocfilehash: dec76e0dde2775851ff464e3b8765f82dfb57625
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350462"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="5bb84-103">Criar registros DNS no site eNomCentral para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5bb84-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="5bb84-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5bb84-105">Se você usa a eNomCentral como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="5bb84-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5bb84-106">Depois que você adicionar esses registros à eNomCentral, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5bb84-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5bb84-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5bb84-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5bb84-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5bb84-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5bb84-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="5bb84-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5bb84-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5bb84-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5bb84-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5bb84-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="5bb84-117">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5bb84-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5bb84-p104">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="5bb84-121">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5bb84-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="5bb84-123">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="5bb84-125">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="5bb84-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5bb84-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5bb84-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5bb84-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5bb84-127">**Host Name**</span></span> <br/> |<span data-ttu-id="5bb84-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="5bb84-128">**Record Type**</span></span> <br/> |<span data-ttu-id="5bb84-129">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="5bb84-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="5bb84-130">TXT</span><span class="sxs-lookup"><span data-stu-id="5bb84-130">TXT</span></span>  <br/> |<span data-ttu-id="5bb84-131">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5bb84-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5bb84-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="5bb84-132">**Note:** This is an example.</span></span> <span data-ttu-id="5bb84-133">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5bb84-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="5bb84-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="5bb84-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="5bb84-136">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-136">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="5bb84-138">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="5bb84-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5bb84-139">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="5bb84-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5bb84-140">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="5bb84-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5bb84-141">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="5bb84-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5bb84-142">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="5bb84-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5bb84-143">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5bb84-144">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5bb84-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5bb84-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5bb84-148">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5bb84-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5bb84-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5bb84-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="5bb84-150">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5bb84-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5bb84-p107">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="5bb84-154">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5bb84-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="5bb84-156">Na lista suspensa **Gerenciar Domínio**, escolha **Configurações de Email**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="5bb84-158">Na lista suspensa **Seleção de Serviço**, escolha **Usuário (MX)**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="5bb84-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5bb84-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5bb84-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5bb84-161">**Host Name**</span></span>|<span data-ttu-id="5bb84-162">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="5bb84-162">**Address**</span></span>|<span data-ttu-id="5bb84-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="5bb84-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="5bb84-164">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="5bb84-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5bb84-166">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5bb84-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="5bb84-167">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="5bb84-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5bb84-168">10 </span><span class="sxs-lookup"><span data-stu-id="5bb84-168">10</span></span>  <br/> <span data-ttu-id="5bb84-169">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5bb84-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="5bb84-171">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-171">Select **save**.</span></span>
    
    ![eNom-BP-configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="5bb84-173">Se houver outros registros MX existentes, marque as caixas de seleção desses registros para escolhê-los.</span><span class="sxs-lookup"><span data-stu-id="5bb84-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="5bb84-175">Selecione **excluir verificado**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5bb84-177">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="5bb84-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5bb84-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5bb84-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="5bb84-179">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5bb84-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5bb84-p109">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="5bb84-183">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5bb84-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="5bb84-185">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="5bb84-187">Selecione **nova linha**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-187">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="5bb84-189">Nas caixas dos seis novos registros, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="5bb84-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="5bb84-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5bb84-190">**Host Name**</span></span>|<span data-ttu-id="5bb84-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="5bb84-191">**Record Type**</span></span>|<span data-ttu-id="5bb84-192">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="5bb84-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5bb84-193">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="5bb84-193">autodiscover</span></span>  <br/> |<span data-ttu-id="5bb84-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5bb84-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5bb84-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5bb84-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5bb84-197">sip</span><span class="sxs-lookup"><span data-stu-id="5bb84-197">sip</span></span>  <br/> |<span data-ttu-id="5bb84-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5bb84-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5bb84-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bb84-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5bb84-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5bb84-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5bb84-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5bb84-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5bb84-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bb84-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5bb84-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5bb84-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5bb84-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5bb84-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5bb84-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="5bb84-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5bb84-208">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5bb84-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5bb84-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5bb84-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5bb84-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5bb84-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5bb84-212">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="5bb84-214">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-214">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5bb84-216">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="5bb84-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5bb84-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5bb84-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bb84-218">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="5bb84-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5bb84-219">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="5bb84-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5bb84-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5bb84-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5bb84-221">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="5bb84-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="5bb84-222">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5bb84-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5bb84-p111">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="5bb84-226">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5bb84-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="5bb84-228">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="5bb84-230">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="5bb84-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5bb84-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5bb84-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5bb84-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5bb84-232">**Host Name**</span></span>|<span data-ttu-id="5bb84-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="5bb84-233">**Record Type**</span></span>|<span data-ttu-id="5bb84-234">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="5bb84-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5bb84-235">TXT</span><span class="sxs-lookup"><span data-stu-id="5bb84-235">TXT</span></span>  <br/> |<span data-ttu-id="5bb84-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5bb84-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="5bb84-237">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="5bb84-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="5bb84-239">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-239">Select **save**.</span></span>
    
    ![eNom-BP-configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5bb84-241">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="5bb84-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5bb84-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5bb84-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="5bb84-243">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5bb84-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5bb84-p112">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="5bb84-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="5bb84-247">Em **meus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5bb84-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="5bb84-249">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="5bb84-251">À direita da **nova linha**, selecione **adicionar registro SRV ou SPF**.</span><span class="sxs-lookup"><span data-stu-id="5bb84-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="5bb84-253">Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="5bb84-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5bb84-254">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="5bb84-254">**Service**</span></span>|<span data-ttu-id="5bb84-255">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="5bb84-255">**Protocol**</span></span>|<span data-ttu-id="5bb84-256">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="5bb84-256">**Priority**</span></span>|<span data-ttu-id="5bb84-257">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="5bb84-257">**Weight**</span></span>|<span data-ttu-id="5bb84-258">**Porta**</span><span class="sxs-lookup"><span data-stu-id="5bb84-258">**Port**</span></span>|<span data-ttu-id="5bb84-259">**Destino          (Nome do host)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5bb84-260">_sip</span><span class="sxs-lookup"><span data-stu-id="5bb84-260">_sip</span></span>  <br/> |<span data-ttu-id="5bb84-261">_tls</span><span class="sxs-lookup"><span data-stu-id="5bb84-261">_tls</span></span>  <br/> |<span data-ttu-id="5bb84-262">100</span><span class="sxs-lookup"><span data-stu-id="5bb84-262">100</span></span>  <br/> |<span data-ttu-id="5bb84-263">1</span><span class="sxs-lookup"><span data-stu-id="5bb84-263">1</span></span>  <br/> |<span data-ttu-id="5bb84-264">443</span><span class="sxs-lookup"><span data-stu-id="5bb84-264">443</span></span>  <br/> |<span data-ttu-id="5bb84-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bb84-266">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5bb84-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5bb84-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="5bb84-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="5bb84-268">_tcp</span></span>  <br/> |<span data-ttu-id="5bb84-269">100</span><span class="sxs-lookup"><span data-stu-id="5bb84-269">100</span></span>  <br/> |<span data-ttu-id="5bb84-270">1</span><span class="sxs-lookup"><span data-stu-id="5bb84-270">1</span></span>  <br/> |<span data-ttu-id="5bb84-271">5061</span><span class="sxs-lookup"><span data-stu-id="5bb84-271">5061</span></span>  <br/> |<span data-ttu-id="5bb84-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bb84-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bb84-273">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="5bb84-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="5bb84-275">Selecione **salvar**</span><span class="sxs-lookup"><span data-stu-id="5bb84-275">Select **save**</span></span>
    
    ![eNom-BP-configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="5bb84-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5bb84-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

