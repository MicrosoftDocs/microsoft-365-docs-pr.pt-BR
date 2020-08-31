---
title: Criar registros DNS no site Google Domains para a Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Aprenda a verificar seu domínio e a configurar registros DNS para emails, Lync e outros serviços no Google Domains para a Microsoft.
ms.openlocfilehash: 23f3a332b46e53946139869754d610733c89e4a9
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307110"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="8bbae-103">Criar registros DNS no site Google Domains para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bbae-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="8bbae-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8bbae-105">Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="8bbae-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="8bbae-106">Depois que você adicionar esses registros ao Google Domains, o domínio será configurado para funcionar com os serviços Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bbae-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="8bbae-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8bbae-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8bbae-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8bbae-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8bbae-109">Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, confira [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS na Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bbae-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8bbae-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="8bbae-110">Add a TXT record for verification</span></span>
<span data-ttu-id="8bbae-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8bbae-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8bbae-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="8bbae-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bbae-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="8bbae-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8bbae-p104">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="8bbae-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="8bbae-119">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="8bbae-120">Em seguida, insira suas credenciais de login e selecione novamente**Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="8bbae-121">Na página **Meus domínios**, localize o domínio que você deseja usar com a Microsoft e selecione o link **GERENCIAR** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="8bbae-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="8bbae-122">No painel de navegação esquerdo, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="8bbae-123">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bbae-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8bbae-124">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8bbae-125">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8bbae-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="8bbae-126">**Name**</span></span> <br/> |<span data-ttu-id="8bbae-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8bbae-127">**Type**</span></span> <br/> |<span data-ttu-id="8bbae-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bbae-128">**TTL**</span></span> <br/> |<span data-ttu-id="8bbae-129">**Dados**</span><span class="sxs-lookup"><span data-stu-id="8bbae-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="8bbae-130">TXT</span><span class="sxs-lookup"><span data-stu-id="8bbae-130">TXT</span></span>  <br/> |<span data-ttu-id="8bbae-131">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-131">1H</span></span>  <br/> |<span data-ttu-id="8bbae-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8bbae-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8bbae-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8bbae-133">**Note:** This is an example.</span></span> <span data-ttu-id="8bbae-134">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="8bbae-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="8bbae-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="8bbae-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="8bbae-136">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="8bbae-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="8bbae-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8bbae-138">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="8bbae-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8bbae-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="8bbae-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8bbae-140">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="8bbae-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8bbae-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="8bbae-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8bbae-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8bbae-143">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8bbae-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8bbae-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8bbae-145">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8bbae-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8bbae-146">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bbae-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8bbae-147">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bbae-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8bbae-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8bbae-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8bbae-p108">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="8bbae-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="8bbae-152">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="8bbae-153">Em seguida, insira suas credenciais de login e selecione novamente**Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="8bbae-154">Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="8bbae-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8bbae-155">Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta.</span><span class="sxs-lookup"><span data-stu-id="8bbae-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="8bbae-156">Os registros MX do G Suite impedem que você adicione outros registros MX, incluindo aqueles necessários para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bbae-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="8bbae-157">Excluir os registros do G Suite não exclui sua conta do G Suite.</span><span class="sxs-lookup"><span data-stu-id="8bbae-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="8bbae-158">Para excluir os registros MX do G Suite, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bbae-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="8bbae-159">Na seção **Registros sintéticos**, na área **G Suite**, escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="8bbae-160">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-160">(You may have to scroll down.)</span></span>
    
    ![Selecione Excluir na seção Registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="8bbae-162">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-162">Select **Delete**.</span></span>
    
    ![Selecionar Excluir](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="8bbae-164">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bbae-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8bbae-165">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8bbae-166">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8bbae-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="8bbae-167">**Name**</span></span>|<span data-ttu-id="8bbae-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8bbae-168">**Type**</span></span>|<span data-ttu-id="8bbae-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bbae-169">**TTL**</span></span>|<span data-ttu-id="8bbae-170">**Dados**</span><span class="sxs-lookup"><span data-stu-id="8bbae-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8bbae-171">MX</span><span class="sxs-lookup"><span data-stu-id="8bbae-171">MX</span></span>  <br/> |<span data-ttu-id="8bbae-172">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-172">1H</span></span>  <br/> |<span data-ttu-id="8bbae-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8bbae-174">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8bbae-p110">O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="8bbae-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="8bbae-177">**Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bbae-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="8bbae-178">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="8bbae-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="8bbae-179">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="8bbae-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="8bbae-181">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-181">Select **Add**.</span></span>
    
    ![Selecionar Adicionar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="8bbae-183">Se houver outros registros MX personalizados, remova-os.</span><span class="sxs-lookup"><span data-stu-id="8bbae-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="8bbae-184">Selecione **Editar** na linha do registro MX.</span><span class="sxs-lookup"><span data-stu-id="8bbae-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Selecionar Editar na linha do registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="8bbae-186">Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **Dados** e pressione a tecla **Delete** do teclado para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="8bbae-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="8bbae-187">Continue até excluir a entrada **Dados** para cada um dos outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="8bbae-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="8bbae-189">Quando você excluir a entrada **Dados** para cada um dos outros registros MX, selecione **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="8bbae-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Selecione Salvar.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8bbae-191">Adicionar os cinco registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bbae-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="8bbae-192">Para começar, vá até a [página Google Domains] (https://domains.google.com/registrar) e entre nela.</span><span class="sxs-lookup"><span data-stu-id="8bbae-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="8bbae-193">Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="8bbae-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8bbae-194">Adicionar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="8bbae-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="8bbae-195">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bbae-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="8bbae-196">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8bbae-197">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8bbae-198">**Name**</span><span class="sxs-lookup"><span data-stu-id="8bbae-198">**Name**</span></span>|<span data-ttu-id="8bbae-199">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8bbae-199">**Type**</span></span>|<span data-ttu-id="8bbae-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bbae-200">**TTL**</span></span>|<span data-ttu-id="8bbae-201">**Dados**</span><span class="sxs-lookup"><span data-stu-id="8bbae-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8bbae-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8bbae-202">autodiscover</span></span>  <br/> |<span data-ttu-id="8bbae-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="8bbae-203">CNAME</span></span>  <br/> |<span data-ttu-id="8bbae-204">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-204">1H</span></span>  <br/> |<span data-ttu-id="8bbae-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8bbae-206">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8bbae-207">sip</span><span class="sxs-lookup"><span data-stu-id="8bbae-207">sip</span></span>  <br/> |<span data-ttu-id="8bbae-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="8bbae-208">CNAME</span></span>  <br/> |<span data-ttu-id="8bbae-209">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-209">1H</span></span>  <br/> |<span data-ttu-id="8bbae-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8bbae-211">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8bbae-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8bbae-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8bbae-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="8bbae-213">CNAME</span></span>  <br/> |<span data-ttu-id="8bbae-214">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-214">1H</span></span>  <br/> |<span data-ttu-id="8bbae-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8bbae-216">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8bbae-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8bbae-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8bbae-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="8bbae-218">CNAME</span></span>  <br/> |<span data-ttu-id="8bbae-219">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-219">1H</span></span>  <br/> |<span data-ttu-id="8bbae-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8bbae-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="8bbae-221">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8bbae-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8bbae-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8bbae-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="8bbae-223">CNAME</span></span>  <br/> |<span data-ttu-id="8bbae-224">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-224">1H</span></span>  <br/> |<span data-ttu-id="8bbae-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="8bbae-226">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="8bbae-228">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-228">Select **Add**.</span></span>
    
    ![Selecionar Adicionar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="8bbae-230">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8bbae-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="8bbae-231">Na seção **Registros de recursos personalizados**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione novamente **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="8bbae-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="8bbae-232">Repita esse processo até ter criado todos os registros CNAME necessários.</span><span class="sxs-lookup"><span data-stu-id="8bbae-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8bbae-233">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="8bbae-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bbae-234">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="8bbae-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8bbae-235">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="8bbae-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8bbae-236">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bbae-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8bbae-237">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8bbae-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="8bbae-238">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="8bbae-238">Need examples?</span></span> <span data-ttu-id="8bbae-239">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="8bbae-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="8bbae-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8bbae-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="8bbae-p113">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="8bbae-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="8bbae-244">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="8bbae-245">Em seguida, insira suas credenciais de login e selecione novamente**Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="8bbae-246">Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="8bbae-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8bbae-247">Na seção **Registros de recursos personalizados**, na linha do registro TXT, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8bbae-p114">O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado**</span><span class="sxs-lookup"><span data-stu-id="8bbae-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selecionar Editar na linha do registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="8bbae-252">Selecione o controle **(+)**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-252">Select the **(+)** control.</span></span> 
    
    ![Selecionar o controle de adição](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="8bbae-254">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="8bbae-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8bbae-255">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="8bbae-256">**Dados**</span><span class="sxs-lookup"><span data-stu-id="8bbae-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="8bbae-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8bbae-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="8bbae-258">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="8bbae-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="8bbae-260">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-260">Select **Save**.</span></span>
    
    ![Selecione Salvar.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8bbae-262">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bbae-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8bbae-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8bbae-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="8bbae-p115">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="8bbae-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="8bbae-267">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="8bbae-268">Em seguida, insira suas credenciais de login e selecione novamente**Entrar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="8bbae-269">Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="8bbae-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="8bbae-270">Adicione o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="8bbae-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="8bbae-271">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bbae-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8bbae-272">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8bbae-273">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="8bbae-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8bbae-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="8bbae-274">**Name**</span></span>|<span data-ttu-id="8bbae-275">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8bbae-275">**Type**</span></span>|<span data-ttu-id="8bbae-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bbae-276">**TTL**</span></span>|<span data-ttu-id="8bbae-277">**Dados**</span><span class="sxs-lookup"><span data-stu-id="8bbae-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8bbae-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8bbae-278">_sip._tls</span></span>|<span data-ttu-id="8bbae-279">SRV</span><span class="sxs-lookup"><span data-stu-id="8bbae-279">SRV</span></span>|<span data-ttu-id="8bbae-280">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-280">1H</span></span>|<span data-ttu-id="8bbae-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="8bbae-282">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="8bbae-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="8bbae-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8bbae-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="8bbae-284">SRV</span><span class="sxs-lookup"><span data-stu-id="8bbae-284">SRV</span></span>|<span data-ttu-id="8bbae-285">1H</span><span class="sxs-lookup"><span data-stu-id="8bbae-285">1H</span></span>|<span data-ttu-id="8bbae-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8bbae-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="8bbae-287">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="8bbae-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="8bbae-288">É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="8bbae-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="8bbae-290">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8bbae-290">Select **Add**.</span></span>
    
    ![Selecionar Adicionar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="8bbae-292">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="8bbae-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="8bbae-293">Na seção **Registros de recursos personalizados**, crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione novamente **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="8bbae-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8bbae-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8bbae-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8bbae-295">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8bbae-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8bbae-296">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bbae-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
