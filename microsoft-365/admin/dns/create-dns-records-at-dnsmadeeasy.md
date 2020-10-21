---
title: Criar registros DNS no DNSMadeEasy para Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em DNSMadeEasy para a Microsoft.
ms.openlocfilehash: 266f5e8460395ae10b9c430cf66e1f443126ff64
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646206"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="bfbfc-103">Criar registros DNS no DNSMadeEasy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="bfbfc-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="bfbfc-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bfbfc-105">Se você usa a DNSMadeEasy como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="bfbfc-106">Depois que você adicionar esses registros no DNSMadeEasy, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="bfbfc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bfbfc-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bfbfc-109">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bfbfc-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="bfbfc-110">Add a TXT record for verification</span></span>
<span data-ttu-id="bfbfc-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bfbfc-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="bfbfc-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfbfc-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="bfbfc-116">Para contas do DNSMadeEasy, o domínio adicionado foi comprado de um registrador de domínio separado.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="bfbfc-117">O DNSMadeEasy não oferece serviços de registro de domínio.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="bfbfc-118">Sua capacidade de fazer logon em DNSMadeEasy e criar o registro DNS é uma prova de propriedade suficiente.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="bfbfc-119">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="bfbfc-120">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="bfbfc-121">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="bfbfc-122">Na página **DNS gerenciado** , na área **registros txt** , selecione o **+** controle () ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="bfbfc-123">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="bfbfc-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="bfbfc-125">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-125">**Name**</span></span> <br/> |<span data-ttu-id="bfbfc-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-126">**Value**</span></span> <br/> |<span data-ttu-id="bfbfc-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="bfbfc-128">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="bfbfc-129">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bfbfc-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bfbfc-130">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-130">**Note:** This is an example.</span></span> <span data-ttu-id="bfbfc-131">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="bfbfc-132">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="bfbfc-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="bfbfc-133">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="bfbfc-134">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="bfbfc-135">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bfbfc-136">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="bfbfc-137">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bfbfc-138">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="bfbfc-139">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="bfbfc-140">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="bfbfc-141">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bfbfc-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bfbfc-143">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bfbfc-144">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="bfbfc-145">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="bfbfc-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bfbfc-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="bfbfc-p108">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="bfbfc-149">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="bfbfc-150">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="bfbfc-152">Na página **DNS gerenciado** , na área **registros MX** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="bfbfc-153">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="bfbfc-155">Na área **Adicionar Registros MX**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bfbfc-156">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="bfbfc-157">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-157">**Name**</span></span>|<span data-ttu-id="bfbfc-158">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-158">**Server**</span></span>|<span data-ttu-id="bfbfc-159">**Nível de MX**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-159">**MX Level**</span></span>|<span data-ttu-id="bfbfc-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bfbfc-161">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="bfbfc-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bfbfc-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="bfbfc-163">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="bfbfc-164">**Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="bfbfc-165">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="bfbfc-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="bfbfc-166">10 </span><span class="sxs-lookup"><span data-stu-id="bfbfc-166">10</span></span>  <br/> <span data-ttu-id="bfbfc-167">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="bfbfc-168">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="bfbfc-170">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="bfbfc-172">Se houver outros registros MX listados na seção **Registros MX**, exclua todos eles selecionando cada um deles.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="bfbfc-174">Quando todos os registros estiverem selecionados, selecione **excluir selecionado**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="bfbfc-176">Na caixa de diálogo **excluir registros MX** , selecione **excluir** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="bfbfc-178">Adicionar os cinco registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bfbfc-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="bfbfc-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bfbfc-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="bfbfc-p110">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="bfbfc-182">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="bfbfc-183">Na página **DNS gerenciado** , na área **registros CNAME** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="bfbfc-184">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="bfbfc-186">Adicione o primeiro dos cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="bfbfc-187">Na área **Adicionar Registros CNAME**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="bfbfc-188">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-188">**Name**</span></span>|<span data-ttu-id="bfbfc-189">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-189">**Alias to**</span></span>|<span data-ttu-id="bfbfc-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="bfbfc-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bfbfc-191">autodiscover</span></span>  <br/> |<span data-ttu-id="bfbfc-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="bfbfc-193">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-194">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-194">1800</span></span>  <br/> |
    |<span data-ttu-id="bfbfc-195">sip</span><span class="sxs-lookup"><span data-stu-id="bfbfc-195">sip</span></span>  <br/> |<span data-ttu-id="bfbfc-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bfbfc-197">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-198">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-198">1800</span></span>  <br/> |
    |<span data-ttu-id="bfbfc-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bfbfc-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bfbfc-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bfbfc-201">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-202">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-202">1800</span></span>  <br/> |
    |<span data-ttu-id="bfbfc-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bfbfc-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bfbfc-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="bfbfc-205">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-206">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-206">1800</span></span>  <br/> |
    |<span data-ttu-id="bfbfc-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bfbfc-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bfbfc-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="bfbfc-209">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-210">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="bfbfc-212">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="bfbfc-214">Adicione cada um dos outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="bfbfc-215">Na seção **registros CNAME** , selecione o controle **(+)** ( **Adicionar novo**), crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Enviar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="bfbfc-216">Repita esse processo até ter criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bfbfc-217">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="bfbfc-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bfbfc-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bfbfc-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfbfc-219">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bfbfc-220">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bfbfc-221">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="bfbfc-222">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="bfbfc-223">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="bfbfc-223">Need examples?</span></span> <span data-ttu-id="bfbfc-224">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="bfbfc-225">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="bfbfc-226">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="bfbfc-227">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="bfbfc-228">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="bfbfc-229">Na página **DNS gerenciado** , na área **registros txt** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="bfbfc-230">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="bfbfc-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="bfbfc-233">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-233">**Name**</span></span>|<span data-ttu-id="bfbfc-234">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-234">**Value**</span></span>|<span data-ttu-id="bfbfc-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="bfbfc-236">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="bfbfc-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="bfbfc-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bfbfc-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bfbfc-238">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="bfbfc-239">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="bfbfc-241">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="bfbfc-243">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bfbfc-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="bfbfc-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bfbfc-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="bfbfc-p113">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="bfbfc-247">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="bfbfc-248">Na página **DNS gerenciado** , na área **Registros SRV** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="bfbfc-249">Pode ser necessário rolar para baixo.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="bfbfc-251">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="bfbfc-252">Na área **Adicionar Registros SRV**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="bfbfc-253">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-253">**Name**</span></span>|<span data-ttu-id="bfbfc-254">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-254">**Priority**</span></span>|<span data-ttu-id="bfbfc-255">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-255">**Weight**</span></span>|<span data-ttu-id="bfbfc-256">**Porta**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-256">**Port**</span></span>|<span data-ttu-id="bfbfc-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-257">**Host**</span></span>|<span data-ttu-id="bfbfc-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bfbfc-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="bfbfc-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="bfbfc-260">100</span><span class="sxs-lookup"><span data-stu-id="bfbfc-260">100</span></span>  <br/> |<span data-ttu-id="bfbfc-261">1</span><span class="sxs-lookup"><span data-stu-id="bfbfc-261">1</span></span>  <br/> |<span data-ttu-id="bfbfc-262">443</span><span class="sxs-lookup"><span data-stu-id="bfbfc-262">443</span></span>  <br/> |<span data-ttu-id="bfbfc-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bfbfc-264">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-265">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-265">1800</span></span>  <br/> |
    |<span data-ttu-id="bfbfc-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="bfbfc-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="bfbfc-267">100</span><span class="sxs-lookup"><span data-stu-id="bfbfc-267">100</span></span>  <br/> |<span data-ttu-id="bfbfc-268">1</span><span class="sxs-lookup"><span data-stu-id="bfbfc-268">1</span></span>  <br/> |<span data-ttu-id="bfbfc-269">5061</span><span class="sxs-lookup"><span data-stu-id="bfbfc-269">5061</span></span>  <br/> |<span data-ttu-id="bfbfc-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="bfbfc-271">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="bfbfc-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="bfbfc-272">1800</span><span class="sxs-lookup"><span data-stu-id="bfbfc-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="bfbfc-274">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="bfbfc-276">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="bfbfc-277">Na seção **Registros SRV** , selecione o controle **(+)** ( **Adicionar novo**), crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Enviar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="bfbfc-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bfbfc-279">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="bfbfc-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bfbfc-280">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfc-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

