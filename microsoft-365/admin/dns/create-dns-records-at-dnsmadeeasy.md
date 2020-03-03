---
title: Criar registros DNS no DNSMadeEasy para o Office 365
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em DNSMadeEasy para o Office 365.
ms.openlocfilehash: 82244d216652b1957aefc3b81acd881ea4b32393
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350312"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="be929-103">Criar registros DNS no DNSMadeEasy para o Office 365</span><span class="sxs-lookup"><span data-stu-id="be929-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="be929-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="be929-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="be929-105">Se você usa a DNSMadeEasy como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="be929-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="be929-106">Depois que você adicionar esses registros na DNSMadeEasy, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="be929-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="be929-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="be929-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="be929-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="be929-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="be929-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="be929-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="be929-110">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="be929-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="be929-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="be929-111">Add a TXT record for verification</span></span>
<span data-ttu-id="be929-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="be929-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="be929-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="be929-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be929-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="be929-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="be929-117">Para contas do DNSMadeEasy, o domínio adicionado foi comprado de um registrador de domínio separado.</span><span class="sxs-lookup"><span data-stu-id="be929-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="be929-118">O DNSMadeEasy não oferece serviços de registro de domínio.</span><span class="sxs-lookup"><span data-stu-id="be929-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="be929-119">Sua capacidade de fazer logon em DNSMadeEasy e criar o registro DNS é uma prova de propriedade suficiente.</span><span class="sxs-lookup"><span data-stu-id="be929-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="be929-120">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="be929-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="be929-121">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="be929-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="be929-122">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="be929-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="be929-123">Na página **DNS gerenciado** , na área **registros txt** , selecione o controle ( **+**) ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="be929-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="be929-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="be929-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="be929-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="be929-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="be929-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="be929-126">**Name**</span></span> <br/> |<span data-ttu-id="be929-127">**Valor**</span><span class="sxs-lookup"><span data-stu-id="be929-127">**Value**</span></span> <br/> |<span data-ttu-id="be929-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="be929-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="be929-129">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="be929-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="be929-130">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="be929-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="be929-131">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="be929-131">**Note:** This is an example.</span></span> <span data-ttu-id="be929-132">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="be929-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="be929-133">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="be929-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="be929-134">1800</span><span class="sxs-lookup"><span data-stu-id="be929-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="be929-135">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="be929-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="be929-136">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="be929-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="be929-137">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="be929-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="be929-138">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="be929-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="be929-139">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="be929-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="be929-140">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="be929-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="be929-141">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="be929-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="be929-142">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="be929-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="be929-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="be929-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="be929-144">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="be929-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="be929-145">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="be929-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="be929-146">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="be929-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="be929-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="be929-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="be929-p108">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="be929-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="be929-150">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="be929-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="be929-151">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="be929-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="be929-153">Na página **DNS gerenciado** , na área **registros MX** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="be929-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="be929-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="be929-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="be929-156">Na área **Adicionar Registros MX**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="be929-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="be929-157">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="be929-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="be929-158">**Nome**</span><span class="sxs-lookup"><span data-stu-id="be929-158">**Name**</span></span>|<span data-ttu-id="be929-159">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="be929-159">**Server**</span></span>|<span data-ttu-id="be929-160">**Nível de MX**</span><span class="sxs-lookup"><span data-stu-id="be929-160">**MX Level**</span></span>|<span data-ttu-id="be929-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="be929-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="be929-162">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="be929-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="be929-163">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="be929-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="be929-164">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="be929-165">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="be929-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="be929-166">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="be929-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="be929-167">10 </span><span class="sxs-lookup"><span data-stu-id="be929-167">10</span></span>  <br/> <span data-ttu-id="be929-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="be929-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="be929-169">1800</span><span class="sxs-lookup"><span data-stu-id="be929-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="be929-171">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="be929-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="be929-173">Se houver outros registros MX listados na seção **Registros MX**, exclua todos eles selecionando cada um deles.</span><span class="sxs-lookup"><span data-stu-id="be929-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="be929-175">Quando todos os registros estiverem selecionados, selecione **excluir selecionado**.</span><span class="sxs-lookup"><span data-stu-id="be929-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="be929-177">Na caixa de diálogo **excluir registros MX** , selecione **excluir** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="be929-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="be929-179">Adicionar os cinco registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="be929-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="be929-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="be929-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="be929-p110">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="be929-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="be929-183">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="be929-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="be929-184">Na página **DNS gerenciado** , na área **registros CNAME** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="be929-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="be929-185">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="be929-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="be929-187">Adicione o primeiro dos cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="be929-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="be929-188">Na área **Adicionar Registros CNAME**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="be929-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="be929-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="be929-189">**Name**</span></span>|<span data-ttu-id="be929-190">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="be929-190">**Alias to**</span></span>|<span data-ttu-id="be929-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="be929-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="be929-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="be929-192">autodiscover</span></span>  <br/> |<span data-ttu-id="be929-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="be929-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="be929-194">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-195">1800</span><span class="sxs-lookup"><span data-stu-id="be929-195">1800</span></span>  <br/> |
    |<span data-ttu-id="be929-196">sip</span><span class="sxs-lookup"><span data-stu-id="be929-196">sip</span></span>  <br/> |<span data-ttu-id="be929-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be929-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="be929-198">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-199">1800</span><span class="sxs-lookup"><span data-stu-id="be929-199">1800</span></span>  <br/> |
    |<span data-ttu-id="be929-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="be929-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="be929-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be929-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="be929-202">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-203">1800</span><span class="sxs-lookup"><span data-stu-id="be929-203">1800</span></span>  <br/> |
    |<span data-ttu-id="be929-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="be929-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="be929-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="be929-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="be929-206">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-207">1800</span><span class="sxs-lookup"><span data-stu-id="be929-207">1800</span></span>  <br/> |
    |<span data-ttu-id="be929-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="be929-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="be929-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="be929-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="be929-210">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-211">1800</span><span class="sxs-lookup"><span data-stu-id="be929-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="be929-213">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="be929-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="be929-215">Adicione cada um dos outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="be929-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="be929-216">Na seção **registros CNAME** , selecione o controle **(+)** ( **Adicionar novo**), crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Enviar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="be929-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="be929-217">Repita esse processo até ter criado todos os cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="be929-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="be929-218">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="be929-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="be929-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="be929-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="be929-220">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="be929-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="be929-221">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="be929-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="be929-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="be929-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="be929-223">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="be929-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="be929-224">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="be929-224">Need examples?</span></span> <span data-ttu-id="be929-225">Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). </span><span class="sxs-lookup"><span data-stu-id="be929-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="be929-226">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="be929-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="be929-227">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="be929-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="be929-228">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="be929-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="be929-229">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="be929-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="be929-230">Na página **DNS gerenciado** , na área **registros txt** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="be929-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="be929-231">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="be929-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="be929-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="be929-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="be929-234">**Nome**</span><span class="sxs-lookup"><span data-stu-id="be929-234">**Name**</span></span>|<span data-ttu-id="be929-235">**Valor**</span><span class="sxs-lookup"><span data-stu-id="be929-235">**Value**</span></span>|<span data-ttu-id="be929-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="be929-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="be929-237">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="be929-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="be929-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="be929-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="be929-239">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="be929-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="be929-240">1800</span><span class="sxs-lookup"><span data-stu-id="be929-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="be929-242">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="be929-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="be929-244">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="be929-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="be929-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="be929-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="be929-p113">Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="be929-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="be929-248">Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="be929-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="be929-249">Na página **DNS gerenciado** , na área **Registros SRV** , selecione o controle **(+)** ( **Adicionar novo**).</span><span class="sxs-lookup"><span data-stu-id="be929-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="be929-250">Pode ser necessário rolar para baixo.</span><span class="sxs-lookup"><span data-stu-id="be929-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="be929-252">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="be929-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="be929-253">Na área **Adicionar Registros SRV**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="be929-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="be929-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="be929-254">**Name**</span></span>|<span data-ttu-id="be929-255">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="be929-255">**Priority**</span></span>|<span data-ttu-id="be929-256">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="be929-256">**Weight**</span></span>|<span data-ttu-id="be929-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="be929-257">**Port**</span></span>|<span data-ttu-id="be929-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="be929-258">**Host**</span></span>|<span data-ttu-id="be929-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="be929-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="be929-260">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="be929-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="be929-261">100</span><span class="sxs-lookup"><span data-stu-id="be929-261">100</span></span>  <br/> |<span data-ttu-id="be929-262">1</span><span class="sxs-lookup"><span data-stu-id="be929-262">1</span></span>  <br/> |<span data-ttu-id="be929-263">443</span><span class="sxs-lookup"><span data-stu-id="be929-263">443</span></span>  <br/> |<span data-ttu-id="be929-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be929-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="be929-265">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-266">1800</span><span class="sxs-lookup"><span data-stu-id="be929-266">1800</span></span>  <br/> |
    |<span data-ttu-id="be929-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="be929-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="be929-268">100</span><span class="sxs-lookup"><span data-stu-id="be929-268">100</span></span>  <br/> |<span data-ttu-id="be929-269">1</span><span class="sxs-lookup"><span data-stu-id="be929-269">1</span></span>  <br/> |<span data-ttu-id="be929-270">5061</span><span class="sxs-lookup"><span data-stu-id="be929-270">5061</span></span>  <br/> |<span data-ttu-id="be929-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be929-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="be929-272">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="be929-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="be929-273">1800</span><span class="sxs-lookup"><span data-stu-id="be929-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="be929-275">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="be929-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="be929-277">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="be929-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="be929-278">Na seção **Registros SRV** , selecione o controle **(+)** ( **Adicionar novo**), crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Enviar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="be929-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="be929-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="be929-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="be929-280">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="be929-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="be929-281">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="be929-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

