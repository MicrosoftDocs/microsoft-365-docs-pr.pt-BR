---
title: Criar registros DNS no Dyn.com para o Office 365
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Dyn.com para o Office 365.
ms.openlocfilehash: d4471ec84555efb349cc1e42d5048ebf044735e5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238844"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="575e5-103">Criar registros DNS no Dyn.com para o Office 365</span><span class="sxs-lookup"><span data-stu-id="575e5-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="575e5-104">**[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="575e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="575e5-105">Se você usa a Dyn.com como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="575e5-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="575e5-106">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="575e5-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="575e5-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="575e5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="575e5-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="575e5-110">Add a TXT record for verification</span></span>
<span data-ttu-id="575e5-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="575e5-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="575e5-p102">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="575e5-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="575e5-115">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="575e5-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="575e5-116">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="575e5-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="575e5-117">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="575e5-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="575e5-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="575e5-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="575e5-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="575e5-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="575e5-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="575e5-120">**Host**</span></span>|<span data-ttu-id="575e5-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="575e5-121">**TTL**</span></span>|<span data-ttu-id="575e5-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="575e5-122">**Type**</span></span>|<span data-ttu-id="575e5-123">**Dados**</span><span class="sxs-lookup"><span data-stu-id="575e5-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="575e5-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="575e5-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="575e5-125">600</span><span class="sxs-lookup"><span data-stu-id="575e5-125">600</span></span>  <br/> |<span data-ttu-id="575e5-126">TXT</span><span class="sxs-lookup"><span data-stu-id="575e5-126">TXT</span></span>  <br/> |<span data-ttu-id="575e5-127">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="575e5-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="575e5-128">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="575e5-128">**Note:** This is an example.</span></span> <span data-ttu-id="575e5-129">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="575e5-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="575e5-130">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="575e5-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="575e5-132">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="575e5-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="575e5-134">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="575e5-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="575e5-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="575e5-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="575e5-136">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="575e5-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="575e5-137">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="575e5-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="575e5-138">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="575e5-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="575e5-139">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="575e5-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="575e5-140">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="575e5-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="575e5-p104">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="575e5-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="575e5-144">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="575e5-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="575e5-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="575e5-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="575e5-p105">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="575e5-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="575e5-149">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="575e5-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="575e5-150">Na página DNS do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="575e5-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="575e5-151">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="575e5-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="575e5-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="575e5-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="575e5-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="575e5-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="575e5-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="575e5-154">**Host**</span></span>|<span data-ttu-id="575e5-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="575e5-155">**TTL**</span></span>|<span data-ttu-id="575e5-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="575e5-156">**Type**</span></span>|<span data-ttu-id="575e5-157">**Dados**</span><span class="sxs-lookup"><span data-stu-id="575e5-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="575e5-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="575e5-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="575e5-159">600</span><span class="sxs-lookup"><span data-stu-id="575e5-159">600</span></span>  <br/> |<span data-ttu-id="575e5-160">MX</span><span class="sxs-lookup"><span data-stu-id="575e5-160">MX</span></span>  <br/> |<span data-ttu-id="575e5-161">10  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="575e5-162">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="575e5-p106">O **10** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="575e5-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="575e5-165">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="575e5-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="575e5-166">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="575e5-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="575e5-167">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="575e5-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="575e5-169">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="575e5-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="575e5-171">Caso haja outros registros MX, remova-os marcando a caixa de seleção de cada um na coluna **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="575e5-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![flores e texto](../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="575e5-173">Selecione **aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="575e5-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="575e5-175">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="575e5-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="575e5-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="575e5-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="575e5-p108">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="575e5-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="575e5-180">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="575e5-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="575e5-181">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="575e5-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="575e5-182">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="575e5-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="575e5-183">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="575e5-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="575e5-184">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="575e5-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="575e5-185">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="575e5-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="575e5-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="575e5-186">**Host**</span></span>|<span data-ttu-id="575e5-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="575e5-187">**TTL**</span></span>|<span data-ttu-id="575e5-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="575e5-188">**Type**</span></span>|<span data-ttu-id="575e5-189">**Dados**</span><span class="sxs-lookup"><span data-stu-id="575e5-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="575e5-190">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="575e5-190">autodiscover</span></span>  <br/> |<span data-ttu-id="575e5-191">600</span><span class="sxs-lookup"><span data-stu-id="575e5-191">600</span></span>  <br/> |<span data-ttu-id="575e5-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="575e5-192">CNAME</span></span>  <br/> |<span data-ttu-id="575e5-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="575e5-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="575e5-195">sip</span><span class="sxs-lookup"><span data-stu-id="575e5-195">sip</span></span>  <br/> |<span data-ttu-id="575e5-196">600</span><span class="sxs-lookup"><span data-stu-id="575e5-196">600</span></span>  <br/> |<span data-ttu-id="575e5-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="575e5-197">CNAME</span></span>  <br/> |<span data-ttu-id="575e5-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="575e5-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="575e5-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="575e5-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="575e5-201">600</span><span class="sxs-lookup"><span data-stu-id="575e5-201">600</span></span>  <br/> |<span data-ttu-id="575e5-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="575e5-202">CNAME</span></span>  <br/> |<span data-ttu-id="575e5-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="575e5-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="575e5-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="575e5-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="575e5-206">600</span><span class="sxs-lookup"><span data-stu-id="575e5-206">600</span></span>  <br/> |<span data-ttu-id="575e5-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="575e5-207">CNAME</span></span>  <br/> |<span data-ttu-id="575e5-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="575e5-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="575e5-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="575e5-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="575e5-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="575e5-211">600</span><span class="sxs-lookup"><span data-stu-id="575e5-211">600</span></span>  <br/> |<span data-ttu-id="575e5-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="575e5-212">CNAME</span></span>  <br/> |<span data-ttu-id="575e5-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="575e5-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="575e5-216">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="575e5-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="575e5-218">Adicione os cinco registros CNAME restantes.</span><span class="sxs-lookup"><span data-stu-id="575e5-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="575e5-219">Na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="575e5-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="575e5-220">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="575e5-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="575e5-221">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="575e5-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="575e5-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="575e5-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="575e5-223">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="575e5-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="575e5-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="575e5-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="575e5-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="575e5-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="575e5-226">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="575e5-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="575e5-p110">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="575e5-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="575e5-230">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="575e5-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="575e5-231">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="575e5-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="575e5-232">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="575e5-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="575e5-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="575e5-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="575e5-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="575e5-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="575e5-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="575e5-235">**Host**</span></span>|<span data-ttu-id="575e5-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="575e5-236">**TTL**</span></span>|<span data-ttu-id="575e5-237">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="575e5-237">**Type**</span></span>|<span data-ttu-id="575e5-238">**Dados**</span><span class="sxs-lookup"><span data-stu-id="575e5-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="575e5-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="575e5-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="575e5-240">600</span><span class="sxs-lookup"><span data-stu-id="575e5-240">600</span></span>  <br/> |<span data-ttu-id="575e5-241">TXT</span><span class="sxs-lookup"><span data-stu-id="575e5-241">TXT</span></span>  <br/> |<span data-ttu-id="575e5-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="575e5-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="575e5-243">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="575e5-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="575e5-245">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="575e5-245">Select **Create Record**.</span></span>
    
    ![Campo de vários valores](../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="575e5-247">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="575e5-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="575e5-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="575e5-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="575e5-249">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="575e5-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="575e5-250">Você será solicitado a fazer logon primeiro</span><span class="sxs-lookup"><span data-stu-id="575e5-250">You'll be prompted to login first</span></span> 
    
    ![Captura de tela da opção Convidar mais pessoas](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="575e5-252">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="575e5-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="575e5-253">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="575e5-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="575e5-254">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="575e5-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="575e5-255">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="575e5-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="575e5-256">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="575e5-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="575e5-257">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="575e5-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="575e5-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="575e5-258">**Host**</span></span>|<span data-ttu-id="575e5-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="575e5-259">**TTL**</span></span>|<span data-ttu-id="575e5-260">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="575e5-260">**Type**</span></span>|<span data-ttu-id="575e5-261">**Dados**</span><span class="sxs-lookup"><span data-stu-id="575e5-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="575e5-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="575e5-262">_sip._tls</span></span>|<span data-ttu-id="575e5-263">600</span><span class="sxs-lookup"><span data-stu-id="575e5-263">600</span></span>|<span data-ttu-id="575e5-264">SRV</span><span class="sxs-lookup"><span data-stu-id="575e5-264">SRV</span></span>|<span data-ttu-id="575e5-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="575e5-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="575e5-267">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="575e5-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="575e5-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="575e5-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="575e5-269">600</span><span class="sxs-lookup"><span data-stu-id="575e5-269">600</span></span>|<span data-ttu-id="575e5-270">SRV</span><span class="sxs-lookup"><span data-stu-id="575e5-270">SRV</span></span>|<span data-ttu-id="575e5-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="575e5-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="575e5-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="575e5-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="575e5-273">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="575e5-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="575e5-275">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="575e5-275">Select **Create Record**.</span></span>
    
    ![configurar opções de vídeo](../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="575e5-277">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="575e5-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="575e5-278">Na seção **adicionar registro DNS** , crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="575e5-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="575e5-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="575e5-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
