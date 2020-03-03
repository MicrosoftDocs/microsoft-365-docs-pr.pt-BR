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
ms.openlocfilehash: 72df2d98f3446087a1e9796cd616293a91003ad9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350102"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="0524f-103">Criar registros DNS no site Hover para o Office 365</span><span class="sxs-lookup"><span data-stu-id="0524f-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="0524f-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="0524f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0524f-105">Se você usa a Hover como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="0524f-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="0524f-106">Depois que você adicionar esses registros à Hover, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0524f-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="0524f-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="0524f-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0524f-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0524f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0524f-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="0524f-111">Add a TXT record for verification</span></span>
<span data-ttu-id="0524f-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0524f-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0524f-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="0524f-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0524f-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="0524f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="0524f-117">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0524f-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0524f-p104">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="0524f-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="0524f-121">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="0524f-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="0524f-123">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="0524f-123">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="0524f-125">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="0524f-125">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="0524f-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0524f-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="0524f-128">Nome do host</span><span class="sxs-lookup"><span data-stu-id="0524f-128">Hostname</span></span>  <br/> |<span data-ttu-id="0524f-129">Tipo de Registro</span><span class="sxs-lookup"><span data-stu-id="0524f-129">Record Type</span></span>  <br/> |<span data-ttu-id="0524f-130">Valor</span><span class="sxs-lookup"><span data-stu-id="0524f-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="0524f-131">TXT</span><span class="sxs-lookup"><span data-stu-id="0524f-131">TXT</span></span>  <br/> |<span data-ttu-id="0524f-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0524f-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0524f-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0524f-133">**Note:** This is an example.</span></span> <span data-ttu-id="0524f-134">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="0524f-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="0524f-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="0524f-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="0524f-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0524f-137">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="0524f-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="0524f-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0524f-140">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="0524f-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="0524f-141">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="0524f-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0524f-142">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="0524f-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0524f-143">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="0524f-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0524f-144">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="0524f-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0524f-145">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="0524f-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0524f-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0524f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="0524f-149">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="0524f-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="0524f-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0524f-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0524f-151">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0524f-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0524f-p107">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="0524f-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="0524f-155">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="0524f-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="0524f-157">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="0524f-157">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="0524f-159">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="0524f-159">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="0524f-161">Nas caixas do novo registro, selecione **MX** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0524f-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0524f-162">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="0524f-162">**Hostname**</span></span>|<span data-ttu-id="0524f-163">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="0524f-163">**Record Type**</span></span>|<span data-ttu-id="0524f-164">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="0524f-164">**Priority**</span></span>|<span data-ttu-id="0524f-165">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="0524f-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0524f-166">MX</span><span class="sxs-lookup"><span data-stu-id="0524f-166">MX</span></span>  <br/> |<span data-ttu-id="0524f-167">,0</span><span class="sxs-lookup"><span data-stu-id="0524f-167">0</span></span>  <br/> <span data-ttu-id="0524f-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="0524f-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="0524f-169">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0524f-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0524f-170">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0524f-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="0524f-171">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="0524f-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="0524f-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0524f-173">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="0524f-175">Se houver outros registros MX, use o processo de duas etapas a seguir para remover cada um deles:</span><span class="sxs-lookup"><span data-stu-id="0524f-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="0524f-176">Primeiro, passe sobre um registro que você deseja remover, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="0524f-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Passe o mouse e selecione Excluir](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="0524f-178">Em segundo lugar, selecione **Sim** para confirmar cada exclusão.</span><span class="sxs-lookup"><span data-stu-id="0524f-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selecione Sim para confirmar a exclusão](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="0524f-180">Repita esse processo até excluir todos os registros MX, exceto para aquele adicionado anteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="0524f-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="0524f-181">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="0524f-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="0524f-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0524f-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0524f-183">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0524f-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0524f-p109">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="0524f-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="0524f-187">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="0524f-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="0524f-189">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="0524f-189">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="0524f-191">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="0524f-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="0524f-192">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="0524f-192">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="0524f-194">Nas caixas vazias do novo registro, selecione **CNAME** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0524f-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="0524f-195">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="0524f-195">**Hostname**</span></span>|<span data-ttu-id="0524f-196">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="0524f-196">**Record Type**</span></span>|<span data-ttu-id="0524f-197">**Host de Destino**</span><span class="sxs-lookup"><span data-stu-id="0524f-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0524f-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0524f-198">autodiscover</span></span>  <br/> |<span data-ttu-id="0524f-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="0524f-199">CNAME</span></span>  <br/> |<span data-ttu-id="0524f-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0524f-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="0524f-201">sip</span><span class="sxs-lookup"><span data-stu-id="0524f-201">sip</span></span>  <br/> |<span data-ttu-id="0524f-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="0524f-202">CNAME</span></span>  <br/> |<span data-ttu-id="0524f-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0524f-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0524f-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0524f-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0524f-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="0524f-205">CNAME</span></span>  <br/> |<span data-ttu-id="0524f-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0524f-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0524f-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0524f-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0524f-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="0524f-208">CNAME</span></span>  <br/> |<span data-ttu-id="0524f-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0524f-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="0524f-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0524f-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0524f-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="0524f-211">CNAME</span></span>  <br/> |<span data-ttu-id="0524f-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0524f-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Digite ou copie e cole valores DNS](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="0524f-214">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0524f-214">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="0524f-216">Usando as três etapas anteriores e os valores das outras cinco linhas da tabela, adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="0524f-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0524f-217">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="0524f-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0524f-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0524f-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0524f-219">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="0524f-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0524f-220">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="0524f-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0524f-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="0524f-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="0524f-222">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="0524f-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="0524f-223">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0524f-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0524f-p111">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="0524f-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="0524f-227">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="0524f-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="0524f-229">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="0524f-229">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="0524f-231">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="0524f-231">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="0524f-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0524f-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0524f-234">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="0524f-234">**Hostname**</span></span>|<span data-ttu-id="0524f-235">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="0524f-235">**Record Type**</span></span>|<span data-ttu-id="0524f-236">**Valor**</span><span class="sxs-lookup"><span data-stu-id="0524f-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0524f-237">TXT</span><span class="sxs-lookup"><span data-stu-id="0524f-237">TXT</span></span>  <br/> |<span data-ttu-id="0524f-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0524f-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0524f-239">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="0524f-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Digite ou copie e cole valores DNS](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="0524f-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0524f-241">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="0524f-243">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="0524f-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="0524f-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0524f-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="0524f-245">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0524f-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0524f-p112">Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="0524f-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Entrar](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="0524f-249">Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="0524f-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Selecionar um domínio](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="0524f-251">Selecione a guia **DNS** .</span><span class="sxs-lookup"><span data-stu-id="0524f-251">Select the **DNS** tab.</span></span> 
    
    ![Selecione a guia DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="0524f-253">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="0524f-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="0524f-254">Selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="0524f-254">Select **Add New**.</span></span>
    
    ![Selecione Adicionar novo](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="0524f-256">Nas caixas vazias do novo registro, selecione **SRV** como o **Tipo de Registro** e digite ou copie e cole os valores da primeira linha na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0524f-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="0524f-257">**Nome do host**</span><span class="sxs-lookup"><span data-stu-id="0524f-257">**Hostname**</span></span>|<span data-ttu-id="0524f-258">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="0524f-258">**Record Type**</span></span>|<span data-ttu-id="0524f-259">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="0524f-259">**Priority**</span></span>|<span data-ttu-id="0524f-260">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="0524f-260">**Weight**</span></span>|<span data-ttu-id="0524f-261">**Porta**</span><span class="sxs-lookup"><span data-stu-id="0524f-261">**Port**</span></span>|<span data-ttu-id="0524f-262">**Destino**</span><span class="sxs-lookup"><span data-stu-id="0524f-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0524f-263">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="0524f-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="0524f-264">SRV</span><span class="sxs-lookup"><span data-stu-id="0524f-264">SRV</span></span>  <br/> |<span data-ttu-id="0524f-265">100</span><span class="sxs-lookup"><span data-stu-id="0524f-265">100</span></span>  <br/> |<span data-ttu-id="0524f-266">1</span><span class="sxs-lookup"><span data-stu-id="0524f-266">1</span></span>  <br/> |<span data-ttu-id="0524f-267">443</span><span class="sxs-lookup"><span data-stu-id="0524f-267">443</span></span>  <br/> |<span data-ttu-id="0524f-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0524f-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0524f-269">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="0524f-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="0524f-270">SRV</span><span class="sxs-lookup"><span data-stu-id="0524f-270">SRV</span></span>  <br/> |<span data-ttu-id="0524f-271">100</span><span class="sxs-lookup"><span data-stu-id="0524f-271">100</span></span>  <br/> |<span data-ttu-id="0524f-272">1</span><span class="sxs-lookup"><span data-stu-id="0524f-272">1</span></span>  <br/> |<span data-ttu-id="0524f-273">5061</span><span class="sxs-lookup"><span data-stu-id="0524f-273">5061</span></span>  <br/> |<span data-ttu-id="0524f-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0524f-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Digite ou copie e cole valores DNS](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="0524f-276">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0524f-276">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="0524f-278">Usando as três etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="0524f-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0524f-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0524f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
