---
title: Criar registros DNS no Netregistry para Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Netregistry para a Microsoft.
ms.openlocfilehash: ed3e3bae232dcbb3c8e4eea3d1a3bc4dd0a88799
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939150"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="d6ceb-103">Criar registros DNS no Netregistry para Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ceb-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="d6ceb-104">Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d6ceb-105">Se o Netregistry for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d6ceb-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="d6ceb-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d6ceb-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="d6ceb-108">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="d6ceb-109">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ceb-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="d6ceb-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="d6ceb-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="d6ceb-111">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ceb-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="d6ceb-112">Depois que você adicionar esses registros ao Netregistry, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="d6ceb-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d6ceb-116">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d6ceb-116">Add a TXT record for verification</span></span>
<span data-ttu-id="d6ceb-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="d6ceb-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="d6ceb-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6ceb-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d6ceb-122">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="d6ceb-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="d6ceb-125">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="d6ceb-127">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="d6ceb-129">Em **Adicionar um registro de zona**, escolha **registro txt** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="d6ceb-131">Você deve usar aspas antes e depois da entrada na caixa TXT.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="d6ceb-132">No formulário **novo registro txt** , digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="d6ceb-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-133">**Name**</span></span>|<span data-ttu-id="d6ceb-134">**TTL (SEG)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-134">**TTL (SEC)**</span></span>|<span data-ttu-id="d6ceb-135">**TXT (aponta para endereço ou valor)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d6ceb-136">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="d6ceb-137">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-138">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="d6ceb-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="d6ceb-139">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-139">**Note:** This is an example.</span></span> <span data-ttu-id="d6ceb-140">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d6ceb-141">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d6ceb-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="d6ceb-143">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-143">Select **Add record**.</span></span>
    
