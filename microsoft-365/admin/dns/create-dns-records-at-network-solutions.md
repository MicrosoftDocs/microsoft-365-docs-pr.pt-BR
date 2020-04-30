---
title: Criar registros DNS no Network Solutions for Microsoft
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em soluções de rede para a Microsoft.
ms.openlocfilehash: f990e4311ef88022d7fec2e1b7c90b3d8d035448
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939138"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="8cf2e-103">Criar registros DNS no Network Solutions for Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cf2e-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="8cf2e-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8cf2e-105">Se você usa a Network Solutions como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8cf2e-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-106">These are the main records to add.</span></span> <span data-ttu-id="8cf2e-107">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="8cf2e-108">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="8cf2e-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="8cf2e-109">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="8cf2e-110">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cf2e-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="8cf2e-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="8cf2e-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="8cf2e-112">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cf2e-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="8cf2e-113">Depois que você adicionar esses registros às soluções de rede, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="8cf2e-p102">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8cf2e-117">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="8cf2e-117">Add a TXT record for verification</span></span>
<span data-ttu-id="8cf2e-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8cf2e-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8cf2e-p103">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cf2e-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8cf2e-123">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8cf2e-124">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8cf2e-125">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8cf2e-126">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="8cf2e-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8cf2e-128">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8cf2e-130">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-130">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8cf2e-132">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8cf2e-133">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-133">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8cf2e-135">Role para baixo até a seção **texto (registros txt)** e selecione **editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selecionar editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="8cf2e-137">Nas caixas do novo registro, digite ou copie e cole os valores na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="8cf2e-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-138">**Host**</span></span>|<span data-ttu-id="8cf2e-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-139">**TTL**</span></span>|<span data-ttu-id="8cf2e-140">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="8cf2e-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8cf2e-142">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-142">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8cf2e-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8cf2e-144">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-144">**Note:** This is an example.</span></span> <span data-ttu-id="8cf2e-145">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="8cf2e-146">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="8cf2e-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Digitar ou colar valores nas caixas do novo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="8cf2e-148">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-148">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="8cf2e-150">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-150">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="8cf2e-152">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8cf2e-153">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8cf2e-154">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="8cf2e-155">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8cf2e-156">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8cf2e-157">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8cf2e-158">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8cf2e-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8cf2e-162">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8cf2e-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8cf2e-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8cf2e-164">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8cf2e-165">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8cf2e-166">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8cf2e-167">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="8cf2e-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8cf2e-169">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8cf2e-171">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-171">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8cf2e-173">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8cf2e-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-174">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8cf2e-176">Role para baixo até a seção **servidores de email (registros MX)** e selecione **editar registros MX**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Selecione Editar registros MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="8cf2e-178">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8cf2e-179">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-179">**Priority**</span></span>|<span data-ttu-id="8cf2e-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-180">**TTL**</span></span>|<span data-ttu-id="8cf2e-181">**Servidor de Email**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8cf2e-182">10 </span><span class="sxs-lookup"><span data-stu-id="8cf2e-182">10</span></span>  <br/> <span data-ttu-id="8cf2e-183">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-183">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="8cf2e-184">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-184">3600</span></span>  <br/> | <span data-ttu-id="8cf2e-185">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8cf2e-186">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8cf2e-187">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="8cf2e-188">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="8cf2e-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Digitar ou colar valores nas caixas do novo registro](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="8cf2e-190">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-190">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="8cf2e-192">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-192">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="8cf2e-194">Se houver outros registros MX, exclua todos escolhendo **Excluir** para cada registro.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="8cf2e-196">Quando estiverem todos selecionados, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-196">When they are all selected, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="8cf2e-198">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-198">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8cf2e-200">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cf2e-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8cf2e-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8cf2e-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8cf2e-202">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8cf2e-203">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8cf2e-204">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8cf2e-205">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="8cf2e-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8cf2e-207">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8cf2e-209">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-209">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8cf2e-211">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8cf2e-212">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-212">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8cf2e-214">Role para baixo até a seção **aliases de host (registros CNAME)** e selecione **editar registros CNAME**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Selecione Editar registros CNAME em aliases de host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="8cf2e-216">Nas caixas dos quatro novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8cf2e-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-217">**Alias**</span></span>|<span data-ttu-id="8cf2e-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-218">**TTL**</span></span>|<span data-ttu-id="8cf2e-219">**Refere-se ao Nome do host**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-219">**Refers to Host Name**</span></span>|<span data-ttu-id="8cf2e-220">**Outro Host          (selecione o botão de opção **Outro Host**)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8cf2e-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8cf2e-221">autodiscover</span></span>  <br/> |<span data-ttu-id="8cf2e-222">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-222">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-223">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-223">(No setting)</span></span>  <br/> |<span data-ttu-id="8cf2e-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8cf2e-225">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8cf2e-226">sip</span><span class="sxs-lookup"><span data-stu-id="8cf2e-226">sip</span></span>  <br/> |<span data-ttu-id="8cf2e-227">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-227">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-228">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-228">(No setting)</span></span>  <br/> |<span data-ttu-id="8cf2e-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8cf2e-230">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8cf2e-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8cf2e-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8cf2e-232">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-232">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-233">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-233">(No setting)</span></span>  <br/> |<span data-ttu-id="8cf2e-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8cf2e-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8cf2e-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8cf2e-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8cf2e-237">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-237">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-238">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-238">(No setting)</span></span>  <br/> |<span data-ttu-id="8cf2e-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8cf2e-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="8cf2e-240">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8cf2e-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8cf2e-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8cf2e-242">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-242">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-243">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-243">(No setting)</span></span>  <br/> |<span data-ttu-id="8cf2e-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8cf2e-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="8cf2e-245">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Digitar ou colar valores dos novos registros](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="8cf2e-247">Depois de adicionar todos os registros CNAME necessários, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="8cf2e-249">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-249">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8cf2e-251">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="8cf2e-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8cf2e-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8cf2e-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cf2e-253">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8cf2e-254">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8cf2e-255">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8cf2e-256">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="8cf2e-257">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8cf2e-258">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8cf2e-259">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8cf2e-260">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="8cf2e-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8cf2e-262">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8cf2e-264">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-264">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8cf2e-266">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8cf2e-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-267">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8cf2e-269">Role para baixo até a seção **texto (registros txt)** e selecione **editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selecionar editar registros TXT em texto](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="8cf2e-271">Nas caixas do novo registro, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="8cf2e-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-272">**Host**</span></span>|<span data-ttu-id="8cf2e-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-273">**TTL**</span></span>|<span data-ttu-id="8cf2e-274">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="8cf2e-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8cf2e-276">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-276">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8cf2e-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8cf2e-278">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Digitar ou colar valores para o novo registro](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="8cf2e-280">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-280">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="8cf2e-282">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-282">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8cf2e-284">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cf2e-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8cf2e-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8cf2e-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8cf2e-286">Siga as etapas abaixo ou [assista ao vídeo (inicia em 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8cf2e-p113">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8cf2e-289">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="8cf2e-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8cf2e-291">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8cf2e-293">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-293">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8cf2e-295">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8cf2e-296">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8cf2e-296">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8cf2e-298">Role para baixo até a seção **serviço (Registros SRV)** e selecione **Editar Registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selecione Editar Registros SRV em serviço](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="8cf2e-300">Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8cf2e-301">Escolha os valores **Serviço** e **Protocolo** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="8cf2e-302">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-302">**Service**</span></span>|<span data-ttu-id="8cf2e-303">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-303">**Protocol**</span></span>|<span data-ttu-id="8cf2e-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-304">**TTL**</span></span>|<span data-ttu-id="8cf2e-305">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-305">**Priority**</span></span>|<span data-ttu-id="8cf2e-306">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-306">**Weight**</span></span>|<span data-ttu-id="8cf2e-307">**Porta**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-307">**Port**</span></span>|<span data-ttu-id="8cf2e-308">**Destino**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8cf2e-309">_sip</span><span class="sxs-lookup"><span data-stu-id="8cf2e-309">_sip</span></span>  <br/> |<span data-ttu-id="8cf2e-310">_tls</span><span class="sxs-lookup"><span data-stu-id="8cf2e-310">_tls</span></span>  <br/> |<span data-ttu-id="8cf2e-311">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-311">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-312">100</span><span class="sxs-lookup"><span data-stu-id="8cf2e-312">100</span></span>  <br/> |<span data-ttu-id="8cf2e-313">1</span><span class="sxs-lookup"><span data-stu-id="8cf2e-313">1</span></span>  <br/> |<span data-ttu-id="8cf2e-314">443</span><span class="sxs-lookup"><span data-stu-id="8cf2e-314">443</span></span>  <br/> |<span data-ttu-id="8cf2e-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8cf2e-316">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8cf2e-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8cf2e-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="8cf2e-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="8cf2e-318">_tcp</span></span>  <br/> |<span data-ttu-id="8cf2e-319">3600</span><span class="sxs-lookup"><span data-stu-id="8cf2e-319">3600</span></span>  <br/> |<span data-ttu-id="8cf2e-320">100</span><span class="sxs-lookup"><span data-stu-id="8cf2e-320">100</span></span>  <br/> |<span data-ttu-id="8cf2e-321">1</span><span class="sxs-lookup"><span data-stu-id="8cf2e-321">1</span></span>  <br/> |<span data-ttu-id="8cf2e-322">5061</span><span class="sxs-lookup"><span data-stu-id="8cf2e-322">5061</span></span>  <br/> |<span data-ttu-id="8cf2e-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="8cf2e-324">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8cf2e-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Digitar ou colar valores dos novos registros](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="8cf2e-326">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-326">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="8cf2e-328">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8cf2e-328">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="8cf2e-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8cf2e-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
