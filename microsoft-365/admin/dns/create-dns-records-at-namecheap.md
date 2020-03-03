---
title: Criar registros DNS no Namecheap para o Office 365
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Namecheap para o Office 365.
ms.openlocfilehash: 26b8b6586c71636d97c423106e4799105a076a54
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348392"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a><span data-ttu-id="a6848-103">Criar registros DNS no Namecheap para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a6848-103">Create DNS records at Namecheap for Office 365</span></span>

 <span data-ttu-id="a6848-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a6848-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a6848-105">Se o Namecheap for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a6848-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a6848-106">Depois que você adicionar esses registros no Namecheap, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6848-106">After you add these records at Namecheap, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6848-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a6848-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a6848-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a6848-110">Add a TXT record for verification</span></span>
<span data-ttu-id="a6848-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a6848-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a6848-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="a6848-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6848-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="a6848-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a6848-116">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a6848-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a6848-117">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a6848-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a6848-118">Você será solicitado a entrar e continuar.</span><span class="sxs-lookup"><span data-stu-id="a6848-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a6848-120">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6848-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a6848-122">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a6848-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a6848-124">Selecione **DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="a6848-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a6848-126">Na seção **registros de host** , selecione **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a6848-128">Na lista suspensa **tipo** , selecione **registro txt**.</span><span class="sxs-lookup"><span data-stu-id="a6848-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6848-129">O menu suspenso **tipo** aparece automaticamente quando você seleciona **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="a6848-131">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a6848-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a6848-132">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a6848-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a6848-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a6848-133">**Type**</span></span>|<span data-ttu-id="a6848-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="a6848-134">**Host**</span></span>|<span data-ttu-id="a6848-135">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a6848-135">**Value**</span></span>|<span data-ttu-id="a6848-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a6848-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a6848-137">TXT</span><span class="sxs-lookup"><span data-stu-id="a6848-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a6848-138">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a6848-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="a6848-139">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a6848-139">**Note:** This is an example.</span></span> <span data-ttu-id="a6848-140">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6848-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="a6848-141">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a6848-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a6848-142">30 min</span><span class="sxs-lookup"><span data-stu-id="a6848-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="a6848-144">Selecione o controle **salvar alterações** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a6848-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="a6848-146">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="a6848-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a6848-147">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="a6848-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a6848-148">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="a6848-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a6848-149">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="a6848-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a6848-150">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="a6848-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a6848-151">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="a6848-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a6848-152">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a6848-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="a6848-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a6848-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a6848-156">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a6848-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a6848-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a6848-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a6848-158">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a6848-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a6848-159">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a6848-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a6848-160">Você será solicitado a entrar e continuar.</span><span class="sxs-lookup"><span data-stu-id="a6848-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a6848-162">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6848-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a6848-164">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a6848-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a6848-166">Selecione **DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="a6848-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a6848-168">Na seção **configurações de email** , selecione **MX personalizado** na lista suspensa **encaminhamento de email** .</span><span class="sxs-lookup"><span data-stu-id="a6848-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="a6848-169">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a6848-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="a6848-171">Selecione **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="a6848-173">Nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6848-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="a6848-174">(A caixa **prioridade** é a caixa sem nome à direita da caixa **valor** .</span><span class="sxs-lookup"><span data-stu-id="a6848-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="a6848-175">Escolha o valor **TTL** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6848-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a6848-176">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a6848-176">**Type**</span></span>|<span data-ttu-id="a6848-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="a6848-177">**Host**</span></span>|<span data-ttu-id="a6848-178">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a6848-178">**Value**</span></span>|<span data-ttu-id="a6848-179">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a6848-179">**Priority**</span></span>|<span data-ttu-id="a6848-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a6848-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a6848-181">Registro MX</span><span class="sxs-lookup"><span data-stu-id="a6848-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="a6848-182">\<*Domain-Key*\>. mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a6848-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a6848-184">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6848-184">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="a6848-185">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="a6848-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a6848-186">,0</span><span class="sxs-lookup"><span data-stu-id="a6848-186">0</span></span>  <br/> <span data-ttu-id="a6848-187">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6848-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="a6848-188">30 min</span><span class="sxs-lookup"><span data-stu-id="a6848-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="a6848-190">Selecione o controle **salvar alterações** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a6848-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="a6848-192">Se houver outros registros MX, use o processo de duas etapas a seguir para remover cada um deles:</span><span class="sxs-lookup"><span data-stu-id="a6848-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="a6848-193">Primeiro, selecione o **ícone Excluir** (lixeira) para o registro que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="a6848-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="a6848-195">Em segundo lugar, selecione **Sim** para confirmar a exclusão.</span><span class="sxs-lookup"><span data-stu-id="a6848-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="a6848-197">Remova todos os registros MX, exceto aquele que você adicionou anteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a6848-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a6848-198">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a6848-198">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a6848-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a6848-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a6848-200">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a6848-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a6848-201">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a6848-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a6848-202">Você será solicitado a entrar e continuar.</span><span class="sxs-lookup"><span data-stu-id="a6848-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a6848-204">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6848-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a6848-206">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a6848-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a6848-208">Selecione **DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="a6848-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a6848-210">Na seção **registros de host** , selecione **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a6848-212">Na lista suspensa **tipo** , selecione **registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="a6848-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6848-213">O menu suspenso **tipo** aparece automaticamente quando você seleciona **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="a6848-215">Nas caixas vazias do novo registro, selecione **CNAME** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6848-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a6848-216">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a6848-216">**Type**</span></span>|<span data-ttu-id="a6848-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="a6848-217">**Host**</span></span>|<span data-ttu-id="a6848-218">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a6848-218">**Value**</span></span>|<span data-ttu-id="a6848-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a6848-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a6848-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6848-220">CNAME</span></span>  <br/> |<span data-ttu-id="a6848-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a6848-221">autodiscover</span></span>  <br/> |<span data-ttu-id="a6848-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a6848-223">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-224">3600</span><span class="sxs-lookup"><span data-stu-id="a6848-224">3600</span></span>  <br/> |
    |<span data-ttu-id="a6848-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6848-225">CNAME</span></span>  <br/> |<span data-ttu-id="a6848-226">sip</span><span class="sxs-lookup"><span data-stu-id="a6848-226">sip</span></span>  <br/> |<span data-ttu-id="a6848-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a6848-228">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-229">3600</span><span class="sxs-lookup"><span data-stu-id="a6848-229">3600</span></span>  <br/> |
    |<span data-ttu-id="a6848-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6848-230">CNAME</span></span>  <br/> |<span data-ttu-id="a6848-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a6848-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a6848-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a6848-233">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-234">3600</span><span class="sxs-lookup"><span data-stu-id="a6848-234">3600</span></span>  <br/> |
    |<span data-ttu-id="a6848-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6848-235">CNAME</span></span>  <br/> |<span data-ttu-id="a6848-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a6848-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a6848-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a6848-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="a6848-238">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-239">3600</span><span class="sxs-lookup"><span data-stu-id="a6848-239">3600</span></span>  <br/> |
    |<span data-ttu-id="a6848-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="a6848-240">CNAME</span></span>  <br/> |<span data-ttu-id="a6848-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a6848-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a6848-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="a6848-243">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-244">3600</span><span class="sxs-lookup"><span data-stu-id="a6848-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="a6848-246">Selecione o controle **salvar alterações** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a6848-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="a6848-248">Usando as quatro etapas anteriores e os valores das outras cinco linhas na tabela, adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="a6848-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a6848-249">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="a6848-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a6848-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a6848-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6848-251">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="a6848-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a6848-252">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="a6848-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a6848-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6848-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a6848-254">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a6848-254">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="a6848-255">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a6848-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a6848-256">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a6848-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a6848-257">Você será solicitado a entrar e continuar.</span><span class="sxs-lookup"><span data-stu-id="a6848-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="a6848-258">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6848-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a6848-260">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a6848-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a6848-262">Selecione **DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="a6848-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a6848-264">Na seção **registros de host** , selecione **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a6848-266">Na lista suspensa **tipo** , selecione **registro txt**.</span><span class="sxs-lookup"><span data-stu-id="a6848-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6848-267">O menu suspenso **tipo** aparece automaticamente quando você seleciona **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="a6848-269">Nas caixas do novo registro, digite ou copie e cole os seguintes valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6848-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="a6848-270">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a6848-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a6848-271">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a6848-271">**Type**</span></span>|<span data-ttu-id="a6848-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="a6848-272">**Host**</span></span>|<span data-ttu-id="a6848-273">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a6848-273">**Value**</span></span>|<span data-ttu-id="a6848-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a6848-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a6848-275">TXT</span><span class="sxs-lookup"><span data-stu-id="a6848-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a6848-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a6848-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a6848-277">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="a6848-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a6848-278">30 min</span><span class="sxs-lookup"><span data-stu-id="a6848-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="a6848-280">Selecione o controle **salvar alterações** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a6848-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a6848-282">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="a6848-282">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a6848-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a6848-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a6848-284">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a6848-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a6848-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="a6848-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a6848-287">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6848-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a6848-289">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a6848-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a6848-291">Selecione **DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="a6848-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a6848-293">Na seção **registros de host** , selecione **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a6848-295">Na lista suspensa **tipo** , selecione **registro SRV**.</span><span class="sxs-lookup"><span data-stu-id="a6848-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6848-296">O menu suspenso **tipo** aparece automaticamente quando você seleciona **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a6848-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="a6848-298">Nas caixas vazias dos novos registros, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6848-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a6848-299">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="a6848-299">**Service**</span></span>|<span data-ttu-id="a6848-300">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="a6848-300">**Protocol**</span></span>|<span data-ttu-id="a6848-301">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a6848-301">**Priority**</span></span>|<span data-ttu-id="a6848-302">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="a6848-302">**Weight**</span></span>|<span data-ttu-id="a6848-303">**Porta**</span><span class="sxs-lookup"><span data-stu-id="a6848-303">**Port**</span></span>|<span data-ttu-id="a6848-304">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a6848-304">**Target**</span></span>|<span data-ttu-id="a6848-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a6848-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a6848-306">_sip</span><span class="sxs-lookup"><span data-stu-id="a6848-306">_sip</span></span>  <br/> |<span data-ttu-id="a6848-307">_tls</span><span class="sxs-lookup"><span data-stu-id="a6848-307">_tls</span></span>  <br/> |<span data-ttu-id="a6848-308">100</span><span class="sxs-lookup"><span data-stu-id="a6848-308">100</span></span>  <br/> |<span data-ttu-id="a6848-309">1</span><span class="sxs-lookup"><span data-stu-id="a6848-309">1</span></span>  <br/> |<span data-ttu-id="a6848-310">443</span><span class="sxs-lookup"><span data-stu-id="a6848-310">443</span></span>  <br/> |<span data-ttu-id="a6848-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a6848-312">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-313">30 min</span><span class="sxs-lookup"><span data-stu-id="a6848-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="a6848-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a6848-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a6848-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="a6848-315">_tcp</span></span>  <br/> |<span data-ttu-id="a6848-316">100</span><span class="sxs-lookup"><span data-stu-id="a6848-316">100</span></span>  <br/> |<span data-ttu-id="a6848-317">1</span><span class="sxs-lookup"><span data-stu-id="a6848-317">1</span></span>  <br/> |<span data-ttu-id="a6848-318">5061</span><span class="sxs-lookup"><span data-stu-id="a6848-318">5061</span></span>  <br/> |<span data-ttu-id="a6848-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a6848-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a6848-320">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="a6848-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a6848-321">30 min</span><span class="sxs-lookup"><span data-stu-id="a6848-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="a6848-323">Selecione o controle **salvar alterações** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a6848-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="a6848-325">Usando as quatro etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="a6848-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a6848-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a6848-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
