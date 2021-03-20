---
title: Criar registros DNS no eNomCentral para a Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no eNomCentral para Microsoft.
ms.openlocfilehash: 528659667ee062c8cf767bed0989558020032924
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910361"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="78aa3-103">Criar registros DNS no eNomCentral para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78aa3-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="78aa3-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="78aa3-105">Se você usa a eNomCentral como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="78aa3-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="78aa3-106">Depois de adicionar esses registros no eNomCentral, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78aa3-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="78aa3-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78aa3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="78aa3-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="78aa3-110">Add a TXT record for verification</span></span>
<span data-ttu-id="78aa3-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="78aa3-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="78aa3-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="78aa3-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="78aa3-116">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="78aa3-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="78aa3-p104">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="78aa3-120">Em **meus domínios,** selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78aa3-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="78aa3-122">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="78aa3-124">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="78aa3-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="78aa3-125">Escolha o **valor Tipo** de Registro na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="78aa3-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="78aa3-126">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="78aa3-126">Host Name</span></span>|<span data-ttu-id="78aa3-127">Record Type</span><span class="sxs-lookup"><span data-stu-id="78aa3-127">Record Type</span></span>|<span data-ttu-id="78aa3-128">Endereço</span><span class="sxs-lookup"><span data-stu-id="78aa3-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="78aa3-129">TXT</span><span class="sxs-lookup"><span data-stu-id="78aa3-129">TXT</span></span>|<span data-ttu-id="78aa3-130">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="78aa3-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="78aa3-131">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="78aa3-131">**Note:** This is an example.</span></span> <span data-ttu-id="78aa3-132">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="78aa3-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="78aa3-133">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="78aa3-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="78aa3-135">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-135">Select **save**.</span></span>

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="78aa3-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="78aa3-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="78aa3-138">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="78aa3-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="78aa3-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="78aa3-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="78aa3-140">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="78aa3-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="78aa3-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="78aa3-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="78aa3-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="78aa3-143">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="78aa3-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78aa3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="78aa3-147">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78aa3-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="78aa3-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="78aa3-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="78aa3-149">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="78aa3-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="78aa3-p107">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="78aa3-153">Em **meus domínios,** selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78aa3-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="78aa3-155">Na lista suspensa **Gerenciar Domínio**, escolha **Configurações de Email**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="78aa3-157">Na lista suspensa **Seleção de Serviço**, escolha **Usuário (MX)**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="78aa3-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="78aa3-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="78aa3-160">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="78aa3-160">Host Name</span></span>|<span data-ttu-id="78aa3-161">Endereço</span><span class="sxs-lookup"><span data-stu-id="78aa3-161">Address</span></span>|<span data-ttu-id="78aa3-162">Pref</span><span class="sxs-lookup"><span data-stu-id="78aa3-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="78aa3-163">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="78aa3-164">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="78aa3-165">**Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78aa3-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="78aa3-166">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="78aa3-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="78aa3-167">10 </span><span class="sxs-lookup"><span data-stu-id="78aa3-167">10</span></span>  <br/> <span data-ttu-id="78aa3-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="78aa3-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span>|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="78aa3-170">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-170">Select **save**.</span></span>

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="78aa3-172">Se houver outros registros MX existentes, marque as caixas de seleção desses registros para escolhê-los.</span><span class="sxs-lookup"><span data-stu-id="78aa3-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="78aa3-174">Selecione **excluir verificado**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-174">Select **delete checked**.</span></span>

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="78aa3-176">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78aa3-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="78aa3-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="78aa3-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="78aa3-178">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="78aa3-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="78aa3-p109">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="78aa3-182">Em **meus domínios,** selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78aa3-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="78aa3-184">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="78aa3-186">Selecione **nova linha**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-186">Select **new row**.</span></span>

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="78aa3-188">Nas caixas dos seis novos registros, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="78aa3-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="78aa3-189">Escolha o **valor Tipo** de Registro na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="78aa3-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="78aa3-190">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="78aa3-190">Host Name</span></span>|<span data-ttu-id="78aa3-191">Record Type</span><span class="sxs-lookup"><span data-stu-id="78aa3-191">Record Type</span></span>|<span data-ttu-id="78aa3-192">Endereço</span><span class="sxs-lookup"><span data-stu-id="78aa3-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="78aa3-193">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="78aa3-193">autodiscover</span></span>|<span data-ttu-id="78aa3-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="78aa3-194">CNAME (Alias)</span></span>|<span data-ttu-id="78aa3-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="78aa3-196">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="78aa3-197">sip</span><span class="sxs-lookup"><span data-stu-id="78aa3-197">sip</span></span>|<span data-ttu-id="78aa3-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="78aa3-198">CNAME (Alias)</span></span>|<span data-ttu-id="78aa3-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="78aa3-200">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="78aa3-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="78aa3-201">lyncdiscover</span></span>|<span data-ttu-id="78aa3-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="78aa3-202">CNAME (Alias)</span></span>|<span data-ttu-id="78aa3-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="78aa3-204">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="78aa3-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="78aa3-205">enterpriseregistration</span></span>|<span data-ttu-id="78aa3-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="78aa3-206">CNAME (Alias)</span></span>|<span data-ttu-id="78aa3-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="78aa3-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="78aa3-208">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="78aa3-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="78aa3-209">enterpriseenrollment</span></span>|<span data-ttu-id="78aa3-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="78aa3-210">CNAME (Alias)</span></span>|<span data-ttu-id="78aa3-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="78aa3-212">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="78aa3-214">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-214">Select **save**.</span></span>

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="78aa3-216">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="78aa3-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="78aa3-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="78aa3-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="78aa3-218">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="78aa3-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="78aa3-219">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="78aa3-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="78aa3-220">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78aa3-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="78aa3-221">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="78aa3-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="78aa3-222">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="78aa3-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="78aa3-p111">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="78aa3-226">Em **meus domínios,** selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78aa3-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="78aa3-228">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="78aa3-230">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="78aa3-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="78aa3-231">Escolha o **valor Tipo** de Registro na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="78aa3-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="78aa3-232">Nome de Host</span><span class="sxs-lookup"><span data-stu-id="78aa3-232">Host Name</span></span>|<span data-ttu-id="78aa3-233">Record Type</span><span class="sxs-lookup"><span data-stu-id="78aa3-233">Record Type</span></span>|<span data-ttu-id="78aa3-234">Endereço</span><span class="sxs-lookup"><span data-stu-id="78aa3-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="78aa3-235">TXT</span><span class="sxs-lookup"><span data-stu-id="78aa3-235">TXT</span></span>|<span data-ttu-id="78aa3-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="78aa3-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="78aa3-237">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="78aa3-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="78aa3-239">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-239">Select **save**.</span></span>

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="78aa3-241">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78aa3-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="78aa3-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="78aa3-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="78aa3-243">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="78aa3-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="78aa3-p112">Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="78aa3-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="78aa3-247">Em **meus domínios,** selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78aa3-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="78aa3-249">Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="78aa3-251">À direita da nova **linha,** selecione **adicionar registro SRV ou SPF**.</span><span class="sxs-lookup"><span data-stu-id="78aa3-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="78aa3-253">Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="78aa3-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="78aa3-254">Serviço</span><span class="sxs-lookup"><span data-stu-id="78aa3-254">Service</span></span>|<span data-ttu-id="78aa3-255">Protocolo</span><span class="sxs-lookup"><span data-stu-id="78aa3-255">Protocol</span></span>|<span data-ttu-id="78aa3-256">Priority</span><span class="sxs-lookup"><span data-stu-id="78aa3-256">Priority</span></span>|<span data-ttu-id="78aa3-257">Peso</span><span class="sxs-lookup"><span data-stu-id="78aa3-257">Weight</span></span>|<span data-ttu-id="78aa3-258">Porta</span><span class="sxs-lookup"><span data-stu-id="78aa3-258">Port</span></span>|<span data-ttu-id="78aa3-259">Destino (Nomedo Host)</span><span class="sxs-lookup"><span data-stu-id="78aa3-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="78aa3-260">_sip</span><span class="sxs-lookup"><span data-stu-id="78aa3-260">_sip</span></span>|<span data-ttu-id="78aa3-261">_tls</span><span class="sxs-lookup"><span data-stu-id="78aa3-261">_tls</span></span>|<span data-ttu-id="78aa3-262">100</span><span class="sxs-lookup"><span data-stu-id="78aa3-262">100</span></span>|<span data-ttu-id="78aa3-263">1</span><span class="sxs-lookup"><span data-stu-id="78aa3-263">1</span></span>|<span data-ttu-id="78aa3-264">443</span><span class="sxs-lookup"><span data-stu-id="78aa3-264">443</span></span>|<span data-ttu-id="78aa3-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="78aa3-266">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="78aa3-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="78aa3-267">_sipfederationtls</span></span>|<span data-ttu-id="78aa3-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="78aa3-268">_tcp</span></span>|<span data-ttu-id="78aa3-269">100</span><span class="sxs-lookup"><span data-stu-id="78aa3-269">100</span></span>|<span data-ttu-id="78aa3-270">1</span><span class="sxs-lookup"><span data-stu-id="78aa3-270">1</span></span>|<span data-ttu-id="78aa3-271">5061</span><span class="sxs-lookup"><span data-stu-id="78aa3-271">5061</span></span>|<span data-ttu-id="78aa3-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="78aa3-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="78aa3-273">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="78aa3-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="78aa3-275">Selecionar **salvar**</span><span class="sxs-lookup"><span data-stu-id="78aa3-275">Select **save**</span></span>

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="78aa3-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78aa3-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>