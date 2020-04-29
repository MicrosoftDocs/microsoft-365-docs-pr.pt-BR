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
ms.openlocfilehash: 399482374f87d864edbc01feb4896b168d157f7f
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919743"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="526c0-103">Criar registros DNS no Google Domains para Microsoft</span><span class="sxs-lookup"><span data-stu-id="526c0-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="526c0-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="526c0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="526c0-105">Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="526c0-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="526c0-106">Depois que você adicionar esses registros no Google Domains, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526c0-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="526c0-107">Para saber mais sobre hospedagem na web e DNS para sites com a Microsoft, confira [Usar um site público com o a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="526c0-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="526c0-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="526c0-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="526c0-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="526c0-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="526c0-110">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="526c0-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="526c0-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="526c0-111">Add a TXT record for verification</span></span>
<span data-ttu-id="526c0-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="526c0-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="526c0-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="526c0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="526c0-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="526c0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="526c0-p104">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="526c0-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="526c0-120">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="526c0-121">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="526c0-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="526c0-122">Na página **meus domínios** , localize o domínio que você deseja usar com a Microsoft e selecione o link **gerenciar** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="526c0-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="526c0-123">No painel de navegação à esquerda, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="526c0-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="526c0-124">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="526c0-124">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="526c0-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="526c0-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="526c0-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="526c0-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="526c0-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="526c0-127">**Name**</span></span> <br/> |<span data-ttu-id="526c0-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="526c0-128">**Type**</span></span> <br/> |<span data-ttu-id="526c0-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="526c0-129">**TTL**</span></span> <br/> |<span data-ttu-id="526c0-130">**Dados**</span><span class="sxs-lookup"><span data-stu-id="526c0-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="526c0-131">TXT</span><span class="sxs-lookup"><span data-stu-id="526c0-131">TXT</span></span>  <br/> |<span data-ttu-id="526c0-132">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-132">1H</span></span>  <br/> |<span data-ttu-id="526c0-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="526c0-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="526c0-134">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="526c0-134">**Note:** This is an example.</span></span> <span data-ttu-id="526c0-135">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="526c0-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="526c0-136">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="526c0-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="526c0-137">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="526c0-138">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="526c0-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="526c0-139">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="526c0-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="526c0-140">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="526c0-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="526c0-141">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="526c0-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="526c0-142">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="526c0-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="526c0-143">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="526c0-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="526c0-144">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="526c0-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="526c0-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="526c0-146">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="526c0-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="526c0-147">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="526c0-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="526c0-148">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526c0-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="526c0-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="526c0-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="526c0-p108">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="526c0-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="526c0-153">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="526c0-154">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="526c0-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="526c0-155">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="526c0-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="526c0-156">Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta.</span><span class="sxs-lookup"><span data-stu-id="526c0-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="526c0-157">Os registros MX do G Suite impedem que você adicione qualquer outro registro MX, incluindo aqueles necessários para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526c0-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="526c0-158">Excluir os registros do G Suite não exclui sua conta do G Suite.</span><span class="sxs-lookup"><span data-stu-id="526c0-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="526c0-159">Para excluir os registros MX do G Suite, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="526c0-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="526c0-160">Na seção **registros sintéticos** , na área **G Suite** , selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="526c0-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="526c0-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="526c0-161">(You may have to scroll down.)</span></span>
    
    ![Selecione Excluir na seção registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="526c0-163">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="526c0-163">Select **Delete**.</span></span>
    
    ![Selecione Excluir](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="526c0-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="526c0-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="526c0-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="526c0-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="526c0-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="526c0-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="526c0-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="526c0-168">**Name**</span></span>|<span data-ttu-id="526c0-169">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="526c0-169">**Type**</span></span>|<span data-ttu-id="526c0-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="526c0-170">**TTL**</span></span>|<span data-ttu-id="526c0-171">**Dados**</span><span class="sxs-lookup"><span data-stu-id="526c0-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="526c0-172">MX</span><span class="sxs-lookup"><span data-stu-id="526c0-172">MX</span></span>  <br/> |<span data-ttu-id="526c0-173">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-173">1H</span></span>  <br/> |<span data-ttu-id="526c0-174">0  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="526c0-175">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="526c0-p110">O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="526c0-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="526c0-178">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526c0-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="526c0-179">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="526c0-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="526c0-180">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="526c0-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="526c0-182">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-182">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="526c0-184">Se houver outros registros MX personalizados, remova-os:</span><span class="sxs-lookup"><span data-stu-id="526c0-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="526c0-185">Selecione **Editar** na linha do registro MX.</span><span class="sxs-lookup"><span data-stu-id="526c0-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Selecionar Editar na linha do registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="526c0-187">Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **dados** e, em seguida, pressione a tecla **delete** no teclado para excluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="526c0-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="526c0-188">Continue até excluir a entrada **Dados** para cada um dos outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="526c0-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="526c0-190">Quando tiver excluído a entrada de **dados** de cada um dos outros registros MX, selecione **salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="526c0-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Selecione salvar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="526c0-192">Adicionar os cinco registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="526c0-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="526c0-193">Para começar, vá até a sua página [Google Domains] (https://domains.google.com/registrar) e entre.</span><span class="sxs-lookup"><span data-stu-id="526c0-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="526c0-194">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="526c0-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="526c0-195">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="526c0-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="526c0-196">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="526c0-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="526c0-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="526c0-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="526c0-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="526c0-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="526c0-199">**Nome**</span><span class="sxs-lookup"><span data-stu-id="526c0-199">**Name**</span></span>|<span data-ttu-id="526c0-200">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="526c0-200">**Type**</span></span>|<span data-ttu-id="526c0-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="526c0-201">**TTL**</span></span>|<span data-ttu-id="526c0-202">**Dados**</span><span class="sxs-lookup"><span data-stu-id="526c0-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="526c0-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="526c0-203">autodiscover</span></span>  <br/> |<span data-ttu-id="526c0-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="526c0-204">CNAME</span></span>  <br/> |<span data-ttu-id="526c0-205">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-205">1H</span></span>  <br/> |<span data-ttu-id="526c0-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="526c0-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="526c0-208">sip</span><span class="sxs-lookup"><span data-stu-id="526c0-208">sip</span></span>  <br/> |<span data-ttu-id="526c0-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="526c0-209">CNAME</span></span>  <br/> |<span data-ttu-id="526c0-210">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-210">1H</span></span>  <br/> |<span data-ttu-id="526c0-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="526c0-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="526c0-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="526c0-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="526c0-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="526c0-214">CNAME</span></span>  <br/> |<span data-ttu-id="526c0-215">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-215">1H</span></span>  <br/> |<span data-ttu-id="526c0-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="526c0-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="526c0-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="526c0-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="526c0-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="526c0-219">CNAME</span></span>  <br/> |<span data-ttu-id="526c0-220">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-220">1H</span></span>  <br/> |<span data-ttu-id="526c0-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="526c0-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="526c0-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="526c0-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="526c0-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="526c0-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="526c0-224">CNAME</span></span>  <br/> |<span data-ttu-id="526c0-225">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-225">1H</span></span>  <br/> |<span data-ttu-id="526c0-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="526c0-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="526c0-229">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-229">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="526c0-231">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="526c0-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="526c0-232">Na seção **registros de recursos personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="526c0-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="526c0-233">Repita esse processo até ter criado todos os registros CNAME necessários.</span><span class="sxs-lookup"><span data-stu-id="526c0-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="526c0-234">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="526c0-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="526c0-235">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="526c0-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="526c0-236">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="526c0-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="526c0-237">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="526c0-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="526c0-238">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="526c0-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="526c0-239">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="526c0-239">Need examples?</span></span> <span data-ttu-id="526c0-240">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="526c0-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="526c0-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="526c0-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="526c0-p113">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="526c0-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="526c0-245">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="526c0-246">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="526c0-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="526c0-247">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="526c0-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="526c0-248">Na seção **registros de recursos personalizados** , na linha do registro TXT, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="526c0-p114">O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado**</span><span class="sxs-lookup"><span data-stu-id="526c0-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selecionar Editar na linha do registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="526c0-253">Selecione o controle **(+)** .</span><span class="sxs-lookup"><span data-stu-id="526c0-253">Select the **(+)** control.</span></span> 
    
    ![Selecione o controle de adição](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="526c0-255">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="526c0-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="526c0-256">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="526c0-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="526c0-257">**Dados**</span><span class="sxs-lookup"><span data-stu-id="526c0-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="526c0-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="526c0-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="526c0-259">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="526c0-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="526c0-261">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-261">Select **Save**.</span></span>
    
    ![Selecione salvar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="526c0-263">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="526c0-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="526c0-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="526c0-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="526c0-p115">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="526c0-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="526c0-268">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="526c0-269">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="526c0-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="526c0-270">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="526c0-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="526c0-271">Adicione o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="526c0-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="526c0-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="526c0-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="526c0-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="526c0-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="526c0-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="526c0-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="526c0-275">**Nome**</span><span class="sxs-lookup"><span data-stu-id="526c0-275">**Name**</span></span>|<span data-ttu-id="526c0-276">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="526c0-276">**Type**</span></span>|<span data-ttu-id="526c0-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="526c0-277">**TTL**</span></span>|<span data-ttu-id="526c0-278">**Dados**</span><span class="sxs-lookup"><span data-stu-id="526c0-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="526c0-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="526c0-279">_sip._tls</span></span>|<span data-ttu-id="526c0-280">SRV</span><span class="sxs-lookup"><span data-stu-id="526c0-280">SRV</span></span>|<span data-ttu-id="526c0-281">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-281">1H</span></span>|<span data-ttu-id="526c0-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="526c0-283">**Esse valor deve terminar com um ponto (.)** **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="526c0-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="526c0-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="526c0-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="526c0-285">SRV</span><span class="sxs-lookup"><span data-stu-id="526c0-285">SRV</span></span>|<span data-ttu-id="526c0-286">1H</span><span class="sxs-lookup"><span data-stu-id="526c0-286">1H</span></span>|<span data-ttu-id="526c0-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="526c0-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="526c0-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="526c0-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="526c0-289">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="526c0-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="526c0-291">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="526c0-291">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="526c0-293">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="526c0-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="526c0-294">Na seção **registros de recursos personalizados** , crie um registro usando os valores da segunda linha da tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="526c0-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="526c0-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="526c0-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="526c0-296">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="526c0-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="526c0-297">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="526c0-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
