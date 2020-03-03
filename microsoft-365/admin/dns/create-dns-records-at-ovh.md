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
ms.openlocfilehash: 4857addd7dfd096c1ddd6e59f1f17ace76b75a9e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354342"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="ce8f2-103">Criar registros DNS no OVH para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="ce8f2-104">Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ce8f2-105">Se o OVH for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ce8f2-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="ce8f2-107">Criar registros DNS no OVH para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="ce8f2-108">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="ce8f2-109">Adicionar os registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="ce8f2-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="ce8f2-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ce8f2-111">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="ce8f2-112">Depois que você adicionar esses registros no OVH, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ce8f2-113">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ce8f2-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ce8f2-117">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="ce8f2-117">Add a TXT record for verification</span></span>
<span data-ttu-id="ce8f2-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ce8f2-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="ce8f2-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce8f2-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ce8f2-123">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-123">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ce8f2-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-124">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ce8f2-126">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ce8f2-128">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-128">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ce8f2-130">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-130">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ce8f2-132">Selecionar **txt**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-132">Select **TXT**</span></span>
    
    ![OVH selecionar entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="ce8f2-134">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="ce8f2-135">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ce8f2-136">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-136">**Record type**</span></span>|<span data-ttu-id="ce8f2-137">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-137">**Sub-domain**</span></span>|<span data-ttu-id="ce8f2-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-138">**TTL**</span></span>|<span data-ttu-id="ce8f2-139">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce8f2-140">TXT</span><span class="sxs-lookup"><span data-stu-id="ce8f2-140">TXT</span></span>  <br/> |<span data-ttu-id="ce8f2-141">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="ce8f2-142">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ce8f2-143">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="ce8f2-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="ce8f2-144">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-144">**Note:** This is an example.</span></span> <span data-ttu-id="ce8f2-145">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="ce8f2-146">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ce8f2-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ce8f2-147">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-147">Select **Confirm**.</span></span> 
    
    ![OVH confirmar TXT para verificação](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="ce8f2-149">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ce8f2-150">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ce8f2-151">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ce8f2-152">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ce8f2-153">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ce8f2-154">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ce8f2-155">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ce8f2-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ce8f2-159">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ce8f2-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ce8f2-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="ce8f2-161">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-161">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ce8f2-162">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-162">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ce8f2-164">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ce8f2-166">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-166">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ce8f2-168">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-168">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ce8f2-170">Selecione **MX**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-170">Select **MX**.</span></span>
    
    ![Tipo de registro MX OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="ce8f2-172">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="ce8f2-173">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ce8f2-174">Por padrão, o OVH usa notação relativa para o destino, que adiciona o nome de domínio ao final do registro de destino.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="ce8f2-175">Para usar a notação absoluta em vez disso, adicione um ponto ao registro de destino conforme mostrado na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="ce8f2-176">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-176">**Record type**</span></span>|<span data-ttu-id="ce8f2-177">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-177">**Sub-domain**</span></span>|<span data-ttu-id="ce8f2-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-178">**TTL**</span></span>|<span data-ttu-id="ce8f2-179">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-179">**Priority**</span></span>|<span data-ttu-id="ce8f2-180">**Destino**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce8f2-181">MX</span><span class="sxs-lookup"><span data-stu-id="ce8f2-181">MX</span></span>  <br/> |<span data-ttu-id="ce8f2-182">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="ce8f2-183">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ce8f2-184">10 </span><span class="sxs-lookup"><span data-stu-id="ce8f2-184">10</span></span>  <br/> <span data-ttu-id="ce8f2-185">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="ce8f2-186">\<Domain-Key\>. mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ce8f2-187">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="ce8f2-188">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ce8f2-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH registro MX para email](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="ce8f2-190">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-190">Select **Next**.</span></span>
    
    ![Registro MX OVH Selecione Avançar](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="ce8f2-192">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-192">Select **Confirm**.</span></span>
    
    ![Registro MX OVH selecione confirmar](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="ce8f2-194">Se houver outros registros MX, exclua todos na lista na página **zona DNS** .</span><span class="sxs-lookup"><span data-stu-id="ce8f2-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="ce8f2-195">Selecione cada registro e, na coluna **ações** , selecione o ícone lixeira-pode **excluir** .</span><span class="sxs-lookup"><span data-stu-id="ce8f2-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH excluir registro MX](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="ce8f2-197">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ce8f2-198">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ce8f2-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ce8f2-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="ce8f2-200">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-200">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ce8f2-201">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-201">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ce8f2-203">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ce8f2-205">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-205">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ce8f2-207">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-207">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ce8f2-209">Selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-209">Select **CNAME**.</span></span>
    
    ![OVH adicionar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="ce8f2-211">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="ce8f2-212">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="ce8f2-213">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ce8f2-214">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-214">**Record type**</span></span>|<span data-ttu-id="ce8f2-215">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-215">**Sub-domain**</span></span>|<span data-ttu-id="ce8f2-216">**Destino**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-216">**Target**</span></span>|<span data-ttu-id="ce8f2-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce8f2-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce8f2-218">CNAME</span></span>  <br/> |<span data-ttu-id="ce8f2-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ce8f2-219">autodiscover</span></span>  <br/> |<span data-ttu-id="ce8f2-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="ce8f2-221">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ce8f2-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ce8f2-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce8f2-222">CNAME</span></span>  <br/> |<span data-ttu-id="ce8f2-223">sip</span><span class="sxs-lookup"><span data-stu-id="ce8f2-223">sip</span></span>  <br/> |<span data-ttu-id="ce8f2-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ce8f2-225">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ce8f2-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ce8f2-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce8f2-226">CNAME</span></span>  <br/> |<span data-ttu-id="ce8f2-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ce8f2-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ce8f2-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ce8f2-229">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ce8f2-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ce8f2-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce8f2-230">CNAME</span></span>  <br/> |<span data-ttu-id="ce8f2-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ce8f2-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ce8f2-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="ce8f2-233">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ce8f2-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ce8f2-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="ce8f2-234">CNAME</span></span>  <br/> |<span data-ttu-id="ce8f2-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ce8f2-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ce8f2-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="ce8f2-237">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="ce8f2-237">3600 seconds</span></span>  <br/> |
   
    ![Registro CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="ce8f2-239">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-239">Select **Next**.</span></span>
    
    ![OVH adicionar valores CNAME e selecionar avançar](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="ce8f2-241">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="ce8f2-242">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="ce8f2-243">Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ce8f2-244">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="ce8f2-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ce8f2-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ce8f2-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce8f2-246">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ce8f2-247">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ce8f2-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ce8f2-249">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="ce8f2-250">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-250">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ce8f2-251">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-251">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ce8f2-253">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ce8f2-255">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-255">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ce8f2-257">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-257">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ce8f2-259">Selecione **txt**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="ce8f2-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="ce8f2-261">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-261">**Record type**</span></span>|<span data-ttu-id="ce8f2-262">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-262">**Sub-domain**</span></span>|<span data-ttu-id="ce8f2-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-263">**TTL**</span></span>|<span data-ttu-id="ce8f2-264">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce8f2-265">TXT</span><span class="sxs-lookup"><span data-stu-id="ce8f2-265">TXT</span></span>  <br/> |<span data-ttu-id="ce8f2-266">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="ce8f2-267">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ce8f2-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ce8f2-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ce8f2-269">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH adicionar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="ce8f2-271">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-271">Select **Next**.</span></span>
    
    ![OVH adicionar registro TXT para SPF e selecione avançar](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="ce8f2-273">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-273">Select **Confirm**.</span></span>
    
    ![OVH adicionar registro TXT para SPF e Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ce8f2-275">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8f2-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ce8f2-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ce8f2-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="ce8f2-277">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-277">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ce8f2-278">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-278">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ce8f2-280">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ce8f2-282">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-282">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ce8f2-284">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-284">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ce8f2-286">Selecione **SRV**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-286">Select **SRV**.</span></span>
    
    ![OVH selecionar o tipo de registro SRV](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="ce8f2-288">Crie o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="ce8f2-289">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="ce8f2-290">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ce8f2-291">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-291">**Record type**</span></span>|<span data-ttu-id="ce8f2-292">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-292">**Sub-domain**</span></span>|<span data-ttu-id="ce8f2-293">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-293">**Priority**</span></span>|<span data-ttu-id="ce8f2-294">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-294">**Weight**</span></span>|<span data-ttu-id="ce8f2-295">**Porta**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-295">**Port**</span></span>|<span data-ttu-id="ce8f2-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-296">**TTL**</span></span>|<span data-ttu-id="ce8f2-297">**Destino**</span><span class="sxs-lookup"><span data-stu-id="ce8f2-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ce8f2-298">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="ce8f2-299">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="ce8f2-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="ce8f2-300">100</span><span class="sxs-lookup"><span data-stu-id="ce8f2-300">100</span></span>  <br/> |<span data-ttu-id="ce8f2-301">1</span><span class="sxs-lookup"><span data-stu-id="ce8f2-301">1</span></span>  <br/> |<span data-ttu-id="ce8f2-302">443</span><span class="sxs-lookup"><span data-stu-id="ce8f2-302">443</span></span>  <br/> |<span data-ttu-id="ce8f2-303">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ce8f2-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="ce8f2-305">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="ce8f2-306">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="ce8f2-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ce8f2-307">100</span><span class="sxs-lookup"><span data-stu-id="ce8f2-307">100</span></span>  <br/> |<span data-ttu-id="ce8f2-308">1</span><span class="sxs-lookup"><span data-stu-id="ce8f2-308">1</span></span>  <br/> |<span data-ttu-id="ce8f2-309">5061</span><span class="sxs-lookup"><span data-stu-id="ce8f2-309">5061</span></span>  <br/> |<span data-ttu-id="ce8f2-310">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="ce8f2-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ce8f2-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Registro SRV OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="ce8f2-313">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-313">Select **Next**.</span></span>
    
    ![Registro SRV OVH Selecione Avançar](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="ce8f2-315">Selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="ce8f2-316">Repita as etapas anteriores para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-316">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="ce8f2-317">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="ce8f2-317">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="ce8f2-p120">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ce8f2-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
