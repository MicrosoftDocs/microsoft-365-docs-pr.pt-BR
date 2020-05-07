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
ms.openlocfilehash: 6bfe32ba8f77adec97f4ab5ee40e92126be91f10
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049006"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="fd5e2-103">Criar registros DNS no Google Domains para Microsoft</span><span class="sxs-lookup"><span data-stu-id="fd5e2-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="fd5e2-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fd5e2-105">Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="fd5e2-106">Depois que você adicionar esses registros no Google Domains, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="fd5e2-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fd5e2-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fd5e2-109">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fd5e2-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fd5e2-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="fd5e2-110">Add a TXT record for verification</span></span>
<span data-ttu-id="fd5e2-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fd5e2-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fd5e2-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd5e2-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fd5e2-p104">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="fd5e2-119">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="fd5e2-120">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="fd5e2-121">Na página **meus domínios** , localize o domínio que você deseja usar com a Microsoft e selecione o link **gerenciar** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="fd5e2-122">No painel de navegação à esquerda, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="fd5e2-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fd5e2-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="fd5e2-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fd5e2-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-126">**Name**</span></span> <br/> |<span data-ttu-id="fd5e2-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-127">**Type**</span></span> <br/> |<span data-ttu-id="fd5e2-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-128">**TTL**</span></span> <br/> |<span data-ttu-id="fd5e2-129">**Dados**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="fd5e2-130">TXT</span><span class="sxs-lookup"><span data-stu-id="fd5e2-130">TXT</span></span>  <br/> |<span data-ttu-id="fd5e2-131">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-131">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fd5e2-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fd5e2-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-133">**Note:** This is an example.</span></span> <span data-ttu-id="fd5e2-134">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="fd5e2-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="fd5e2-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="fd5e2-136">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="fd5e2-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fd5e2-138">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="fd5e2-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fd5e2-140">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fd5e2-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="fd5e2-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="fd5e2-143">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fd5e2-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fd5e2-145">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fd5e2-146">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fd5e2-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fd5e2-147">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fd5e2-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fd5e2-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="fd5e2-p108">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="fd5e2-152">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="fd5e2-153">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="fd5e2-154">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fd5e2-155">Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="fd5e2-156">Os registros MX do G Suite impedem que você adicione qualquer outro registro MX, incluindo aqueles necessários para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="fd5e2-157">Excluir os registros do G Suite não exclui sua conta do G Suite.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="fd5e2-158">Para excluir os registros MX do G Suite, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="fd5e2-159">Na seção **registros sintéticos** , na área **G Suite** , selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="fd5e2-160">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-160">(You may have to scroll down.)</span></span>
    
    ![Selecione Excluir na seção registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="fd5e2-162">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-162">Select **Delete**.</span></span>
    
    ![Selecione Excluir](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="fd5e2-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fd5e2-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="fd5e2-166">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="fd5e2-167">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-167">**Name**</span></span>|<span data-ttu-id="fd5e2-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-168">**Type**</span></span>|<span data-ttu-id="fd5e2-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-169">**TTL**</span></span>|<span data-ttu-id="fd5e2-170">**Dados**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fd5e2-171">MX</span><span class="sxs-lookup"><span data-stu-id="fd5e2-171">MX</span></span>  <br/> |<span data-ttu-id="fd5e2-172">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-172">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-173">0  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="fd5e2-174">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="fd5e2-p110">O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="fd5e2-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="fd5e2-177">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="fd5e2-178">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="fd5e2-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="fd5e2-179">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="fd5e2-181">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-181">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="fd5e2-183">Se houver outros registros MX personalizados, remova-os:</span><span class="sxs-lookup"><span data-stu-id="fd5e2-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="fd5e2-184">Selecione **Editar** na linha do registro MX.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Selecionar Editar na linha do registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="fd5e2-186">Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **dados** e, em seguida, pressione a tecla **delete** no teclado para excluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="fd5e2-187">Continue até excluir a entrada **Dados** para cada um dos outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="fd5e2-189">Quando tiver excluído a entrada de **dados** de cada um dos outros registros MX, selecione **salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Selecione salvar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fd5e2-191">Adicionar os cinco registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="fd5e2-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="fd5e2-192">Para começar, vá até a sua página [Google Domains] (https://domains.google.com/registrar) e entre.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="fd5e2-193">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="fd5e2-194">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="fd5e2-195">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="fd5e2-196">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="fd5e2-197">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="fd5e2-198">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-198">**Name**</span></span>|<span data-ttu-id="fd5e2-199">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-199">**Type**</span></span>|<span data-ttu-id="fd5e2-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-200">**TTL**</span></span>|<span data-ttu-id="fd5e2-201">**Dados**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fd5e2-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fd5e2-202">autodiscover</span></span>  <br/> |<span data-ttu-id="fd5e2-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd5e2-203">CNAME</span></span>  <br/> |<span data-ttu-id="fd5e2-204">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-204">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="fd5e2-206">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fd5e2-207">sip</span><span class="sxs-lookup"><span data-stu-id="fd5e2-207">sip</span></span>  <br/> |<span data-ttu-id="fd5e2-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd5e2-208">CNAME</span></span>  <br/> |<span data-ttu-id="fd5e2-209">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-209">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fd5e2-211">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fd5e2-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fd5e2-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fd5e2-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd5e2-213">CNAME</span></span>  <br/> |<span data-ttu-id="fd5e2-214">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-214">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fd5e2-216">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fd5e2-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fd5e2-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fd5e2-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd5e2-218">CNAME</span></span>  <br/> |<span data-ttu-id="fd5e2-219">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-219">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="fd5e2-221">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fd5e2-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fd5e2-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fd5e2-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="fd5e2-223">CNAME</span></span>  <br/> |<span data-ttu-id="fd5e2-224">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-224">1H</span></span>  <br/> |<span data-ttu-id="fd5e2-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="fd5e2-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="fd5e2-228">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-228">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="fd5e2-230">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="fd5e2-231">Na seção **registros de recursos personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="fd5e2-232">Repita esse processo até ter criado todos os registros CNAME necessários.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fd5e2-233">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="fd5e2-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd5e2-234">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fd5e2-235">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fd5e2-236">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fd5e2-237">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="fd5e2-238">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="fd5e2-238">Need examples?</span></span> <span data-ttu-id="fd5e2-239">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="fd5e2-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="fd5e2-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="fd5e2-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="fd5e2-p113">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="fd5e2-244">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="fd5e2-245">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="fd5e2-246">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="fd5e2-247">Na seção **registros de recursos personalizados** , na linha do registro TXT, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fd5e2-p114">O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selecionar Editar na linha do registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="fd5e2-252">Selecione o controle **(+)** .</span><span class="sxs-lookup"><span data-stu-id="fd5e2-252">Select the **(+)** control.</span></span> 
    
    ![Selecione o controle de adição](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="fd5e2-254">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="fd5e2-255">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="fd5e2-256">**Dados**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="fd5e2-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fd5e2-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="fd5e2-258">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="fd5e2-260">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-260">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fd5e2-262">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fd5e2-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fd5e2-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fd5e2-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="fd5e2-p115">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="fd5e2-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="fd5e2-267">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="fd5e2-268">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="fd5e2-269">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="fd5e2-270">Adicione o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="fd5e2-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fd5e2-272">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="fd5e2-273">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="fd5e2-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="fd5e2-274">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-274">**Name**</span></span>|<span data-ttu-id="fd5e2-275">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-275">**Type**</span></span>|<span data-ttu-id="fd5e2-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-276">**TTL**</span></span>|<span data-ttu-id="fd5e2-277">**Dados**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fd5e2-278">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="fd5e2-278">_sip._tls</span></span>|<span data-ttu-id="fd5e2-279">SRV</span><span class="sxs-lookup"><span data-stu-id="fd5e2-279">SRV</span></span>|<span data-ttu-id="fd5e2-280">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-280">1H</span></span>|<span data-ttu-id="fd5e2-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="fd5e2-282">**Esse valor deve terminar com um ponto (.)** **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="fd5e2-283">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="fd5e2-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="fd5e2-284">SRV</span><span class="sxs-lookup"><span data-stu-id="fd5e2-284">SRV</span></span>|<span data-ttu-id="fd5e2-285">1H</span><span class="sxs-lookup"><span data-stu-id="fd5e2-285">1H</span></span>|<span data-ttu-id="fd5e2-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="fd5e2-287">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fd5e2-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="fd5e2-288">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="fd5e2-290">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-290">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="fd5e2-292">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="fd5e2-293">Na seção **registros de recursos personalizados** , crie um registro usando os valores da segunda linha da tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fd5e2-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fd5e2-295">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="fd5e2-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fd5e2-296">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fd5e2-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
