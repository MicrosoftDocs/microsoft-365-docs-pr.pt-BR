---
title: Criar registros DNS no site Hover para o Office 365
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em foco para o Office 365.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238942"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="5f6bb-103">Criar registros DNS no site Hover para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5f6bb-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="5f6bb-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5f6bb-105">Se você usa a Hover como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="5f6bb-106">Depois que você adicionar esses registros à Hover, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5f6bb-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5f6bb-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5f6bb-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="5f6bb-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5f6bb-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6bb-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5f6bb-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f6bb-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="5f6bb-117">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5f6bb-p104">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="5f6bb-121">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="5f6bb-123">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="5f6bb-123">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="5f6bb-125">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-125">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="5f6bb-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5f6bb-128">Nome do host</span><span class="sxs-lookup"><span data-stu-id="5f6bb-128">Hostname</span></span>  <br/> |<span data-ttu-id="5f6bb-129">Tipo de Registro</span><span class="sxs-lookup"><span data-stu-id="5f6bb-129">Record Type</span></span>  <br/> |<span data-ttu-id="5f6bb-130">Valor</span><span class="sxs-lookup"><span data-stu-id="5f6bb-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="5f6bb-131">TXT</span><span class="sxs-lookup"><span data-stu-id="5f6bb-131">TXT</span></span>  <br/> |<span data-ttu-id="5f6bb-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5f6bb-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5f6bb-133">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-133">**Note:** This is an example.</span></span> <span data-ttu-id="5f6bb-134">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="5f6bb-135">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="5f6bb-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="5f6bb-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-137">Select **Save**.</span></span>
    
    ![Selecione salvar](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="5f6bb-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5f6bb-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5f6bb-141">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5f6bb-142">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="5f6bb-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5f6bb-143">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5f6bb-144">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5f6bb-145">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5f6bb-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5f6bb-149">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5f6bb-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5f6bb-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6bb-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="5f6bb-151">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5f6bb-p107">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="5f6bb-155">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="5f6bb-157">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="5f6bb-157">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="5f6bb-159">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-159">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="5f6bb-161">Nas caixas do novo registro, selecione **MX** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5f6bb-162">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-162">**Hostname**</span></span>|<span data-ttu-id="5f6bb-163">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-163">**Record Type**</span></span>|<span data-ttu-id="5f6bb-164">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-164">**Priority**</span></span>|<span data-ttu-id="5f6bb-165">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5f6bb-166">MX</span><span class="sxs-lookup"><span data-stu-id="5f6bb-166">MX</span></span>  <br/> |<span data-ttu-id="5f6bb-167">,0</span><span class="sxs-lookup"><span data-stu-id="5f6bb-167">0</span></span>  <br/> <span data-ttu-id="5f6bb-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f6bb-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5f6bb-169">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5f6bb-170">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="5f6bb-171">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="5f6bb-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="5f6bb-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-173">Select **Save**.</span></span>
    
    ![Selecione salvar](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="5f6bb-175">Se houver outros registros MX, use o processo de duas etapas a seguir para remover cada um deles:</span><span class="sxs-lookup"><span data-stu-id="5f6bb-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="5f6bb-176">Primeiro, passe sobre um registro que você deseja remover, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Passe o mouse e selecione Excluir](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="5f6bb-178">Em segundo lugar, selecione **Sim** para confirmar cada exclusão.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selecione Sim para confirmar a exclusão](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="5f6bb-180">Repita esse processo até excluir todos os registros MX, exceto para aquele adicionado anteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5f6bb-181">Adicionar os registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5f6bb-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5f6bb-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6bb-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="5f6bb-183">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5f6bb-p109">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="5f6bb-187">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="5f6bb-189">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="5f6bb-189">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="5f6bb-191">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="5f6bb-192">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-192">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="5f6bb-194">Nas caixas vazias do novo registro, selecione **CNAME** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="5f6bb-195">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-195">**Hostname**</span></span>|<span data-ttu-id="5f6bb-196">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-196">**Record Type**</span></span>|<span data-ttu-id="5f6bb-197">**Host de Destino**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5f6bb-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5f6bb-198">autodiscover</span></span>  <br/> |<span data-ttu-id="5f6bb-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f6bb-199">CNAME</span></span>  <br/> |<span data-ttu-id="5f6bb-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5f6bb-201">sip</span><span class="sxs-lookup"><span data-stu-id="5f6bb-201">sip</span></span>  <br/> |<span data-ttu-id="5f6bb-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f6bb-202">CNAME</span></span>  <br/> |<span data-ttu-id="5f6bb-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f6bb-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5f6bb-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5f6bb-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f6bb-205">CNAME</span></span>  <br/> |<span data-ttu-id="5f6bb-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f6bb-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5f6bb-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5f6bb-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f6bb-208">CNAME</span></span>  <br/> |<span data-ttu-id="5f6bb-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5f6bb-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5f6bb-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5f6bb-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5f6bb-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f6bb-211">CNAME</span></span>  <br/> |<span data-ttu-id="5f6bb-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Digite ou copie e cole valores DNS](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="5f6bb-214">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-214">Select **Save**.</span></span>
    
    ![Selecione salvar](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="5f6bb-216">Usando as três etapas anteriores e os valores das outras cinco linhas da tabela, adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5f6bb-217">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="5f6bb-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5f6bb-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6bb-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f6bb-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5f6bb-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5f6bb-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5f6bb-222">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="5f6bb-223">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5f6bb-p111">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="5f6bb-227">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="5f6bb-229">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="5f6bb-229">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="5f6bb-231">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-231">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="5f6bb-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5f6bb-234">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-234">**Hostname**</span></span>|<span data-ttu-id="5f6bb-235">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-235">**Record Type**</span></span>|<span data-ttu-id="5f6bb-236">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5f6bb-237">TXT</span><span class="sxs-lookup"><span data-stu-id="5f6bb-237">TXT</span></span>  <br/> |<span data-ttu-id="5f6bb-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5f6bb-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="5f6bb-239">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Digite ou copie e cole valores DNS](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="5f6bb-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-241">Select **Save**.</span></span>
    
    ![Selecione salvar](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5f6bb-243">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5f6bb-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5f6bb-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6bb-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="5f6bb-245">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5f6bb-p112">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="5f6bb-249">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="5f6bb-251">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="5f6bb-251">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="5f6bb-253">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5f6bb-254">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-254">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="5f6bb-256">Nas caixas vazias do novo registro, selecione **SRV** como o **Tipo de Registro** e digite ou copie e cole os valores da primeira linha na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="5f6bb-257">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-257">**Hostname**</span></span>|<span data-ttu-id="5f6bb-258">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-258">**Record Type**</span></span>|<span data-ttu-id="5f6bb-259">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-259">**Priority**</span></span>|<span data-ttu-id="5f6bb-260">**Peso**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-260">**Weight**</span></span>|<span data-ttu-id="5f6bb-261">**Porta**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-261">**Port**</span></span>|<span data-ttu-id="5f6bb-262">**Destino**</span><span class="sxs-lookup"><span data-stu-id="5f6bb-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5f6bb-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="5f6bb-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="5f6bb-264">SRV</span><span class="sxs-lookup"><span data-stu-id="5f6bb-264">SRV</span></span>  <br/> |<span data-ttu-id="5f6bb-265">100</span><span class="sxs-lookup"><span data-stu-id="5f6bb-265">100</span></span>  <br/> |<span data-ttu-id="5f6bb-266">1</span><span class="sxs-lookup"><span data-stu-id="5f6bb-266">1</span></span>  <br/> |<span data-ttu-id="5f6bb-267">443</span><span class="sxs-lookup"><span data-stu-id="5f6bb-267">443</span></span>  <br/> |<span data-ttu-id="5f6bb-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5f6bb-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="5f6bb-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5f6bb-270">SRV</span><span class="sxs-lookup"><span data-stu-id="5f6bb-270">SRV</span></span>  <br/> |<span data-ttu-id="5f6bb-271">100</span><span class="sxs-lookup"><span data-stu-id="5f6bb-271">100</span></span>  <br/> |<span data-ttu-id="5f6bb-272">1</span><span class="sxs-lookup"><span data-stu-id="5f6bb-272">1</span></span>  <br/> |<span data-ttu-id="5f6bb-273">5061</span><span class="sxs-lookup"><span data-stu-id="5f6bb-273">5061</span></span>  <br/> |<span data-ttu-id="5f6bb-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5f6bb-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Digite ou copie e cole valores DNS](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="5f6bb-276">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-276">Select **Save**.</span></span>
    
    ![Selecione salvar](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="5f6bb-278">Usando as três etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="5f6bb-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f6bb-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5f6bb-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
