---
title: Criar registros DNS ao focalizar para a Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em foco para a Microsoft.
ms.openlocfilehash: e51cb77831f4e29ac3a51602a1bb19f8b0c9e0e3
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780344"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="78251-103">Criar registros DNS ao focalizar para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78251-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="78251-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="78251-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="78251-105">Se você usa a Hover como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="78251-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="78251-106">Depois que você adicionar esses registros ao focalizar, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78251-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="78251-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="78251-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="78251-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="78251-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="78251-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78251-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="78251-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="78251-110">Add a TXT record for verification</span></span>
<span data-ttu-id="78251-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="78251-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="78251-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="78251-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="78251-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="78251-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78251-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="78251-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="78251-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="78251-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="78251-116">Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="78251-116">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="78251-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="78251-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="78251-118">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="78251-118">You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="78251-120">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78251-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="78251-122">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="78251-122">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="78251-124">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="78251-124">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="78251-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="78251-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="78251-127">Nome do host</span><span class="sxs-lookup"><span data-stu-id="78251-127">Hostname</span></span>  <br/> |<span data-ttu-id="78251-128">Tipo de Registro</span><span class="sxs-lookup"><span data-stu-id="78251-128">Record Type</span></span>  <br/> |<span data-ttu-id="78251-129">Valor</span><span class="sxs-lookup"><span data-stu-id="78251-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="78251-130">TXT</span><span class="sxs-lookup"><span data-stu-id="78251-130">TXT</span></span>  <br/> |<span data-ttu-id="78251-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="78251-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="78251-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="78251-132">**Note:** This is an example.</span></span> <span data-ttu-id="78251-133">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="78251-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="78251-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="78251-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="78251-136">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78251-136">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="78251-138">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="78251-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="78251-139">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="78251-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="78251-140">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="78251-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="78251-141">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="78251-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="78251-142">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="78251-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="78251-143">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="78251-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="78251-144">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="78251-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="78251-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="78251-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="78251-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="78251-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="78251-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78251-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="78251-148">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78251-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="78251-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="78251-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="78251-150">Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="78251-150">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="78251-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="78251-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="78251-152">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="78251-152">You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="78251-154">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78251-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="78251-156">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="78251-156">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="78251-158">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="78251-158">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="78251-160">Nas caixas do novo registro, selecione **MX** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="78251-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="78251-161">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="78251-161">**Hostname**</span></span>|<span data-ttu-id="78251-162">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="78251-162">**Record Type**</span></span>|<span data-ttu-id="78251-163">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="78251-163">**Priority**</span></span>|<span data-ttu-id="78251-164">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="78251-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="78251-165">MX</span><span class="sxs-lookup"><span data-stu-id="78251-165">MX</span></span>  <br/> |<span data-ttu-id="78251-166">,0</span><span class="sxs-lookup"><span data-stu-id="78251-166">0</span></span>  <br/> <span data-ttu-id="78251-167">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="78251-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="78251-168">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="78251-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="78251-169">**Observação:** Acesse sua *\<domain-key\>* conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78251-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="78251-170">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="78251-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="78251-172">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78251-172">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="78251-174">Se houver outros registros MX, use o processo de duas etapas a seguir para remover cada um deles:</span><span class="sxs-lookup"><span data-stu-id="78251-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="78251-175">Primeiro, passe sobre um registro que você deseja remover, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="78251-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Passe o mouse e selecione Excluir](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="78251-177">Em segundo lugar, selecione **Sim** para confirmar cada exclusão.</span><span class="sxs-lookup"><span data-stu-id="78251-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selecione Sim para confirmar a exclusão](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="78251-179">Repita esse processo até excluir todos os registros MX, exceto para aquele adicionado anteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="78251-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="78251-180">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78251-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="78251-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="78251-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="78251-182">Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="78251-182">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="78251-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="78251-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="78251-184">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="78251-184">You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="78251-186">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78251-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="78251-188">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="78251-188">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="78251-190">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="78251-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="78251-191">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="78251-191">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="78251-193">Nas caixas vazias do novo registro, selecione **CNAME** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="78251-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="78251-194">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="78251-194">**Hostname**</span></span>|<span data-ttu-id="78251-195">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="78251-195">**Record Type**</span></span>|<span data-ttu-id="78251-196">**Host de Destino**</span><span class="sxs-lookup"><span data-stu-id="78251-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="78251-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="78251-197">autodiscover</span></span>  <br/> |<span data-ttu-id="78251-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="78251-198">CNAME</span></span>  <br/> |<span data-ttu-id="78251-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="78251-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="78251-200">sip</span><span class="sxs-lookup"><span data-stu-id="78251-200">sip</span></span>  <br/> |<span data-ttu-id="78251-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="78251-201">CNAME</span></span>  <br/> |<span data-ttu-id="78251-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78251-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="78251-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="78251-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="78251-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="78251-204">CNAME</span></span>  <br/> |<span data-ttu-id="78251-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78251-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="78251-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="78251-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="78251-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="78251-207">CNAME</span></span>  <br/> |<span data-ttu-id="78251-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="78251-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="78251-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="78251-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="78251-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="78251-210">CNAME</span></span>  <br/> |<span data-ttu-id="78251-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="78251-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Digite ou copie e cole valores DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="78251-213">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78251-213">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="78251-215">Usando as três etapas anteriores e os valores das outras cinco linhas da tabela, adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="78251-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="78251-216">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="78251-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="78251-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="78251-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="78251-218">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="78251-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="78251-219">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="78251-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="78251-220">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78251-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="78251-221">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="78251-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="78251-222">Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="78251-222">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="78251-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="78251-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="78251-224">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="78251-224">You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="78251-226">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78251-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="78251-228">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="78251-228">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="78251-230">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="78251-230">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="78251-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="78251-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="78251-233">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="78251-233">**Hostname**</span></span>|<span data-ttu-id="78251-234">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="78251-234">**Record Type**</span></span>|<span data-ttu-id="78251-235">**Valor**</span><span class="sxs-lookup"><span data-stu-id="78251-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="78251-236">TXT</span><span class="sxs-lookup"><span data-stu-id="78251-236">TXT</span></span>  <br/> |<span data-ttu-id="78251-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="78251-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="78251-238">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="78251-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Digite ou copie e cole valores DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="78251-240">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78251-240">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="78251-242">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78251-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="78251-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="78251-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="78251-244">Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="78251-244">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="78251-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="78251-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="78251-246">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="78251-246">You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="78251-248">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="78251-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="78251-250">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="78251-250">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="78251-252">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="78251-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="78251-253">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="78251-253">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="78251-255">Nas caixas vazias do novo registro, selecione **SRV** como o **Tipo de Registro** e digite ou copie e cole os valores da primeira linha na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="78251-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="78251-256">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="78251-256">**Hostname**</span></span>|<span data-ttu-id="78251-257">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="78251-257">**Record Type**</span></span>|<span data-ttu-id="78251-258">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="78251-258">**Priority**</span></span>|<span data-ttu-id="78251-259">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="78251-259">**Weight**</span></span>|<span data-ttu-id="78251-260">**Porta**</span><span class="sxs-lookup"><span data-stu-id="78251-260">**Port**</span></span>|<span data-ttu-id="78251-261">**Destino**</span><span class="sxs-lookup"><span data-stu-id="78251-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="78251-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="78251-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="78251-263">SRV</span><span class="sxs-lookup"><span data-stu-id="78251-263">SRV</span></span>  <br/> |<span data-ttu-id="78251-264">100</span><span class="sxs-lookup"><span data-stu-id="78251-264">100</span></span>  <br/> |<span data-ttu-id="78251-265">1 </span><span class="sxs-lookup"><span data-stu-id="78251-265">1</span></span>  <br/> |<span data-ttu-id="78251-266">443</span><span class="sxs-lookup"><span data-stu-id="78251-266">443</span></span>  <br/> |<span data-ttu-id="78251-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78251-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="78251-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="78251-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="78251-269">SRV</span><span class="sxs-lookup"><span data-stu-id="78251-269">SRV</span></span>  <br/> |<span data-ttu-id="78251-270">100</span><span class="sxs-lookup"><span data-stu-id="78251-270">100</span></span>  <br/> |<span data-ttu-id="78251-271">1 </span><span class="sxs-lookup"><span data-stu-id="78251-271">1</span></span>  <br/> |<span data-ttu-id="78251-272">5061</span><span class="sxs-lookup"><span data-stu-id="78251-272">5061</span></span>  <br/> |<span data-ttu-id="78251-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="78251-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Digite ou copie e cole valores DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="78251-275">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78251-275">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="78251-277">Usando as três etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="78251-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78251-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="78251-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="78251-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="78251-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="78251-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="78251-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
