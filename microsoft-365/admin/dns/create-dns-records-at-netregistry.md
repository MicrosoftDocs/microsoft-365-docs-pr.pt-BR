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
ms.openlocfilehash: 6aed84a4eaf95674358aa54986cfbb76edec2ef3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629306"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="b0c1c-103">Criar registros DNS no Netregistry para Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="b0c1c-104">Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b0c1c-105">Se o Netregistry for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b0c1c-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="b0c1c-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="b0c1c-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="b0c1c-108">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="b0c1c-109">Adicionar os registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b0c1c-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="b0c1c-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="b0c1c-111">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b0c1c-112">Depois que você adicionar esses registros ao Netregistry, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="b0c1c-113">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0c1c-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b0c1c-117">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="b0c1c-117">Add a TXT record for verification</span></span>
<span data-ttu-id="b0c1c-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="b0c1c-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="b0c1c-119">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b0c1c-120">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0c1c-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b0c1c-123">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="b0c1c-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="b0c1c-126">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="b0c1c-128">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="b0c1c-130">Em **Adicionar um registro de zona**, escolha **registro txt** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="b0c1c-132">Você deve usar aspas antes e depois da entrada na caixa TXT.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="b0c1c-133">No formulário **novo registro txt** , digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="b0c1c-134">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-134">**Name**</span></span>|<span data-ttu-id="b0c1c-135">**TTL (SEG)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-135">**TTL (SEC)**</span></span>|<span data-ttu-id="b0c1c-136">**TXT (aponta para endereço ou valor)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b0c1c-137">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="b0c1c-138">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="b0c1c-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="b0c1c-140">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-140">**Note:** This is an example.</span></span> <span data-ttu-id="b0c1c-141">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b0c1c-142">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="b0c1c-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="b0c1c-144">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-144">Select **Add record**.</span></span>
    
