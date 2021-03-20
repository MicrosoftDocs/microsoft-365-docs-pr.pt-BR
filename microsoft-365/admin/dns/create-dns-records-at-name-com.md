---
title: Criar registros DNS no name.com para a Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços name.com para a Microsoft.
ms.openlocfilehash: 97cc83fe060f8fbfe78decff584bded3102b09b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910169"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="10b3f-103">Criar registros DNS no name.com para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="10b3f-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="10b3f-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="10b3f-105">Se você usa a name.com como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="10b3f-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="10b3f-106">Depois de adicionar esses registros name.com, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10b3f-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="10b3f-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10b3f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="10b3f-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="10b3f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="10b3f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="10b3f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="10b3f-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10b3f-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="10b3f-p104">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10b3f-119">Em **Meus Domínios,** selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="10b3f-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10b3f-121">Na coluna **Detalhes,** selecione **Registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10b3f-123">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="10b3f-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="10b3f-124">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b3f-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10b3f-125">**Type**</span></span> <br/> |<span data-ttu-id="10b3f-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="10b3f-126">**Host**</span></span> <br/> |<span data-ttu-id="10b3f-127">**Atender**</span><span class="sxs-lookup"><span data-stu-id="10b3f-127">**Answer**</span></span> <br/> |<span data-ttu-id="10b3f-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b3f-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="10b3f-129">TXT</span><span class="sxs-lookup"><span data-stu-id="10b3f-129">TXT</span></span>  <br/> |<span data-ttu-id="10b3f-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10b3f-131">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="10b3f-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="10b3f-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="10b3f-132">**Note:** This is an example.</span></span> <span data-ttu-id="10b3f-133">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="10b3f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="10b3f-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="10b3f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="10b3f-135">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-135">Use the default value (300).</span></span>  <br/> |
   
    ![Nome-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="10b3f-137">Selecione **Adicionar Registro**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="10b3f-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="10b3f-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="10b3f-140">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="10b3f-141">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="10b3f-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="10b3f-142">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="10b3f-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="10b3f-143">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="10b3f-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="10b3f-144">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="10b3f-145">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="10b3f-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10b3f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="10b3f-149">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10b3f-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="10b3f-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="10b3f-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="10b3f-p107">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10b3f-154">Em **Meus Domínios,** selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="10b3f-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10b3f-156">Na coluna **Detalhes,** selecione **Registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10b3f-158">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="10b3f-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="10b3f-159">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10b3f-160">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10b3f-160">**Type**</span></span>|<span data-ttu-id="10b3f-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="10b3f-161">**Host**</span></span>|<span data-ttu-id="10b3f-162">**Atender**</span><span class="sxs-lookup"><span data-stu-id="10b3f-162">**Answer**</span></span>|<span data-ttu-id="10b3f-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b3f-163">**TTL**</span></span>|<span data-ttu-id="10b3f-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="10b3f-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b3f-165">MX</span><span class="sxs-lookup"><span data-stu-id="10b3f-165">MX</span></span>  <br/> |<span data-ttu-id="10b3f-166">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="10b3f-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="10b3f-168">**Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10b3f-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="10b3f-169">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="10b3f-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="10b3f-170">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="10b3f-171">0</span><span class="sxs-lookup"><span data-stu-id="10b3f-171">0</span></span>  <br/> <span data-ttu-id="10b3f-172">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="10b3f-172">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="10b3f-174">Selecione **Adicionar Registro**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="10b3f-176">Se houver outros registros MX, exclua cada um deles, usando o procedimento de duas etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="10b3f-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="10b3f-177">Para um registro MX, selecione **Excluir** na **coluna Ações.**</span><span class="sxs-lookup"><span data-stu-id="10b3f-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="10b3f-179">Para confirmar cada exclusão, selecione **Excluir** na **coluna Ações** novamente.</span><span class="sxs-lookup"><span data-stu-id="10b3f-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="10b3f-181">Repita esse procedimento de duas etapas até ter excluído todos os registros MX.</span><span class="sxs-lookup"><span data-stu-id="10b3f-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="10b3f-182">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="10b3f-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="10b3f-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="10b3f-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="10b3f-p109">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10b3f-187">Em **Meus Domínios,** selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="10b3f-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10b3f-189">Na coluna **Detalhes,** selecione **Registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10b3f-191">Adicionar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="10b3f-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="10b3f-192">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="10b3f-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="10b3f-193">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10b3f-194">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10b3f-194">**Type**</span></span>|<span data-ttu-id="10b3f-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="10b3f-195">**Host**</span></span>|<span data-ttu-id="10b3f-196">**Atender**</span><span class="sxs-lookup"><span data-stu-id="10b3f-196">**Answer**</span></span>|<span data-ttu-id="10b3f-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b3f-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b3f-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b3f-198">CNAME</span></span>  <br/> |<span data-ttu-id="10b3f-199">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="10b3f-199">autodiscover</span></span>  <br/> |<span data-ttu-id="10b3f-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="10b3f-201">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10b3f-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b3f-202">CNAME</span></span>  <br/> |<span data-ttu-id="10b3f-203">sip</span><span class="sxs-lookup"><span data-stu-id="10b3f-203">sip</span></span>  <br/> |<span data-ttu-id="10b3f-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="10b3f-205">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10b3f-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b3f-206">CNAME</span></span>  <br/> |<span data-ttu-id="10b3f-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="10b3f-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="10b3f-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="10b3f-209">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10b3f-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b3f-210">CNAME</span></span>  <br/> |<span data-ttu-id="10b3f-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="10b3f-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="10b3f-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="10b3f-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="10b3f-213">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10b3f-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="10b3f-214">CNAME</span></span>  <br/> |<span data-ttu-id="10b3f-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="10b3f-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="10b3f-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="10b3f-217">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="10b3f-219">Selecione **Adicionar Registro** para adicionar o primeiro registro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="10b3f-221">Adicione o segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="10b3f-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="10b3f-222">Use os valores da segunda linha da tabela acima e selecione **Adicionar Registro** para adicionar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="10b3f-223">Adicione os registros restantes da mesma maneira, usando os valores da terceira, quarta, quinta e sexta linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="10b3f-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="10b3f-224">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="10b3f-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="10b3f-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="10b3f-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="10b3f-226">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="10b3f-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="10b3f-227">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="10b3f-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="10b3f-228">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10b3f-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="10b3f-229">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="10b3f-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="10b3f-p111">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10b3f-233">Em **Meus Domínios,** selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="10b3f-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10b3f-235">Na coluna **Detalhes,** selecione **Registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10b3f-237">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="10b3f-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="10b3f-238">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10b3f-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10b3f-239">**Type**</span></span>|<span data-ttu-id="10b3f-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="10b3f-240">**Host**</span></span>|<span data-ttu-id="10b3f-241">**Atender**</span><span class="sxs-lookup"><span data-stu-id="10b3f-241">**Answer**</span></span>|<span data-ttu-id="10b3f-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b3f-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b3f-243">TXT</span><span class="sxs-lookup"><span data-stu-id="10b3f-243">TXT</span></span>  <br/> |<span data-ttu-id="10b3f-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10b3f-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="10b3f-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="10b3f-246">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="10b3f-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="10b3f-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="10b3f-249">Selecione **Adicionar Registro**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="10b3f-251">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="10b3f-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="10b3f-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="10b3f-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="10b3f-p112">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10b3f-256">Em **Meus Domínios,** selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="10b3f-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10b3f-258">Na coluna **Detalhes,** selecione **Registros DNS+**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10b3f-260">Adicione o primeiro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="10b3f-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="10b3f-261">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="10b3f-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="10b3f-262">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="10b3f-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10b3f-263">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10b3f-263">**Type**</span></span>|<span data-ttu-id="10b3f-264">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="10b3f-264">**Service**</span></span>|<span data-ttu-id="10b3f-265">**Peso**</span><span class="sxs-lookup"><span data-stu-id="10b3f-265">**Weight**</span></span>|<span data-ttu-id="10b3f-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10b3f-266">**TTL**</span></span>|<span data-ttu-id="10b3f-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="10b3f-267">**Prio**</span></span>|<span data-ttu-id="10b3f-268">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="10b3f-268">**Protocol**</span></span>|<span data-ttu-id="10b3f-269">**Porta**</span><span class="sxs-lookup"><span data-stu-id="10b3f-269">**Port**</span></span>|<span data-ttu-id="10b3f-270">**Destino**</span><span class="sxs-lookup"><span data-stu-id="10b3f-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10b3f-271">SRV</span><span class="sxs-lookup"><span data-stu-id="10b3f-271">SRV</span></span>|<span data-ttu-id="10b3f-272">sip</span><span class="sxs-lookup"><span data-stu-id="10b3f-272">sip</span></span>|<span data-ttu-id="10b3f-273">1</span><span class="sxs-lookup"><span data-stu-id="10b3f-273">1</span></span>|<span data-ttu-id="10b3f-274">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-274">Use the default value (300).</span></span>|<span data-ttu-id="10b3f-275">100</span><span class="sxs-lookup"><span data-stu-id="10b3f-275">100</span></span>|<span data-ttu-id="10b3f-276">tls</span><span class="sxs-lookup"><span data-stu-id="10b3f-276">tls</span></span>|<span data-ttu-id="10b3f-277">443</span><span class="sxs-lookup"><span data-stu-id="10b3f-277">443</span></span>|<span data-ttu-id="10b3f-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="10b3f-279">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="10b3f-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="10b3f-280">SRV</span><span class="sxs-lookup"><span data-stu-id="10b3f-280">SRV</span></span>|<span data-ttu-id="10b3f-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="10b3f-281">sipfederationtls</span></span>|<span data-ttu-id="10b3f-282">1</span><span class="sxs-lookup"><span data-stu-id="10b3f-282">1</span></span>|<span data-ttu-id="10b3f-283">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="10b3f-283">Use the default value (300).</span></span>|<span data-ttu-id="10b3f-284">100</span><span class="sxs-lookup"><span data-stu-id="10b3f-284">100</span></span>|<span data-ttu-id="10b3f-285">tcp</span><span class="sxs-lookup"><span data-stu-id="10b3f-285">tcp</span></span>|<span data-ttu-id="10b3f-286">5061</span><span class="sxs-lookup"><span data-stu-id="10b3f-286">5061</span></span>|<span data-ttu-id="10b3f-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10b3f-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="10b3f-288">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="10b3f-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="10b3f-290">Selecione **Adicionar Registro**.</span><span class="sxs-lookup"><span data-stu-id="10b3f-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="10b3f-292">Adicione o segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="10b3f-292">Add the second SRV record:</span></span>

<span data-ttu-id="10b3f-293">Use os valores da próxima linha da tabela acima e selecione **Adicionar Registro** para adicionar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="10b3f-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="10b3f-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10b3f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>