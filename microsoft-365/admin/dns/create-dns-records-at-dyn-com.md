---
title: Criar registros DNS no Dyn.com para Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Dyn.com para a Microsoft.
ms.openlocfilehash: 91dbd3fbde8417764a01eb285b267f3981b2f139
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646134"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="3c8a0-103">Criar registros DNS no Dyn.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c8a0-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="3c8a0-104">**[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3c8a0-105">Se você usa a Dyn.com como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="3c8a0-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3c8a0-109">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="3c8a0-109">Add a TXT record for verification</span></span>
<span data-ttu-id="3c8a0-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3c8a0-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="3c8a0-p102">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c8a0-114">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c8a0-115">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c8a0-116">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c8a0-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3c8a0-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c8a0-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-119">**Host**</span></span>|<span data-ttu-id="3c8a0-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-120">**TTL**</span></span>|<span data-ttu-id="3c8a0-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-121">**Type**</span></span>|<span data-ttu-id="3c8a0-122">**Dados**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c8a0-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3c8a0-124">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-124">600</span></span>  <br/> |<span data-ttu-id="3c8a0-125">TXT</span><span class="sxs-lookup"><span data-stu-id="3c8a0-125">TXT</span></span>  <br/> |<span data-ttu-id="3c8a0-126">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3c8a0-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3c8a0-127">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-127">**Note:** This is an example.</span></span> <span data-ttu-id="3c8a0-128">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3c8a0-129">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="3c8a0-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="3c8a0-131">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="3c8a0-133">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3c8a0-134">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3c8a0-135">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3c8a0-136">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3c8a0-137">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3c8a0-138">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3c8a0-139">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3c8a0-p104">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3c8a0-143">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3c8a0-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3c8a0-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3c8a0-p105">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c8a0-148">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c8a0-149">Na página DNS do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c8a0-150">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c8a0-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3c8a0-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c8a0-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-153">**Host**</span></span>|<span data-ttu-id="3c8a0-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-154">**TTL**</span></span>|<span data-ttu-id="3c8a0-155">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-155">**Type**</span></span>|<span data-ttu-id="3c8a0-156">**Dados**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c8a0-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3c8a0-158">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-158">600</span></span>  <br/> |<span data-ttu-id="3c8a0-159">MX</span><span class="sxs-lookup"><span data-stu-id="3c8a0-159">MX</span></span>  <br/> |<span data-ttu-id="3c8a0-160">10  *\<domain-key\>*  . mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3c8a0-161">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3c8a0-p106">O **10** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="3c8a0-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3c8a0-164">**Observação:** Acesse sua  *\<domain-key\>*  conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3c8a0-165">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="3c8a0-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="3c8a0-166">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-166">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="3c8a0-168">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="3c8a0-170">Caso haja outros registros MX, remova-os marcando a caixa de seleção de cada um na coluna **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![flores e texto](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="3c8a0-172">Selecione **aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c8a0-174">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c8a0-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3c8a0-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3c8a0-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3c8a0-p108">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c8a0-179">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c8a0-180">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c8a0-181">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c8a0-182">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3c8a0-183">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3c8a0-184">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c8a0-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-185">**Host**</span></span>|<span data-ttu-id="3c8a0-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-186">**TTL**</span></span>|<span data-ttu-id="3c8a0-187">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-187">**Type**</span></span>|<span data-ttu-id="3c8a0-188">**Dados**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c8a0-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3c8a0-189">autodiscover</span></span>  <br/> |<span data-ttu-id="3c8a0-190">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-190">600</span></span>  <br/> |<span data-ttu-id="3c8a0-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c8a0-191">CNAME</span></span>  <br/> |<span data-ttu-id="3c8a0-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3c8a0-193">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c8a0-194">sip</span><span class="sxs-lookup"><span data-stu-id="3c8a0-194">sip</span></span>  <br/> |<span data-ttu-id="3c8a0-195">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-195">600</span></span>  <br/> |<span data-ttu-id="3c8a0-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c8a0-196">CNAME</span></span>  <br/> |<span data-ttu-id="3c8a0-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3c8a0-198">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c8a0-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3c8a0-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3c8a0-200">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-200">600</span></span>  <br/> |<span data-ttu-id="3c8a0-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c8a0-201">CNAME</span></span>  <br/> |<span data-ttu-id="3c8a0-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3c8a0-203">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c8a0-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3c8a0-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3c8a0-205">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-205">600</span></span>  <br/> |<span data-ttu-id="3c8a0-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c8a0-206">CNAME</span></span>  <br/> |<span data-ttu-id="3c8a0-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3c8a0-208">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3c8a0-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3c8a0-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3c8a0-210">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-210">600</span></span>  <br/> |<span data-ttu-id="3c8a0-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="3c8a0-211">CNAME</span></span>  <br/> |<span data-ttu-id="3c8a0-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3c8a0-213">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="3c8a0-215">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="3c8a0-217">Adicione os cinco registros CNAME restantes.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="3c8a0-218">Na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="3c8a0-219">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3c8a0-220">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="3c8a0-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3c8a0-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3c8a0-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c8a0-222">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3c8a0-223">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3c8a0-224">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3c8a0-225">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="3c8a0-p110">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c8a0-229">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c8a0-230">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c8a0-231">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c8a0-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3c8a0-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c8a0-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-234">**Host**</span></span>|<span data-ttu-id="3c8a0-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-235">**TTL**</span></span>|<span data-ttu-id="3c8a0-236">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-236">**Type**</span></span>|<span data-ttu-id="3c8a0-237">**Dados**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c8a0-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3c8a0-239">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-239">600</span></span>  <br/> |<span data-ttu-id="3c8a0-240">TXT</span><span class="sxs-lookup"><span data-stu-id="3c8a0-240">TXT</span></span>  <br/> |<span data-ttu-id="3c8a0-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3c8a0-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3c8a0-242">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="3c8a0-244">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-244">Select **Create Record**.</span></span>
    
    ![Campo de vários valores](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c8a0-246">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c8a0-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3c8a0-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3c8a0-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3c8a0-248">Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="3c8a0-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="3c8a0-249">Você será solicitado a fazer logon primeiro</span><span class="sxs-lookup"><span data-stu-id="3c8a0-249">You'll be prompted to login first</span></span> 
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3c8a0-251">Na página **serviços de nível de zona** , selecione **dyn serviço DNS padrão** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3c8a0-252">Na página **DNS** do seu domínio, selecione **preferências**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3c8a0-253">Selecione **habilitar interface especializada**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3c8a0-254">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3c8a0-255">Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3c8a0-256">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="3c8a0-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3c8a0-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-257">**Host**</span></span>|<span data-ttu-id="3c8a0-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-258">**TTL**</span></span>|<span data-ttu-id="3c8a0-259">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-259">**Type**</span></span>|<span data-ttu-id="3c8a0-260">**Dados**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c8a0-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3c8a0-261">_sip._tls</span></span>|<span data-ttu-id="3c8a0-262">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-262">600</span></span>|<span data-ttu-id="3c8a0-263">SRV</span><span class="sxs-lookup"><span data-stu-id="3c8a0-263">SRV</span></span>|<span data-ttu-id="3c8a0-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3c8a0-265">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="3c8a0-266">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3c8a0-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3c8a0-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3c8a0-268">600</span><span class="sxs-lookup"><span data-stu-id="3c8a0-268">600</span></span>|<span data-ttu-id="3c8a0-269">SRV</span><span class="sxs-lookup"><span data-stu-id="3c8a0-269">SRV</span></span>|<span data-ttu-id="3c8a0-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3c8a0-271">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="3c8a0-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="3c8a0-272">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="3c8a0-274">Selecione **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-274">Select **Create Record**.</span></span>
    
    ![configurar opções de vídeo](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="3c8a0-276">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3c8a0-277">Na seção **adicionar registro DNS** , crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione **criar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="3c8a0-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c8a0-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