<span data-ttu-id="b0c1c-145">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b0c1c-146">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b0c1c-147">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b0c1c-148">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b0c1c-149">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b0c1c-150">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b0c1c-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b0c1c-154">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b0c1c-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="b0c1c-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="b0c1c-156">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="b0c1c-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="b0c1c-159">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="b0c1c-161">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="b0c1c-163">Em **registros de zona atuais**, remova os registros MX padrão selecionando **remover** ao lado de cada registro MX na lista.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="b0c1c-165">Em **Adicionar um registro de zona**, escolha **registro MX** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="b0c1c-167">No formulário **novo registro MX** , digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="b0c1c-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-168">**Name**</span></span>|<span data-ttu-id="b0c1c-169">**TTL (SEG)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-169">**TTL (SEC)**</span></span>|<span data-ttu-id="b0c1c-170">**Exchange (aponta para o endereço ou valor)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="b0c1c-171">**O host está totalmente qualificado?**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="b0c1c-172">**Preferência (prioridade)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b0c1c-173">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="b0c1c-174">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="b0c1c-175">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b0c1c-176">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-176">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="b0c1c-177">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="b0c1c-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="b0c1c-178">(marque a caixa de seleção)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="b0c1c-179">10 </span><span class="sxs-lookup"><span data-stu-id="b0c1c-179">10</span></span>  <br/> <span data-ttu-id="b0c1c-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="b0c1c-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="b0c1c-182">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b0c1c-184">Adicionar os registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-184">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b0c1c-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="b0c1c-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="b0c1c-186">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="b0c1c-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="b0c1c-189">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="b0c1c-191">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="b0c1c-193">Em **Adicionar um registro de zona**, escolha **registro CNAME** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="b0c1c-195">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b0c1c-196">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-196">**Name**</span></span>|<span data-ttu-id="b0c1c-197">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-197">**Type**</span></span>|<span data-ttu-id="b0c1c-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-198">**TTL**</span></span>|<span data-ttu-id="b0c1c-199">**HOST (aponta para ou valor de endereço)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b0c1c-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b0c1c-200">autodiscover</span></span>  <br/> |<span data-ttu-id="b0c1c-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="b0c1c-201">CNAME</span></span>  <br/> |<span data-ttu-id="b0c1c-202">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b0c1c-204">sip</span><span class="sxs-lookup"><span data-stu-id="b0c1c-204">sip</span></span>  <br/> |<span data-ttu-id="b0c1c-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="b0c1c-205">CNAME</span></span>  <br/> |<span data-ttu-id="b0c1c-206">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b0c1c-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b0c1c-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b0c1c-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="b0c1c-209">CNAME</span></span>  <br/> |<span data-ttu-id="b0c1c-210">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b0c1c-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b0c1c-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b0c1c-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="b0c1c-213">CNAME</span></span>  <br/> |<span data-ttu-id="b0c1c-214">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b0c1c-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b0c1c-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b0c1c-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b0c1c-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="b0c1c-217">CNAME</span></span>  <br/> |<span data-ttu-id="b0c1c-218">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="b0c1c-221">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="b0c1c-223">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="b0c1c-224">Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b0c1c-225">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="b0c1c-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b0c1c-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="b0c1c-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0c1c-227">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b0c1c-228">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b0c1c-229">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b0c1c-230">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="b0c1c-231">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="b0c1c-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="b0c1c-234">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="b0c1c-236">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="b0c1c-238">Em **Adicionar um registro de zona**, escolha **registro txt** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="b0c1c-240">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b0c1c-241">Você deve usar aspas antes e depois da entrada na caixa TXT.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="b0c1c-242">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-242">**Name**</span></span>|<span data-ttu-id="b0c1c-243">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-243">**Type**</span></span>|<span data-ttu-id="b0c1c-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-244">**TTL**</span></span>|<span data-ttu-id="b0c1c-245">**Dados TXT (destino)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b0c1c-246">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="b0c1c-247">TXT</span><span class="sxs-lookup"><span data-stu-id="b0c1c-247">TXT</span></span>  <br/> |<span data-ttu-id="b0c1c-248">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-249">"v = spf1 inclui include. Protection. Outlook. com-All"</span><span class="sxs-lookup"><span data-stu-id="b0c1c-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="b0c1c-250">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="b0c1c-252">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b0c1c-254">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0c1c-254">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b0c1c-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="b0c1c-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="b0c1c-256">Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="b0c1c-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="b0c1c-259">Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="b0c1c-261">Selecione **Gerenciador de zona**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="b0c1c-263">Em **Adicionar um registro de zona**, escolha **registro SRV** na lista e, em seguida, selecione **criar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="b0c1c-265">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0c1c-266">O campo nome é uma combinação do serviço (por exemplo, _sip) e o protocolo (por exemplo, _tls).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="b0c1c-267">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-267">**Type**</span></span>|<span data-ttu-id="b0c1c-268">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-268">**Name**</span></span>|<span data-ttu-id="b0c1c-269">**TTL (SEG)**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-269">**TTL (SEC)**</span></span>|<span data-ttu-id="b0c1c-270">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-270">**Priority**</span></span>|<span data-ttu-id="b0c1c-271">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-271">**Weight**</span></span>|<span data-ttu-id="b0c1c-272">**Porta**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-272">**Port**</span></span>|<span data-ttu-id="b0c1c-273">**Destino**</span><span class="sxs-lookup"><span data-stu-id="b0c1c-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b0c1c-274">SRV (serviço)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="b0c1c-275">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="b0c1c-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="b0c1c-276">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-277">100</span><span class="sxs-lookup"><span data-stu-id="b0c1c-277">100</span></span>  <br/> |<span data-ttu-id="b0c1c-278">1</span><span class="sxs-lookup"><span data-stu-id="b0c1c-278">1</span></span>  <br/> |<span data-ttu-id="b0c1c-279">443</span><span class="sxs-lookup"><span data-stu-id="b0c1c-279">443</span></span>  <br/> |<span data-ttu-id="b0c1c-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b0c1c-281">SRV (serviço)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="b0c1c-282">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="b0c1c-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b0c1c-283">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="b0c1c-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b0c1c-284">100</span><span class="sxs-lookup"><span data-stu-id="b0c1c-284">100</span></span>  <br/> |<span data-ttu-id="b0c1c-285">1</span><span class="sxs-lookup"><span data-stu-id="b0c1c-285">1</span></span>  <br/> |<span data-ttu-id="b0c1c-286">5061</span><span class="sxs-lookup"><span data-stu-id="b0c1c-286">5061</span></span>  <br/> |<span data-ttu-id="b0c1c-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b0c1c-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="b0c1c-289">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="b0c1c-291">Repita as etapas anteriores para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="b0c1c-292">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="b0c1c-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b0c1c-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b0c1c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

