---
title: Criar registros DNS no site name.com para o Office 365
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em name.com para o Office 365.
ms.openlocfilehash: f21a40f543ff3a9faffe6ffba98f4d541b2a7a7b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349968"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="a78c5-103">Criar registros DNS no site name.com para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a78c5-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="a78c5-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a78c5-105">Se você usa a name.com como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="a78c5-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a78c5-106">Depois que você adicionar esses registros na name.com, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a78c5-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a78c5-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a78c5-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a78c5-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a78c5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a78c5-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a78c5-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a78c5-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a78c5-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a78c5-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a78c5-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a78c5-p104">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a78c5-120">Em **meus domínios**, selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a78c5-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a78c5-122">Na coluna **detalhes** , selecione \* \* registros DNS \* \*.</span><span class="sxs-lookup"><span data-stu-id="a78c5-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a78c5-124">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a78c5-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a78c5-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a78c5-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a78c5-126">**Type**</span></span> <br/> |<span data-ttu-id="a78c5-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="a78c5-127">**Host**</span></span> <br/> |<span data-ttu-id="a78c5-128">**Atender**</span><span class="sxs-lookup"><span data-stu-id="a78c5-128">**Answer**</span></span> <br/> |<span data-ttu-id="a78c5-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a78c5-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="a78c5-130">TXT</span><span class="sxs-lookup"><span data-stu-id="a78c5-130">TXT</span></span>  <br/> |<span data-ttu-id="a78c5-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a78c5-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a78c5-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a78c5-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a78c5-133">**Note:** This is an example.</span></span> <span data-ttu-id="a78c5-134">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a78c5-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="a78c5-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a78c5-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a78c5-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-136">Use the default value (300).</span></span>  <br/> |
   
    ![Nome-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="a78c5-138">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="a78c5-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="a78c5-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a78c5-141">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a78c5-142">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="a78c5-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a78c5-143">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="a78c5-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a78c5-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="a78c5-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a78c5-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a78c5-146">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="a78c5-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a78c5-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a78c5-150">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a78c5-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a78c5-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a78c5-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a78c5-p107">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a78c5-155">Em **meus domínios**, selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a78c5-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a78c5-157">Na coluna **detalhes** , selecione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a78c5-159">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a78c5-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a78c5-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a78c5-161">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a78c5-161">**Type**</span></span>|<span data-ttu-id="a78c5-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="a78c5-162">**Host**</span></span>|<span data-ttu-id="a78c5-163">**Atender**</span><span class="sxs-lookup"><span data-stu-id="a78c5-163">**Answer**</span></span>|<span data-ttu-id="a78c5-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a78c5-164">**TTL**</span></span>|<span data-ttu-id="a78c5-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="a78c5-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a78c5-166">MX</span><span class="sxs-lookup"><span data-stu-id="a78c5-166">MX</span></span>  <br/> |<span data-ttu-id="a78c5-167">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="a78c5-168">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a78c5-169">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a78c5-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="a78c5-170">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="a78c5-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a78c5-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="a78c5-172">,0</span><span class="sxs-lookup"><span data-stu-id="a78c5-172">0</span></span>  <br/> <span data-ttu-id="a78c5-173">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a78c5-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="a78c5-175">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="a78c5-177">Se houver outros registros MX, exclua cada um deles, usando o procedimento de duas etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="a78c5-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="a78c5-178">Para cada registro MX, selecione **excluir** na coluna **ações** .</span><span class="sxs-lookup"><span data-stu-id="a78c5-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="a78c5-180">Para confirmar cada exclusão, selecione **excluir** na coluna **ações** novamente.</span><span class="sxs-lookup"><span data-stu-id="a78c5-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="a78c5-182">Repita esse procedimento de duas etapas até ter excluído todos os registros MX.</span><span class="sxs-lookup"><span data-stu-id="a78c5-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a78c5-183">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="a78c5-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a78c5-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a78c5-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a78c5-p109">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a78c5-188">Em **meus domínios**, selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a78c5-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a78c5-190">Na coluna **detalhes** , selecione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a78c5-192">Adicionar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="a78c5-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="a78c5-193">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a78c5-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="a78c5-194">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a78c5-195">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a78c5-195">**Type**</span></span>|<span data-ttu-id="a78c5-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="a78c5-196">**Host**</span></span>|<span data-ttu-id="a78c5-197">**Atender**</span><span class="sxs-lookup"><span data-stu-id="a78c5-197">**Answer**</span></span>|<span data-ttu-id="a78c5-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a78c5-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a78c5-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a78c5-199">CNAME</span></span>  <br/> |<span data-ttu-id="a78c5-200">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="a78c5-200">autodiscover</span></span>  <br/> |<span data-ttu-id="a78c5-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a78c5-202">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a78c5-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="a78c5-203">CNAME</span></span>  <br/> |<span data-ttu-id="a78c5-204">sip</span><span class="sxs-lookup"><span data-stu-id="a78c5-204">sip</span></span>  <br/> |<span data-ttu-id="a78c5-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a78c5-206">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a78c5-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="a78c5-207">CNAME</span></span>  <br/> |<span data-ttu-id="a78c5-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a78c5-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a78c5-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a78c5-210">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a78c5-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a78c5-211">CNAME</span></span>  <br/> |<span data-ttu-id="a78c5-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a78c5-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a78c5-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a78c5-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a78c5-214">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="a78c5-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="a78c5-215">CNAME</span></span>  <br/> |<span data-ttu-id="a78c5-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a78c5-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a78c5-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a78c5-218">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="a78c5-220">Selecione **adicionar registro** para adicionar o primeiro registro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="a78c5-222">Adicione o segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="a78c5-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="a78c5-223">Use os valores da segunda linha da tabela acima e, em seguida, selecione **adicionar registro** para adicionar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="a78c5-224">Adicione os registros restantes da mesma maneira, usando os valores da terceira, quarta, quinta e sexta linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="a78c5-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a78c5-225">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="a78c5-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a78c5-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a78c5-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a78c5-227">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="a78c5-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a78c5-228">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="a78c5-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a78c5-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a78c5-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a78c5-230">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a78c5-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a78c5-p111">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a78c5-234">Em **meus domínios**, selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a78c5-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a78c5-236">Na coluna **detalhes** , selecione **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a78c5-238">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a78c5-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a78c5-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a78c5-240">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a78c5-240">**Type**</span></span>|<span data-ttu-id="a78c5-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="a78c5-241">**Host**</span></span>|<span data-ttu-id="a78c5-242">**Atender**</span><span class="sxs-lookup"><span data-stu-id="a78c5-242">**Answer**</span></span>|<span data-ttu-id="a78c5-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a78c5-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a78c5-244">TXT</span><span class="sxs-lookup"><span data-stu-id="a78c5-244">TXT</span></span>  <br/> |<span data-ttu-id="a78c5-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a78c5-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a78c5-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a78c5-247">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a78c5-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a78c5-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="a78c5-250">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a78c5-252">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="a78c5-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a78c5-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a78c5-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a78c5-p112">Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="a78c5-257">Em **meus domínios**, selecione o nome do domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a78c5-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="a78c5-259">Na coluna **detalhes** , selecione **registros DNS +**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="a78c5-261">Adicione o primeiro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="a78c5-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="a78c5-262">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a78c5-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="a78c5-263">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a78c5-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a78c5-264">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a78c5-264">**Type**</span></span>|<span data-ttu-id="a78c5-265">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="a78c5-265">**Service**</span></span>|<span data-ttu-id="a78c5-266">**Peso**</span><span class="sxs-lookup"><span data-stu-id="a78c5-266">**Weight**</span></span>|<span data-ttu-id="a78c5-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a78c5-267">**TTL**</span></span>|<span data-ttu-id="a78c5-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="a78c5-268">**Prio**</span></span>|<span data-ttu-id="a78c5-269">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="a78c5-269">**Protocol**</span></span>|<span data-ttu-id="a78c5-270">**Porta**</span><span class="sxs-lookup"><span data-stu-id="a78c5-270">**Port**</span></span>|<span data-ttu-id="a78c5-271">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a78c5-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a78c5-272">SRV</span><span class="sxs-lookup"><span data-stu-id="a78c5-272">SRV</span></span>|<span data-ttu-id="a78c5-273">sip</span><span class="sxs-lookup"><span data-stu-id="a78c5-273">sip</span></span>|<span data-ttu-id="a78c5-274">1</span><span class="sxs-lookup"><span data-stu-id="a78c5-274">1</span></span>|<span data-ttu-id="a78c5-275">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-275">Use the default value (300).</span></span>|<span data-ttu-id="a78c5-276">100</span><span class="sxs-lookup"><span data-stu-id="a78c5-276">100</span></span>|<span data-ttu-id="a78c5-277">tls</span><span class="sxs-lookup"><span data-stu-id="a78c5-277">tls</span></span>|<span data-ttu-id="a78c5-278">443</span><span class="sxs-lookup"><span data-stu-id="a78c5-278">443</span></span>|<span data-ttu-id="a78c5-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="a78c5-280">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a78c5-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="a78c5-281">SRV</span><span class="sxs-lookup"><span data-stu-id="a78c5-281">SRV</span></span>|<span data-ttu-id="a78c5-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a78c5-282">sipfederationtls</span></span>|<span data-ttu-id="a78c5-283">1</span><span class="sxs-lookup"><span data-stu-id="a78c5-283">1</span></span>|<span data-ttu-id="a78c5-284">Use o valor padrão (300).</span><span class="sxs-lookup"><span data-stu-id="a78c5-284">Use the default value (300).</span></span>|<span data-ttu-id="a78c5-285">100</span><span class="sxs-lookup"><span data-stu-id="a78c5-285">100</span></span>|<span data-ttu-id="a78c5-286">tcp</span><span class="sxs-lookup"><span data-stu-id="a78c5-286">tcp</span></span>|<span data-ttu-id="a78c5-287">5061</span><span class="sxs-lookup"><span data-stu-id="a78c5-287">5061</span></span>|<span data-ttu-id="a78c5-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a78c5-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="a78c5-289">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a78c5-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="a78c5-291">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="a78c5-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="a78c5-293">Adicione o segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="a78c5-293">Add the second SRV record:</span></span>

<span data-ttu-id="a78c5-294">Use os valores da próxima linha da tabela acima e, em seguida, selecione **adicionar registro** para adicionar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="a78c5-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="a78c5-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a78c5-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
