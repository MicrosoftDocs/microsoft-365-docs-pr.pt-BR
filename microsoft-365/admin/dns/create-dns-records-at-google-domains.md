---
title: Criar registros DNS no Google Domains para Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Lync e outros serviços no Google Domains for Microsoft.
ms.openlocfilehash: 20a3ba9baefcdb26936d2d0a5fda7ed1b5db971e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629534"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="80618-103">Criar registros DNS no Google Domains para Microsoft</span><span class="sxs-lookup"><span data-stu-id="80618-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="80618-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="80618-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="80618-105">Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="80618-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="80618-106">Depois que você adicionar esses registros no Google Domains, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80618-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="80618-107">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="80618-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="80618-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="80618-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="80618-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="80618-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="80618-110">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="80618-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="80618-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="80618-111">Add a TXT record for verification</span></span>
<span data-ttu-id="80618-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="80618-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="80618-113">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="80618-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="80618-114">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="80618-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80618-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="80618-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="80618-p104">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="80618-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="80618-120">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="80618-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="80618-121">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="80618-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="80618-122">Na página **meus domínios** , localize o domínio que você deseja usar com a Microsoft e selecione o link **gerenciar** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="80618-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="80618-123">No painel de navegação à esquerda, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="80618-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="80618-124">Na seção \* \* registros de recursos personalizados \* \*, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="80618-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80618-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="80618-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="80618-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80618-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="80618-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="80618-127">**Name**</span></span> <br/> |<span data-ttu-id="80618-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="80618-128">**Type**</span></span> <br/> |<span data-ttu-id="80618-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="80618-129">**TTL**</span></span> <br/> |<span data-ttu-id="80618-130">**Dados**</span><span class="sxs-lookup"><span data-stu-id="80618-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="80618-131">TXT</span><span class="sxs-lookup"><span data-stu-id="80618-131">TXT</span></span>  <br/> |<span data-ttu-id="80618-132">1H</span><span class="sxs-lookup"><span data-stu-id="80618-132">1H</span></span>  <br/> |<span data-ttu-id="80618-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="80618-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="80618-134">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="80618-134">**Note:** This is an example.</span></span> <span data-ttu-id="80618-135">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="80618-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="80618-136">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="80618-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="80618-137">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80618-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="80618-138">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="80618-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="80618-139">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="80618-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="80618-140">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="80618-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="80618-141">No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="80618-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="80618-142">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="80618-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="80618-143">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="80618-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="80618-144">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="80618-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80618-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="80618-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="80618-146">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="80618-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="80618-147">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="80618-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="80618-148">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="80618-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="80618-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="80618-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="80618-p108">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="80618-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="80618-153">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="80618-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="80618-154">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="80618-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="80618-155">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="80618-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80618-156">Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta.</span><span class="sxs-lookup"><span data-stu-id="80618-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="80618-157">Os registros MX do G Suite impedem que você adicione qualquer outro registro MX, incluindo aqueles necessários para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80618-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="80618-158">Excluir os registros do G Suite não exclui sua conta do G Suite.</span><span class="sxs-lookup"><span data-stu-id="80618-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="80618-159">Para excluir os registros MX do G Suite, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="80618-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="80618-160">Na seção **registros sintéticos** , na área **G Suite** , selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="80618-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="80618-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="80618-161">(You may have to scroll down.)</span></span>
    
    ![Selecione Excluir na seção registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="80618-163">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="80618-163">Select **Delete**.</span></span>
    
    ![Selecione Excluir](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="80618-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80618-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80618-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="80618-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="80618-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80618-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="80618-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="80618-168">**Name**</span></span>|<span data-ttu-id="80618-169">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="80618-169">**Type**</span></span>|<span data-ttu-id="80618-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="80618-170">**TTL**</span></span>|<span data-ttu-id="80618-171">**Dados**</span><span class="sxs-lookup"><span data-stu-id="80618-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="80618-172">MX</span><span class="sxs-lookup"><span data-stu-id="80618-172">MX</span></span>  <br/> |<span data-ttu-id="80618-173">1H</span><span class="sxs-lookup"><span data-stu-id="80618-173">1H</span></span>  <br/> |<span data-ttu-id="80618-174">0  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="80618-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="80618-175">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="80618-p110">O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="80618-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="80618-178">**Observação:** Obtenha sua \< *chave* \> de domínio de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80618-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="80618-179">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="80618-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="80618-180">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="80618-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="80618-182">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80618-182">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="80618-184">Se houver outros registros MX personalizados, remova-os:</span><span class="sxs-lookup"><span data-stu-id="80618-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="80618-185">Selecione **Editar** na linha do registro MX.</span><span class="sxs-lookup"><span data-stu-id="80618-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Selecionar Editar na linha do registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="80618-187">Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **dados** e, em seguida, pressione a tecla **delete** no teclado para excluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="80618-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="80618-188">Continue até excluir a entrada **Dados** para cada um dos outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="80618-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="80618-190">Quando tiver excluído a entrada de **dados** de cada um dos outros registros MX, selecione **salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="80618-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Selecione salvar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="80618-192">Adicionar os cinco registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="80618-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="80618-193">Para começar, vá até a sua página [Google Domains] (https://domains.google.com/registrar) e entre.</span><span class="sxs-lookup"><span data-stu-id="80618-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="80618-194">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="80618-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="80618-195">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="80618-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="80618-196">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="80618-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="80618-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="80618-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="80618-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80618-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="80618-199">**Nome**</span><span class="sxs-lookup"><span data-stu-id="80618-199">**Name**</span></span>|<span data-ttu-id="80618-200">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="80618-200">**Type**</span></span>|<span data-ttu-id="80618-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="80618-201">**TTL**</span></span>|<span data-ttu-id="80618-202">**Dados**</span><span class="sxs-lookup"><span data-stu-id="80618-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="80618-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="80618-203">autodiscover</span></span>  <br/> |<span data-ttu-id="80618-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="80618-204">CNAME</span></span>  <br/> |<span data-ttu-id="80618-205">1H</span><span class="sxs-lookup"><span data-stu-id="80618-205">1H</span></span>  <br/> |<span data-ttu-id="80618-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="80618-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="80618-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80618-208">sip</span><span class="sxs-lookup"><span data-stu-id="80618-208">sip</span></span>  <br/> |<span data-ttu-id="80618-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="80618-209">CNAME</span></span>  <br/> |<span data-ttu-id="80618-210">1H</span><span class="sxs-lookup"><span data-stu-id="80618-210">1H</span></span>  <br/> |<span data-ttu-id="80618-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80618-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="80618-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80618-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="80618-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="80618-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="80618-214">CNAME</span></span>  <br/> |<span data-ttu-id="80618-215">1H</span><span class="sxs-lookup"><span data-stu-id="80618-215">1H</span></span>  <br/> |<span data-ttu-id="80618-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80618-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="80618-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80618-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="80618-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="80618-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="80618-219">CNAME</span></span>  <br/> |<span data-ttu-id="80618-220">1H</span><span class="sxs-lookup"><span data-stu-id="80618-220">1H</span></span>  <br/> |<span data-ttu-id="80618-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="80618-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="80618-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80618-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="80618-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="80618-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="80618-224">CNAME</span></span>  <br/> |<span data-ttu-id="80618-225">1H</span><span class="sxs-lookup"><span data-stu-id="80618-225">1H</span></span>  <br/> |<span data-ttu-id="80618-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="80618-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="80618-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="80618-229">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80618-229">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="80618-231">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="80618-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="80618-232">Na seção **registros de recursos personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="80618-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="80618-233">Repita esse processo até ter criado todos os registros CNAME necessários.</span><span class="sxs-lookup"><span data-stu-id="80618-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="80618-234">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="80618-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80618-235">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="80618-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="80618-236">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="80618-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="80618-237">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80618-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="80618-238">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="80618-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="80618-239">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="80618-239">Need examples?</span></span> <span data-ttu-id="80618-240">Confira estes [registros de sistema de nomes de domínio externo para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="80618-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="80618-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="80618-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="80618-p113">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="80618-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="80618-245">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="80618-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="80618-246">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="80618-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="80618-247">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="80618-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="80618-248">Na seção **registros de recursos personalizados** , na linha do registro TXT, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="80618-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="80618-p114">O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado**</span><span class="sxs-lookup"><span data-stu-id="80618-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selecionar Editar na linha do registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="80618-253">Selecione o controle **(+)** .</span><span class="sxs-lookup"><span data-stu-id="80618-253">Select the **(+)** control.</span></span> 
    
    ![Selecione o controle de adição](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="80618-255">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="80618-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="80618-256">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="80618-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="80618-257">**Dados**</span><span class="sxs-lookup"><span data-stu-id="80618-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="80618-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="80618-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="80618-259">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="80618-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="80618-261">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80618-261">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="80618-263">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="80618-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="80618-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="80618-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="80618-p115">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="80618-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="80618-268">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="80618-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="80618-269">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="80618-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="80618-270">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="80618-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="80618-271">Adicione o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="80618-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="80618-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80618-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80618-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="80618-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="80618-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80618-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="80618-275">**Nome**</span><span class="sxs-lookup"><span data-stu-id="80618-275">**Name**</span></span>|<span data-ttu-id="80618-276">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="80618-276">**Type**</span></span>|<span data-ttu-id="80618-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="80618-277">**TTL**</span></span>|<span data-ttu-id="80618-278">**Dados**</span><span class="sxs-lookup"><span data-stu-id="80618-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="80618-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="80618-279">_sip._tls</span></span>|<span data-ttu-id="80618-280">SRV</span><span class="sxs-lookup"><span data-stu-id="80618-280">SRV</span></span>|<span data-ttu-id="80618-281">1H</span><span class="sxs-lookup"><span data-stu-id="80618-281">1H</span></span>|<span data-ttu-id="80618-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80618-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="80618-283">**Esse valor deve terminar com um ponto (.)** **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="80618-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="80618-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="80618-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="80618-285">SRV</span><span class="sxs-lookup"><span data-stu-id="80618-285">SRV</span></span>|<span data-ttu-id="80618-286">1H</span><span class="sxs-lookup"><span data-stu-id="80618-286">1H</span></span>|<span data-ttu-id="80618-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80618-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="80618-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="80618-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="80618-289">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="80618-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="80618-291">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80618-291">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="80618-293">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="80618-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="80618-294">Na seção **registros de recursos personalizados** , crie um registro usando os valores da segunda linha da tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="80618-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="80618-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="80618-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="80618-296">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="80618-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="80618-297">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="80618-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
