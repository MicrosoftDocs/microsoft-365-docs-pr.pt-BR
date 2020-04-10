---
title: Criar registros DNS no site Network Solutions para o Office 365
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em soluções de rede para o Office 365.
ms.openlocfilehash: 6bbe954f763e0cb06e9bf32b991e60da34393c57
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211117"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="a9cf6-103">Criar registros DNS no site Network Solutions para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="a9cf6-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a9cf6-105">Se você usa a Network Solutions como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a9cf6-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-106">These are the main records to add.</span></span> <span data-ttu-id="a9cf6-107">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="a9cf6-108">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a9cf6-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="a9cf6-109">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="a9cf6-110">Adicionar os registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="a9cf6-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="a9cf6-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a9cf6-112">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="a9cf6-113">Depois que você adicionar esses registros à Network Solutions, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a9cf6-114">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a9cf6-p102">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a9cf6-118">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a9cf6-118">Add a TXT record for verification</span></span>
<span data-ttu-id="a9cf6-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a9cf6-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a9cf6-p103">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9cf6-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a9cf6-124">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a9cf6-125">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a9cf6-126">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cf6-127">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="a9cf6-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a9cf6-129">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a9cf6-131">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-131">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a9cf6-133">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a9cf6-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-134">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a9cf6-136">Role para baixo até a seção **texto (registros txt)** e selecione **editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selecionar editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="a9cf6-138">Nas caixas do novo registro, digite ou copie e cole os valores na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="a9cf6-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-139">**Host**</span></span>|<span data-ttu-id="a9cf6-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-140">**TTL**</span></span>|<span data-ttu-id="a9cf6-141">**Texto**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="a9cf6-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a9cf6-143">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-143">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-144">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a9cf6-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a9cf6-145">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-145">**Note:** This is an example.</span></span> <span data-ttu-id="a9cf6-146">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="a9cf6-147">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a9cf6-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Digitar ou colar valores nas caixas do novo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="a9cf6-149">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-149">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="a9cf6-151">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-151">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="a9cf6-153">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a9cf6-154">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a9cf6-155">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="a9cf6-156">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a9cf6-157">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a9cf6-158">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a9cf6-159">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a9cf6-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a9cf6-163">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a9cf6-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a9cf6-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a9cf6-165">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a9cf6-166">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a9cf6-167">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cf6-168">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="a9cf6-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a9cf6-170">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a9cf6-172">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-172">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a9cf6-174">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a9cf6-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-175">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a9cf6-177">Role para baixo até a seção **servidores de email (registros MX)** e selecione **editar registros MX**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Selecione Editar registros MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="a9cf6-179">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a9cf6-180">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-180">**Priority**</span></span>|<span data-ttu-id="a9cf6-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-181">**TTL**</span></span>|<span data-ttu-id="a9cf6-182">**Servidor de Email**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a9cf6-183">10 </span><span class="sxs-lookup"><span data-stu-id="a9cf6-183">10</span></span>  <br/> <span data-ttu-id="a9cf6-184">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="a9cf6-185">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-185">3600</span></span>  <br/> | <span data-ttu-id="a9cf6-186">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a9cf6-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a9cf6-188">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="a9cf6-189">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a9cf6-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Digitar ou colar valores nas caixas do novo registro](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="a9cf6-191">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-191">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="a9cf6-193">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-193">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="a9cf6-195">Se houver outros registros MX, exclua todos escolhendo **Excluir** para cada registro.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="a9cf6-197">Quando estiverem todos selecionados, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-197">When they are all selected, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="a9cf6-199">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-199">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a9cf6-201">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a9cf6-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a9cf6-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a9cf6-203">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a9cf6-204">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a9cf6-205">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cf6-206">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="a9cf6-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a9cf6-208">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a9cf6-210">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-210">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a9cf6-212">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a9cf6-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-213">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a9cf6-215">Role para baixo até a seção **aliases de host (registros CNAME)** e selecione **editar registros CNAME**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Selecione Editar registros CNAME em aliases de host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="a9cf6-217">Nas caixas dos quatro novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a9cf6-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-218">**Alias**</span></span>|<span data-ttu-id="a9cf6-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-219">**TTL**</span></span>|<span data-ttu-id="a9cf6-220">**Refere-se ao Nome do host**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-220">**Refers to Host Name**</span></span>|<span data-ttu-id="a9cf6-221">**Outro Host          (selecione o botão de opção **Outro Host**)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a9cf6-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a9cf6-222">autodiscover</span></span>  <br/> |<span data-ttu-id="a9cf6-223">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-223">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-224">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-224">(No setting)</span></span>  <br/> |<span data-ttu-id="a9cf6-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a9cf6-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a9cf6-227">sip</span><span class="sxs-lookup"><span data-stu-id="a9cf6-227">sip</span></span>  <br/> |<span data-ttu-id="a9cf6-228">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-228">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-229">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-229">(No setting)</span></span>  <br/> |<span data-ttu-id="a9cf6-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a9cf6-231">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a9cf6-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a9cf6-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a9cf6-233">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-233">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-234">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-234">(No setting)</span></span>  <br/> |<span data-ttu-id="a9cf6-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a9cf6-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a9cf6-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a9cf6-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a9cf6-238">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-238">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-239">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-239">(No setting)</span></span>  <br/> |<span data-ttu-id="a9cf6-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a9cf6-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="a9cf6-241">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a9cf6-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a9cf6-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a9cf6-243">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-243">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-244">(Sem configuração)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-244">(No setting)</span></span>  <br/> |<span data-ttu-id="a9cf6-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a9cf6-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="a9cf6-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Digitar ou colar valores dos novos registros](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="a9cf6-248">Depois de adicionar todos os registros CNAME necessários, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="a9cf6-250">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-250">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a9cf6-252">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="a9cf6-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a9cf6-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a9cf6-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9cf6-254">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a9cf6-255">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a9cf6-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a9cf6-257">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="a9cf6-258">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a9cf6-259">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a9cf6-260">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cf6-261">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="a9cf6-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a9cf6-263">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a9cf6-265">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-265">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a9cf6-267">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a9cf6-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-268">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a9cf6-270">Role para baixo até a seção **texto (registros txt)** e selecione **editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selecionar editar registros TXT em texto](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="a9cf6-272">Nas caixas do novo registro, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="a9cf6-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-273">**Host**</span></span>|<span data-ttu-id="a9cf6-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-274">**TTL**</span></span>|<span data-ttu-id="a9cf6-275">**Texto**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="a9cf6-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a9cf6-277">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-277">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a9cf6-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a9cf6-279">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Digitar ou colar valores para o novo registro](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="a9cf6-281">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-281">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="a9cf6-283">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-283">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a9cf6-285">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="a9cf6-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a9cf6-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a9cf6-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a9cf6-287">Siga as etapas abaixo ou [assista ao vídeo (inicia em 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a9cf6-p113">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cf6-290">Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** .</span><span class="sxs-lookup"><span data-stu-id="a9cf6-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a9cf6-292">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a9cf6-294">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-294">Select **Edit DNS**.</span></span>
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a9cf6-296">Selecione **gerenciar registros de DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a9cf6-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a9cf6-297">(You may have to scroll down.)</span></span>
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a9cf6-299">Role para baixo até a seção **serviço (Registros SRV)** e selecione **Editar Registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selecione Editar Registros SRV em serviço](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="a9cf6-301">Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a9cf6-302">Escolha os valores **Serviço** e **Protocolo** nas listas suspensas.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a9cf6-303">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-303">**Service**</span></span>|<span data-ttu-id="a9cf6-304">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-304">**Protocol**</span></span>|<span data-ttu-id="a9cf6-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-305">**TTL**</span></span>|<span data-ttu-id="a9cf6-306">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-306">**Priority**</span></span>|<span data-ttu-id="a9cf6-307">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-307">**Weight**</span></span>|<span data-ttu-id="a9cf6-308">**Porta**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-308">**Port**</span></span>|<span data-ttu-id="a9cf6-309">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a9cf6-310">_sip</span><span class="sxs-lookup"><span data-stu-id="a9cf6-310">_sip</span></span>  <br/> |<span data-ttu-id="a9cf6-311">_tls</span><span class="sxs-lookup"><span data-stu-id="a9cf6-311">_tls</span></span>  <br/> |<span data-ttu-id="a9cf6-312">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-312">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-313">100</span><span class="sxs-lookup"><span data-stu-id="a9cf6-313">100</span></span>  <br/> |<span data-ttu-id="a9cf6-314">1</span><span class="sxs-lookup"><span data-stu-id="a9cf6-314">1</span></span>  <br/> |<span data-ttu-id="a9cf6-315">443</span><span class="sxs-lookup"><span data-stu-id="a9cf6-315">443</span></span>  <br/> |<span data-ttu-id="a9cf6-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a9cf6-317">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a9cf6-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a9cf6-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a9cf6-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="a9cf6-319">_tcp</span></span>  <br/> |<span data-ttu-id="a9cf6-320">3600</span><span class="sxs-lookup"><span data-stu-id="a9cf6-320">3600</span></span>  <br/> |<span data-ttu-id="a9cf6-321">100</span><span class="sxs-lookup"><span data-stu-id="a9cf6-321">100</span></span>  <br/> |<span data-ttu-id="a9cf6-322">1</span><span class="sxs-lookup"><span data-stu-id="a9cf6-322">1</span></span>  <br/> |<span data-ttu-id="a9cf6-323">5061</span><span class="sxs-lookup"><span data-stu-id="a9cf6-323">5061</span></span>  <br/> |<span data-ttu-id="a9cf6-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a9cf6-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a9cf6-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Digitar ou colar valores dos novos registros](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="a9cf6-327">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-327">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="a9cf6-329">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="a9cf6-329">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar alterações](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="a9cf6-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a9cf6-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
