---
title: Criar registros DNS no Meu Domínio para Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Aprenda a verificar seu domínio e a configurar registros DNS para emails, Skype for Business Online e outros serviços em Meu Domínio para Microsoft.
ms.openlocfilehash: 1c6edc1e3ad03b0467c70741d4097cf3a3b5e196
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400407"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="d68a6-103">Criar registros DNS no Meu Domínio para Microsoft</span><span class="sxs-lookup"><span data-stu-id="d68a6-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="d68a6-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d68a6-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="d68a6-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="d68a6-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="d68a6-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="d68a6-107">Se você quiser gerenciar seus próprios registros DNS da Microsoft na MyDomain apesar das limitações do serviço, siga as etapas deste artigo para configurar os registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d68a6-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="d68a6-108">Depois que você adicionar esses registros no Meu Domínio, seu domínio será configurado para funcionar com os serviços Microsoft. </span><span class="sxs-lookup"><span data-stu-id="d68a6-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="d68a6-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d68a6-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d68a6-110">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d68a6-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d68a6-111">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d68a6-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d68a6-112">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d68a6-112">Add a TXT record for verification</span></span>
<span data-ttu-id="d68a6-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d68a6-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d68a6-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="d68a6-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d68a6-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="d68a6-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d68a6-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="d68a6-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="d68a6-117">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="d68a6-117">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d68a6-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="d68a6-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="d68a6-119">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="d68a6-119">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d68a6-120">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d68a6-121">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="d68a6-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d68a6-122">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d68a6-123">Na lista suspensa **Modificar**, clique em **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="d68a6-124">Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d68a6-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="d68a6-125">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="d68a6-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="d68a6-126">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d68a6-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d68a6-127">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d68a6-127">**Note:** This is an example.</span></span> <span data-ttu-id="d68a6-128">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="d68a6-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d68a6-129">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d68a6-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="d68a6-130">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="d68a6-131">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="d68a6-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d68a6-132">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="d68a6-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d68a6-133">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="d68a6-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d68a6-134">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="d68a6-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d68a6-135">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="d68a6-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d68a6-136">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d68a6-137">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d68a6-138">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d68a6-138">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d68a6-139">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d68a6-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d68a6-140">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d68a6-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d68a6-141">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d68a6-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d68a6-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d68a6-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d68a6-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="d68a6-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="d68a6-144">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="d68a6-144">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d68a6-145">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d68a6-146">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="d68a6-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d68a6-147">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d68a6-148">Na lista suspensa **Modificar**, escolha **Registro MX**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="d68a6-150">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="d68a6-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d68a6-151">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d68a6-151">**Priority**</span></span>|<span data-ttu-id="d68a6-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="d68a6-152">**Host**</span></span>|<span data-ttu-id="d68a6-153">**Aponta para:**</span><span class="sxs-lookup"><span data-stu-id="d68a6-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d68a6-154">0</span><span class="sxs-lookup"><span data-stu-id="d68a6-154">0</span></span>  <br/> <span data-ttu-id="d68a6-155">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="d68a6-155">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |@  <br/> | <span data-ttu-id="d68a6-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d68a6-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d68a6-157">**Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d68a6-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="d68a6-158"> > [Como localizo isso?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="d68a6-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="d68a6-160">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="d68a6-162">Se houver outros registros MX, selecione **Remover** na coluna **Ação** em cada um para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="d68a6-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="d68a6-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d68a6-166">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d68a6-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d68a6-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d68a6-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d68a6-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="d68a6-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="d68a6-169">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="d68a6-169">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d68a6-170">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d68a6-171">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="d68a6-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d68a6-172">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d68a6-173">Na lista suspensa **Modificar**, escolha **Alias CNAME**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="d68a6-175">Adicionar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="d68a6-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d68a6-176">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d68a6-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="d68a6-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="d68a6-177">**Host**</span></span>|<span data-ttu-id="d68a6-178">**Aponta para:**</span><span class="sxs-lookup"><span data-stu-id="d68a6-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d68a6-179">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="d68a6-179">autodiscover</span></span>  <br/> |<span data-ttu-id="d68a6-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d68a6-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d68a6-181">sip</span><span class="sxs-lookup"><span data-stu-id="d68a6-181">sip</span></span>  <br/> |<span data-ttu-id="d68a6-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d68a6-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d68a6-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d68a6-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d68a6-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d68a6-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d68a6-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d68a6-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d68a6-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d68a6-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d68a6-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d68a6-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d68a6-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d68a6-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="d68a6-190">Clique em **Adicionar** para adicionar o primeiro registro.</span><span class="sxs-lookup"><span data-stu-id="d68a6-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="d68a6-192">Adicione o segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="d68a6-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="d68a6-193">Use os valores da segunda linha da tabela acima e clique em **Adicionar** para adicionar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="d68a6-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="d68a6-194">Adicione os registros restantes da mesma maneira, usando os valores da terceira, quarta, quinta e sexta linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="d68a6-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d68a6-195">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="d68a6-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d68a6-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d68a6-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d68a6-197">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="d68a6-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d68a6-198">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="d68a6-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d68a6-199">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d68a6-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d68a6-200">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d68a6-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="d68a6-201">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="d68a6-201">Need examples?</span></span> <span data-ttu-id="d68a6-202">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="d68a6-202">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="d68a6-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d68a6-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d68a6-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="d68a6-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="d68a6-205">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="d68a6-205">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d68a6-206">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d68a6-207">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="d68a6-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d68a6-208">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d68a6-209">Na lista suspensa **Modificar**, escolha **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="d68a6-211">Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d68a6-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="d68a6-212">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="d68a6-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="d68a6-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d68a6-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d68a6-214">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d68a6-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="d68a6-216">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d68a6-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d68a6-218">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d68a6-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d68a6-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d68a6-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="d68a6-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="d68a6-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="d68a6-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="d68a6-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d68a6-222">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d68a6-222">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d68a6-223">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="d68a6-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d68a6-224">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d68a6-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
