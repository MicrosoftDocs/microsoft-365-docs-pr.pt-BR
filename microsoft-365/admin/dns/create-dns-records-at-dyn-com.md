---
title: Criar registros DNS no Dyn.com para o Office 365
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Dyn.com para o Office 365.
ms.openlocfilehash: d25d4d9712dcd2e2a171c6ad0eac70b8c01e75ab
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211770"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="da1c6-103">Criar registros DNS no Dyn.com para o Office 365</span><span class="sxs-lookup"><span data-stu-id="da1c6-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="da1c6-104">**[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="da1c6-105">Se você usa a Dyn.com como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="da1c6-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="da1c6-106">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="da1c6-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="da1c6-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="da1c6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="da1c6-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="da1c6-110">Add a TXT record for verification</span></span>
<span data-ttu-id="da1c6-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="da1c6-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="da1c6-p102">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="da1c6-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="da1c6-115">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="da1c6-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="da1c6-116">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="da1c6-117">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="da1c6-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="da1c6-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="da1c6-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da1c6-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="da1c6-120">**Host**</span></span>|<span data-ttu-id="da1c6-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da1c6-121">**TTL**</span></span>|<span data-ttu-id="da1c6-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da1c6-122">**Type**</span></span>|<span data-ttu-id="da1c6-123">**Dados**</span><span class="sxs-lookup"><span data-stu-id="da1c6-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da1c6-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="da1c6-125">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-125">600</span></span>  <br/> |<span data-ttu-id="da1c6-126">TXT</span><span class="sxs-lookup"><span data-stu-id="da1c6-126">TXT</span></span>  <br/> |<span data-ttu-id="da1c6-127">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="da1c6-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="da1c6-128">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="da1c6-128">**Note:** This is an example.</span></span> <span data-ttu-id="da1c6-129">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="da1c6-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="da1c6-130">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="da1c6-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="da1c6-132">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="da1c6-134">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="da1c6-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="da1c6-135">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="da1c6-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="da1c6-136">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="da1c6-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="da1c6-137">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="da1c6-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="da1c6-138">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="da1c6-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="da1c6-139">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="da1c6-140">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="da1c6-p104">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="da1c6-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="da1c6-144">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="da1c6-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="da1c6-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="da1c6-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="da1c6-p105">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="da1c6-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="da1c6-149">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="da1c6-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="da1c6-150">Na página DNS do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="da1c6-151">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="da1c6-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="da1c6-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="da1c6-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da1c6-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="da1c6-154">**Host**</span></span>|<span data-ttu-id="da1c6-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da1c6-155">**TTL**</span></span>|<span data-ttu-id="da1c6-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da1c6-156">**Type**</span></span>|<span data-ttu-id="da1c6-157">**Dados**</span><span class="sxs-lookup"><span data-stu-id="da1c6-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da1c6-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="da1c6-159">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-159">600</span></span>  <br/> |<span data-ttu-id="da1c6-160">MX</span><span class="sxs-lookup"><span data-stu-id="da1c6-160">MX</span></span>  <br/> |<span data-ttu-id="da1c6-161">10  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="da1c6-162">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="da1c6-p106">O **10** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="da1c6-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="da1c6-165">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="da1c6-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="da1c6-166">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="da1c6-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="da1c6-167">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="da1c6-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="da1c6-169">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="da1c6-171">Caso haja outros registros MX, remova-os marcando a caixa de seleção de cada um na coluna **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![flores e texto](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="da1c6-173">Selecione **aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="da1c6-175">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="da1c6-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="da1c6-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="da1c6-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="da1c6-p108">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="da1c6-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="da1c6-180">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="da1c6-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="da1c6-181">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="da1c6-182">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="da1c6-183">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="da1c6-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="da1c6-184">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="da1c6-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="da1c6-185">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da1c6-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="da1c6-186">**Host**</span></span>|<span data-ttu-id="da1c6-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da1c6-187">**TTL**</span></span>|<span data-ttu-id="da1c6-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da1c6-188">**Type**</span></span>|<span data-ttu-id="da1c6-189">**Dados**</span><span class="sxs-lookup"><span data-stu-id="da1c6-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da1c6-190">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="da1c6-190">autodiscover</span></span>  <br/> |<span data-ttu-id="da1c6-191">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-191">600</span></span>  <br/> |<span data-ttu-id="da1c6-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="da1c6-192">CNAME</span></span>  <br/> |<span data-ttu-id="da1c6-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="da1c6-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="da1c6-195">sip</span><span class="sxs-lookup"><span data-stu-id="da1c6-195">sip</span></span>  <br/> |<span data-ttu-id="da1c6-196">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-196">600</span></span>  <br/> |<span data-ttu-id="da1c6-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="da1c6-197">CNAME</span></span>  <br/> |<span data-ttu-id="da1c6-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="da1c6-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="da1c6-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="da1c6-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="da1c6-201">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-201">600</span></span>  <br/> |<span data-ttu-id="da1c6-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="da1c6-202">CNAME</span></span>  <br/> |<span data-ttu-id="da1c6-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="da1c6-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="da1c6-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="da1c6-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="da1c6-206">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-206">600</span></span>  <br/> |<span data-ttu-id="da1c6-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="da1c6-207">CNAME</span></span>  <br/> |<span data-ttu-id="da1c6-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="da1c6-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="da1c6-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="da1c6-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="da1c6-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="da1c6-211">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-211">600</span></span>  <br/> |<span data-ttu-id="da1c6-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="da1c6-212">CNAME</span></span>  <br/> |<span data-ttu-id="da1c6-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="da1c6-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="da1c6-216">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="da1c6-218">Adicione os cinco registros CNAME restantes.</span><span class="sxs-lookup"><span data-stu-id="da1c6-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="da1c6-219">Na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="da1c6-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="da1c6-220">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="da1c6-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="da1c6-221">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="da1c6-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="da1c6-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="da1c6-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="da1c6-223">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="da1c6-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="da1c6-224">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="da1c6-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="da1c6-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="da1c6-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="da1c6-226">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="da1c6-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="da1c6-p110">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="da1c6-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="da1c6-230">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="da1c6-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="da1c6-231">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="da1c6-232">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="da1c6-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="da1c6-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="da1c6-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da1c6-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="da1c6-235">**Host**</span></span>|<span data-ttu-id="da1c6-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da1c6-236">**TTL**</span></span>|<span data-ttu-id="da1c6-237">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da1c6-237">**Type**</span></span>|<span data-ttu-id="da1c6-238">**Dados**</span><span class="sxs-lookup"><span data-stu-id="da1c6-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da1c6-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="da1c6-240">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-240">600</span></span>  <br/> |<span data-ttu-id="da1c6-241">TXT</span><span class="sxs-lookup"><span data-stu-id="da1c6-241">TXT</span></span>  <br/> |<span data-ttu-id="da1c6-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="da1c6-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="da1c6-243">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="da1c6-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="da1c6-245">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-245">Select **Create Record**.</span></span>
    
    ![Campo de vários valores](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="da1c6-247">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="da1c6-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="da1c6-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="da1c6-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="da1c6-249">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="da1c6-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="da1c6-250">Você será solicitado a fazer logon primeiro</span><span class="sxs-lookup"><span data-stu-id="da1c6-250">You'll be prompted to login first</span></span> 
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="da1c6-252">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="da1c6-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="da1c6-253">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="da1c6-254">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="da1c6-255">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="da1c6-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="da1c6-256">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="da1c6-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="da1c6-257">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="da1c6-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da1c6-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="da1c6-258">**Host**</span></span>|<span data-ttu-id="da1c6-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da1c6-259">**TTL**</span></span>|<span data-ttu-id="da1c6-260">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da1c6-260">**Type**</span></span>|<span data-ttu-id="da1c6-261">**Dados**</span><span class="sxs-lookup"><span data-stu-id="da1c6-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da1c6-262">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="da1c6-262">_sip._tls</span></span>|<span data-ttu-id="da1c6-263">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-263">600</span></span>|<span data-ttu-id="da1c6-264">SRV</span><span class="sxs-lookup"><span data-stu-id="da1c6-264">SRV</span></span>|<span data-ttu-id="da1c6-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="da1c6-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="da1c6-267">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="da1c6-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="da1c6-268">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="da1c6-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="da1c6-269">600</span><span class="sxs-lookup"><span data-stu-id="da1c6-269">600</span></span>|<span data-ttu-id="da1c6-270">SRV</span><span class="sxs-lookup"><span data-stu-id="da1c6-270">SRV</span></span>|<span data-ttu-id="da1c6-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="da1c6-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="da1c6-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da1c6-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="da1c6-273">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="da1c6-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="da1c6-275">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="da1c6-275">Select **Create Record**.</span></span>
    
    ![configurar opções de vídeo](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="da1c6-277">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="da1c6-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="da1c6-278">Na seção **adicionar registro DNS** , crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="da1c6-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="da1c6-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="da1c6-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
