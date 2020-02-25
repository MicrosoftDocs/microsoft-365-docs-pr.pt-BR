---
title: Criar registros DNS no OVH para o Office 365
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em OVH para o Office 365.
ms.openlocfilehash: 87de24fd47ce048cb88a2b7d4bcff97b1c155456
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238866"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="41d43-103">Criar registros DNS no OVH para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="41d43-104">Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="41d43-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="41d43-105">Se o OVH for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="41d43-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="41d43-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="41d43-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="41d43-107">Criar registros DNS no OVH para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="41d43-108">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="41d43-109">Adicionar os registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="41d43-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="41d43-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="41d43-111">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="41d43-112">Depois que você adicionar esses registros no OVH, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="41d43-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="41d43-113">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="41d43-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="41d43-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="41d43-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="41d43-117">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="41d43-117">Add a TXT record for verification</span></span>
<span data-ttu-id="41d43-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="41d43-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="41d43-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="41d43-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41d43-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="41d43-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="41d43-123">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="41d43-123">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="41d43-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="41d43-124">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="41d43-126">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="41d43-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="41d43-128">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="41d43-128">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="41d43-130">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="41d43-130">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="41d43-132">Selecionar **txt**</span><span class="sxs-lookup"><span data-stu-id="41d43-132">Select **TXT**</span></span>
    
    ![OVH selecionar entrada TXT](../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="41d43-134">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="41d43-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="41d43-135">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="41d43-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="41d43-136">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="41d43-136">**Record type**</span></span>|<span data-ttu-id="41d43-137">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="41d43-137">**Sub-domain**</span></span>|<span data-ttu-id="41d43-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="41d43-138">**TTL**</span></span>|<span data-ttu-id="41d43-139">**Valor**</span><span class="sxs-lookup"><span data-stu-id="41d43-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="41d43-140">TXT</span><span class="sxs-lookup"><span data-stu-id="41d43-140">TXT</span></span>  <br/> |<span data-ttu-id="41d43-141">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="41d43-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="41d43-142">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="41d43-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="41d43-143">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="41d43-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="41d43-144">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="41d43-144">**Note:** This is an example.</span></span> <span data-ttu-id="41d43-145">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="41d43-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="41d43-146">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="41d43-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="41d43-147">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-147">Select **Confirm**.</span></span> 
    
    ![OVH confirmar TXT para verificação](../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="41d43-149">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="41d43-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="41d43-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="41d43-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="41d43-151">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="41d43-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="41d43-152">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="41d43-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="41d43-153">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="41d43-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="41d43-154">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="41d43-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="41d43-155">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="41d43-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="41d43-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="41d43-159">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="41d43-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="41d43-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="41d43-161">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="41d43-161">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="41d43-162">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="41d43-162">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="41d43-164">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="41d43-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="41d43-166">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="41d43-166">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="41d43-168">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="41d43-168">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="41d43-170">Selecione **MX**.</span><span class="sxs-lookup"><span data-stu-id="41d43-170">Select **MX**.</span></span>
    
    ![Tipo de registro MX OVH](../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="41d43-172">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="41d43-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="41d43-173">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="41d43-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="41d43-174">Por padrão, o OVH usa notação relativa para o destino, que adiciona o nome de domínio ao final do registro de destino.</span><span class="sxs-lookup"><span data-stu-id="41d43-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="41d43-175">Para usar a notação absoluta em vez disso, adicione um ponto ao registro de destino conforme mostrado na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="41d43-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="41d43-176">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="41d43-176">**Record type**</span></span>|<span data-ttu-id="41d43-177">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="41d43-177">**Sub-domain**</span></span>|<span data-ttu-id="41d43-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="41d43-178">**TTL**</span></span>|<span data-ttu-id="41d43-179">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="41d43-179">**Priority**</span></span>|<span data-ttu-id="41d43-180">**Target**</span><span class="sxs-lookup"><span data-stu-id="41d43-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="41d43-181">MX</span><span class="sxs-lookup"><span data-stu-id="41d43-181">MX</span></span>  <br/> |<span data-ttu-id="41d43-182">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="41d43-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="41d43-183">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="41d43-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="41d43-184">10 </span><span class="sxs-lookup"><span data-stu-id="41d43-184">10</span></span>  <br/> <span data-ttu-id="41d43-185">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="41d43-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="41d43-186">\<Domain-Key\>. mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="41d43-187">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="41d43-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="41d43-188">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="41d43-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH registro MX para email](../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="41d43-190">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-190">Select **Next**.</span></span>
    
    ![Registro MX OVH Selecione Avançar](../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="41d43-192">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-192">Select **Confirm**.</span></span>
    
    ![Registro MX OVH selecione confirmar](../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="41d43-194">Se houver outros registros MX, exclua todos na lista na página **zona DNS** .</span><span class="sxs-lookup"><span data-stu-id="41d43-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="41d43-195">Selecione cada registro e, na coluna **ações** , selecione o ícone lixeira-pode **excluir** .</span><span class="sxs-lookup"><span data-stu-id="41d43-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH excluir registro MX](../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="41d43-197">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="41d43-198">Adicionar os registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="41d43-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="41d43-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="41d43-200">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="41d43-200">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="41d43-201">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="41d43-201">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="41d43-203">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="41d43-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="41d43-205">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="41d43-205">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="41d43-207">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="41d43-207">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="41d43-209">Selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="41d43-209">Select **CNAME**.</span></span>
    
    ![OVH adicionar tipo de registro CNAME](../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="41d43-211">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="41d43-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="41d43-212">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="41d43-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="41d43-213">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="41d43-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="41d43-214">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="41d43-214">**Record type**</span></span>|<span data-ttu-id="41d43-215">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="41d43-215">**Sub-domain**</span></span>|<span data-ttu-id="41d43-216">**Destino**</span><span class="sxs-lookup"><span data-stu-id="41d43-216">**Target**</span></span>|<span data-ttu-id="41d43-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="41d43-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="41d43-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="41d43-218">CNAME</span></span>  <br/> |<span data-ttu-id="41d43-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="41d43-219">autodiscover</span></span>  <br/> |<span data-ttu-id="41d43-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="41d43-221">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="41d43-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="41d43-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="41d43-222">CNAME</span></span>  <br/> |<span data-ttu-id="41d43-223">sip</span><span class="sxs-lookup"><span data-stu-id="41d43-223">sip</span></span>  <br/> |<span data-ttu-id="41d43-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="41d43-225">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="41d43-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="41d43-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="41d43-226">CNAME</span></span>  <br/> |<span data-ttu-id="41d43-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="41d43-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="41d43-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="41d43-229">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="41d43-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="41d43-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="41d43-230">CNAME</span></span>  <br/> |<span data-ttu-id="41d43-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="41d43-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="41d43-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="41d43-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="41d43-233">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="41d43-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="41d43-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="41d43-234">CNAME</span></span>  <br/> |<span data-ttu-id="41d43-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="41d43-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="41d43-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="41d43-237">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="41d43-237">3600 seconds</span></span>  <br/> |
   
    ![Registro CNAME OVH](../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="41d43-239">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-239">Select **Next**.</span></span>
    
    ![OVH adicionar valores CNAME e selecionar avançar](../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="41d43-241">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="41d43-242">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="41d43-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="41d43-243">Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="41d43-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="41d43-244">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="41d43-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="41d43-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="41d43-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="41d43-246">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="41d43-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="41d43-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="41d43-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="41d43-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="41d43-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="41d43-249">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="41d43-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="41d43-250">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="41d43-250">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="41d43-251">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="41d43-251">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="41d43-253">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="41d43-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="41d43-255">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="41d43-255">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="41d43-257">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="41d43-257">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="41d43-259">Selecione **txt**.</span><span class="sxs-lookup"><span data-stu-id="41d43-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="41d43-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="41d43-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="41d43-261">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="41d43-261">**Record type**</span></span>|<span data-ttu-id="41d43-262">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="41d43-262">**Sub-domain**</span></span>|<span data-ttu-id="41d43-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="41d43-263">**TTL**</span></span>|<span data-ttu-id="41d43-264">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="41d43-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="41d43-265">TXT</span><span class="sxs-lookup"><span data-stu-id="41d43-265">TXT</span></span>  <br/> |<span data-ttu-id="41d43-266">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="41d43-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="41d43-267">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="41d43-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="41d43-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="41d43-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="41d43-269">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="41d43-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH adicionar registro TXT para SPF](../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="41d43-271">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-271">Select **Next**.</span></span>
    
    ![OVH adicionar registro TXT para SPF e selecione avançar](../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="41d43-273">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-273">Select **Confirm**.</span></span>
    
    ![OVH adicionar registro TXT para SPF e Confirm](../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="41d43-275">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="41d43-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="41d43-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="41d43-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="41d43-277">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="41d43-277">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="41d43-278">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="41d43-278">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="41d43-280">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="41d43-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="41d43-282">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="41d43-282">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="41d43-284">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="41d43-284">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="41d43-286">Selecione **SRV**.</span><span class="sxs-lookup"><span data-stu-id="41d43-286">Select **SRV**.</span></span>
    
    ![OVH selecionar o tipo de registro SRV](../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="41d43-288">Crie o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="41d43-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="41d43-289">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="41d43-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="41d43-290">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="41d43-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="41d43-291">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="41d43-291">**Record type**</span></span>|<span data-ttu-id="41d43-292">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="41d43-292">**Sub-domain**</span></span>|<span data-ttu-id="41d43-293">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="41d43-293">**Priority**</span></span>|<span data-ttu-id="41d43-294">**Peso**</span><span class="sxs-lookup"><span data-stu-id="41d43-294">**Weight**</span></span>|<span data-ttu-id="41d43-295">**Porta**</span><span class="sxs-lookup"><span data-stu-id="41d43-295">**Port**</span></span>|<span data-ttu-id="41d43-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="41d43-296">**TTL**</span></span>|<span data-ttu-id="41d43-297">**Target**</span><span class="sxs-lookup"><span data-stu-id="41d43-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="41d43-298">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="41d43-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="41d43-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="41d43-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="41d43-300">100</span><span class="sxs-lookup"><span data-stu-id="41d43-300">100</span></span>  <br/> |<span data-ttu-id="41d43-301">1</span><span class="sxs-lookup"><span data-stu-id="41d43-301">1</span></span>  <br/> |<span data-ttu-id="41d43-302">443</span><span class="sxs-lookup"><span data-stu-id="41d43-302">443</span></span>  <br/> |<span data-ttu-id="41d43-303">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="41d43-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="41d43-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="41d43-305">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="41d43-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="41d43-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="41d43-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="41d43-307">100</span><span class="sxs-lookup"><span data-stu-id="41d43-307">100</span></span>  <br/> |<span data-ttu-id="41d43-308">1</span><span class="sxs-lookup"><span data-stu-id="41d43-308">1</span></span>  <br/> |<span data-ttu-id="41d43-309">5061</span><span class="sxs-lookup"><span data-stu-id="41d43-309">5061</span></span>  <br/> |<span data-ttu-id="41d43-310">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="41d43-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="41d43-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="41d43-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Registro SRV OVH](../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="41d43-313">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-313">Select **Next**.</span></span>
    
    ![Registro SRV OVH Selecione Avançar](../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="41d43-315">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41d43-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="41d43-316">Repita as etapas anteriores para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="41d43-316">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="41d43-317">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="41d43-317">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="41d43-p120">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="41d43-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