<span data-ttu-id="d6ceb-144">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d6ceb-145">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d6ceb-146">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d6ceb-147">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d6ceb-148">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d6ceb-149">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d6ceb-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d6ceb-153">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d6ceb-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="d6ceb-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="d6ceb-155">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="d6ceb-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="d6ceb-158">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="d6ceb-160">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="d6ceb-162">Em **registros de zona atuais**, remova os registros MX padrão selecionando **remover** ao lado de cada registro MX na lista.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="d6ceb-164">Em **Adicionar um registro de zona**, escolha **registro MX** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="d6ceb-166">No formulário **novo registro MX** , digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="d6ceb-167">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-167">**Name**</span></span>|<span data-ttu-id="d6ceb-168">**TTL (SEG)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-168">**TTL (SEC)**</span></span>|<span data-ttu-id="d6ceb-169">**Exchange (aponta para o endereço ou valor)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="d6ceb-170">**O host está totalmente qualificado?**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="d6ceb-171">**Preferência (prioridade)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d6ceb-172">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="d6ceb-173">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="d6ceb-174">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d6ceb-175">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="d6ceb-176">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d6ceb-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="d6ceb-177">(marque a caixa de seleção)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="d6ceb-178">10 </span><span class="sxs-lookup"><span data-stu-id="d6ceb-178">10</span></span>  <br/> <span data-ttu-id="d6ceb-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="d6ceb-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="d6ceb-181">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d6ceb-183">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ceb-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d6ceb-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="d6ceb-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="d6ceb-185">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="d6ceb-186">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="d6ceb-188">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="d6ceb-190">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="d6ceb-192">Em **Adicionar um registro de zona**, escolha **registro CNAME** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="d6ceb-194">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d6ceb-195">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-195">**Name**</span></span>|<span data-ttu-id="d6ceb-196">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-196">**Type**</span></span>|<span data-ttu-id="d6ceb-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-197">**TTL**</span></span>|<span data-ttu-id="d6ceb-198">**HOST (aponta para ou valor de endereço)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d6ceb-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d6ceb-199">autodiscover</span></span>  <br/> |<span data-ttu-id="d6ceb-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6ceb-200">CNAME</span></span>  <br/> |<span data-ttu-id="d6ceb-201">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d6ceb-203">sip</span><span class="sxs-lookup"><span data-stu-id="d6ceb-203">sip</span></span>  <br/> |<span data-ttu-id="d6ceb-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6ceb-204">CNAME</span></span>  <br/> |<span data-ttu-id="d6ceb-205">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d6ceb-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d6ceb-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d6ceb-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6ceb-208">CNAME</span></span>  <br/> |<span data-ttu-id="d6ceb-209">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d6ceb-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d6ceb-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d6ceb-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6ceb-212">CNAME</span></span>  <br/> |<span data-ttu-id="d6ceb-213">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d6ceb-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d6ceb-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d6ceb-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d6ceb-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6ceb-216">CNAME</span></span>  <br/> |<span data-ttu-id="d6ceb-217">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="d6ceb-220">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="d6ceb-222">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="d6ceb-223">Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d6ceb-224">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="d6ceb-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d6ceb-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="d6ceb-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6ceb-226">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d6ceb-227">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d6ceb-228">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d6ceb-229">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="d6ceb-230">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="d6ceb-231">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="d6ceb-233">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="d6ceb-235">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="d6ceb-237">Em **Adicionar um registro de zona**, escolha **registro txt** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="d6ceb-239">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d6ceb-240">Você deve usar aspas antes e depois da entrada na caixa TXT.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="d6ceb-241">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-241">**Name**</span></span>|<span data-ttu-id="d6ceb-242">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-242">**Type**</span></span>|<span data-ttu-id="d6ceb-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-243">**TTL**</span></span>|<span data-ttu-id="d6ceb-244">**Dados TXT (destino)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d6ceb-245">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="d6ceb-246">TXT</span><span class="sxs-lookup"><span data-stu-id="d6ceb-246">TXT</span></span>  <br/> |<span data-ttu-id="d6ceb-247">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-248">"v = spf1 inclui include. Protection. Outlook. com-All"</span><span class="sxs-lookup"><span data-stu-id="d6ceb-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="d6ceb-249">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="d6ceb-251">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d6ceb-253">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ceb-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d6ceb-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="d6ceb-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="d6ceb-255">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="d6ceb-256">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="d6ceb-258">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="d6ceb-260">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="d6ceb-262">Em **Adicionar um registro de zona**, escolha **registro SRV** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="d6ceb-264">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6ceb-265">O campo nome é uma combinação do serviço (por exemplo, _sip) e o protocolo (por exemplo, _tls).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="d6ceb-266">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-266">**Type**</span></span>|<span data-ttu-id="d6ceb-267">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-267">**Name**</span></span>|<span data-ttu-id="d6ceb-268">**TTL (SEG)**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-268">**TTL (SEC)**</span></span>|<span data-ttu-id="d6ceb-269">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-269">**Priority**</span></span>|<span data-ttu-id="d6ceb-270">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-270">**Weight**</span></span>|<span data-ttu-id="d6ceb-271">**Porta**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-271">**Port**</span></span>|<span data-ttu-id="d6ceb-272">**Destino**</span><span class="sxs-lookup"><span data-stu-id="d6ceb-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d6ceb-273">SRV (serviço)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="d6ceb-274">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="d6ceb-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="d6ceb-275">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-276">100</span><span class="sxs-lookup"><span data-stu-id="d6ceb-276">100</span></span>  <br/> |<span data-ttu-id="d6ceb-277">1</span><span class="sxs-lookup"><span data-stu-id="d6ceb-277">1</span></span>  <br/> |<span data-ttu-id="d6ceb-278">443</span><span class="sxs-lookup"><span data-stu-id="d6ceb-278">443</span></span>  <br/> |<span data-ttu-id="d6ceb-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d6ceb-280">SRV (serviço)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="d6ceb-281">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="d6ceb-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d6ceb-282">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="d6ceb-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="d6ceb-283">100</span><span class="sxs-lookup"><span data-stu-id="d6ceb-283">100</span></span>  <br/> |<span data-ttu-id="d6ceb-284">1</span><span class="sxs-lookup"><span data-stu-id="d6ceb-284">1</span></span>  <br/> |<span data-ttu-id="d6ceb-285">5061</span><span class="sxs-lookup"><span data-stu-id="d6ceb-285">5061</span></span>  <br/> |<span data-ttu-id="d6ceb-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6ceb-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="d6ceb-288">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="d6ceb-290">Repita as etapas anteriores para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="d6ceb-291">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="d6ceb-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6ceb-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d6ceb-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

