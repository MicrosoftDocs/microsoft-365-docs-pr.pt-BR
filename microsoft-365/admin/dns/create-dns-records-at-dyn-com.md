---
title: Criar registros DNS no Dyn.com para Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Dyn.com para a Microsoft.
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629582"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="7651a-103">Criar registros DNS no Dyn.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="7651a-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="7651a-104">**[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7651a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7651a-105">Se você usa a Dyn.com como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="7651a-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="7651a-106">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="7651a-106">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7651a-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7651a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7651a-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="7651a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7651a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7651a-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="7651a-p102">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7651a-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7651a-115">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7651a-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7651a-116">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="7651a-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7651a-117">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="7651a-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7651a-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7651a-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7651a-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7651a-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7651a-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="7651a-120">**Host**</span></span>|<span data-ttu-id="7651a-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7651a-121">**TTL**</span></span>|<span data-ttu-id="7651a-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7651a-122">**Type**</span></span>|<span data-ttu-id="7651a-123">**Dados**</span><span class="sxs-lookup"><span data-stu-id="7651a-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7651a-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7651a-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7651a-125">600</span><span class="sxs-lookup"><span data-stu-id="7651a-125">600</span></span>  <br/> |<span data-ttu-id="7651a-126">TXT</span><span class="sxs-lookup"><span data-stu-id="7651a-126">TXT</span></span>  <br/> |<span data-ttu-id="7651a-127">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7651a-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7651a-128">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="7651a-128">**Note:** This is an example.</span></span> <span data-ttu-id="7651a-129">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="7651a-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7651a-130">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="7651a-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="7651a-132">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="7651a-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="7651a-134">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="7651a-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7651a-135">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="7651a-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7651a-136">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="7651a-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7651a-137">No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="7651a-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7651a-138">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="7651a-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7651a-139">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="7651a-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7651a-140">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="7651a-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7651a-p104">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7651a-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7651a-144">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7651a-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7651a-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7651a-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7651a-p105">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7651a-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7651a-149">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7651a-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7651a-150">Na página DNS do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="7651a-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7651a-151">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="7651a-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7651a-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7651a-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7651a-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7651a-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7651a-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="7651a-154">**Host**</span></span>|<span data-ttu-id="7651a-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7651a-155">**TTL**</span></span>|<span data-ttu-id="7651a-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7651a-156">**Type**</span></span>|<span data-ttu-id="7651a-157">**Dados**</span><span class="sxs-lookup"><span data-stu-id="7651a-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7651a-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7651a-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7651a-159">600</span><span class="sxs-lookup"><span data-stu-id="7651a-159">600</span></span>  <br/> |<span data-ttu-id="7651a-160">MX</span><span class="sxs-lookup"><span data-stu-id="7651a-160">MX</span></span>  <br/> |<span data-ttu-id="7651a-161">10  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7651a-162">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7651a-p106">O **10** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="7651a-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="7651a-165">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7651a-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="7651a-166">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="7651a-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="7651a-167">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="7651a-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="7651a-169">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="7651a-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="7651a-171">Caso haja outros registros MX, remova-os marcando a caixa de seleção de cada um na coluna **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7651a-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![flores e texto](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="7651a-173">Selecione **aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="7651a-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7651a-175">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="7651a-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7651a-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7651a-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7651a-p108">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7651a-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7651a-180">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7651a-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7651a-181">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="7651a-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7651a-182">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="7651a-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7651a-183">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7651a-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7651a-184">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7651a-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="7651a-185">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="7651a-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7651a-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="7651a-186">**Host**</span></span>|<span data-ttu-id="7651a-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7651a-187">**TTL**</span></span>|<span data-ttu-id="7651a-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7651a-188">**Type**</span></span>|<span data-ttu-id="7651a-189">**Dados**</span><span class="sxs-lookup"><span data-stu-id="7651a-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7651a-190">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="7651a-190">autodiscover</span></span>  <br/> |<span data-ttu-id="7651a-191">600</span><span class="sxs-lookup"><span data-stu-id="7651a-191">600</span></span>  <br/> |<span data-ttu-id="7651a-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="7651a-192">CNAME</span></span>  <br/> |<span data-ttu-id="7651a-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7651a-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7651a-195">sip</span><span class="sxs-lookup"><span data-stu-id="7651a-195">sip</span></span>  <br/> |<span data-ttu-id="7651a-196">600</span><span class="sxs-lookup"><span data-stu-id="7651a-196">600</span></span>  <br/> |<span data-ttu-id="7651a-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="7651a-197">CNAME</span></span>  <br/> |<span data-ttu-id="7651a-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7651a-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7651a-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7651a-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7651a-201">600</span><span class="sxs-lookup"><span data-stu-id="7651a-201">600</span></span>  <br/> |<span data-ttu-id="7651a-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="7651a-202">CNAME</span></span>  <br/> |<span data-ttu-id="7651a-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7651a-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7651a-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7651a-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7651a-206">600</span><span class="sxs-lookup"><span data-stu-id="7651a-206">600</span></span>  <br/> |<span data-ttu-id="7651a-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="7651a-207">CNAME</span></span>  <br/> |<span data-ttu-id="7651a-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7651a-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7651a-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7651a-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7651a-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7651a-211">600</span><span class="sxs-lookup"><span data-stu-id="7651a-211">600</span></span>  <br/> |<span data-ttu-id="7651a-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="7651a-212">CNAME</span></span>  <br/> |<span data-ttu-id="7651a-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7651a-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="7651a-216">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="7651a-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="7651a-218">Adicione os cinco registros CNAME restantes.</span><span class="sxs-lookup"><span data-stu-id="7651a-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="7651a-219">Na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="7651a-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="7651a-220">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7651a-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7651a-221">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="7651a-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7651a-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7651a-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7651a-223">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="7651a-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7651a-224">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="7651a-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7651a-225">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7651a-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7651a-226">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="7651a-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="7651a-p110">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7651a-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7651a-230">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7651a-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7651a-231">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="7651a-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7651a-232">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="7651a-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7651a-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7651a-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7651a-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7651a-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7651a-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="7651a-235">**Host**</span></span>|<span data-ttu-id="7651a-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7651a-236">**TTL**</span></span>|<span data-ttu-id="7651a-237">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7651a-237">**Type**</span></span>|<span data-ttu-id="7651a-238">**Dados**</span><span class="sxs-lookup"><span data-stu-id="7651a-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7651a-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7651a-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7651a-240">600</span><span class="sxs-lookup"><span data-stu-id="7651a-240">600</span></span>  <br/> |<span data-ttu-id="7651a-241">TXT</span><span class="sxs-lookup"><span data-stu-id="7651a-241">TXT</span></span>  <br/> |<span data-ttu-id="7651a-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7651a-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7651a-243">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="7651a-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="7651a-245">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="7651a-245">Select **Create Record**.</span></span>
    
    ![Campo de vários valores](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7651a-247">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="7651a-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7651a-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7651a-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7651a-249">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="7651a-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="7651a-250">Você será solicitado a fazer logon primeiro</span><span class="sxs-lookup"><span data-stu-id="7651a-250">You'll be prompted to login first</span></span> 
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="7651a-252">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="7651a-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7651a-253">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="7651a-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="7651a-254">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="7651a-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="7651a-255">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="7651a-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7651a-256">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7651a-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="7651a-257">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="7651a-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7651a-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="7651a-258">**Host**</span></span>|<span data-ttu-id="7651a-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7651a-259">**TTL**</span></span>|<span data-ttu-id="7651a-260">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7651a-260">**Type**</span></span>|<span data-ttu-id="7651a-261">**Dados**</span><span class="sxs-lookup"><span data-stu-id="7651a-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7651a-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="7651a-262">_sip._tls</span></span>|<span data-ttu-id="7651a-263">600</span><span class="sxs-lookup"><span data-stu-id="7651a-263">600</span></span>|<span data-ttu-id="7651a-264">SRV</span><span class="sxs-lookup"><span data-stu-id="7651a-264">SRV</span></span>|<span data-ttu-id="7651a-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="7651a-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="7651a-267">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="7651a-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="7651a-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="7651a-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7651a-269">600</span><span class="sxs-lookup"><span data-stu-id="7651a-269">600</span></span>|<span data-ttu-id="7651a-270">SRV</span><span class="sxs-lookup"><span data-stu-id="7651a-270">SRV</span></span>|<span data-ttu-id="7651a-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7651a-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="7651a-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7651a-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="7651a-273">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="7651a-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="7651a-275">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="7651a-275">Select **Create Record**.</span></span>
    
    ![configurar opções de vídeo](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="7651a-277">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="7651a-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7651a-278">Na seção **adicionar registro DNS** , crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="7651a-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="7651a-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7651a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
