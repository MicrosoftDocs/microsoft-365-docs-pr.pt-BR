---
title: Criar registros DNS no OVH para Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em OVH para a Microsoft.
ms.openlocfilehash: 87a2a731a253fdc0593a1aae8020e615dca63c4a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645810"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="07fcc-103">Criar registros DNS no OVH para Microsoft</span><span class="sxs-lookup"><span data-stu-id="07fcc-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="07fcc-104">Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="07fcc-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="07fcc-105">Se o OVH for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="07fcc-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="07fcc-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="07fcc-107">Criar registros DNS no OVH para Microsoft</span><span class="sxs-lookup"><span data-stu-id="07fcc-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="07fcc-108">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07fcc-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="07fcc-109">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="07fcc-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="07fcc-110">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="07fcc-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="07fcc-111">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="07fcc-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="07fcc-112">Depois que você adicionar esses registros no OVH, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07fcc-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="07fcc-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07fcc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="07fcc-116">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="07fcc-116">Add a TXT record for verification</span></span>
<span data-ttu-id="07fcc-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="07fcc-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="07fcc-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="07fcc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07fcc-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="07fcc-122">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="07fcc-122">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="07fcc-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="07fcc-123">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="07fcc-125">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="07fcc-127">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-127">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="07fcc-129">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-129">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="07fcc-131">Selecionar **txt**</span><span class="sxs-lookup"><span data-stu-id="07fcc-131">Select **TXT**</span></span>
    
    ![OVH selecionar entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="07fcc-133">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="07fcc-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="07fcc-134">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="07fcc-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="07fcc-135">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="07fcc-135">**Record type**</span></span>|<span data-ttu-id="07fcc-136">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="07fcc-136">**Sub-domain**</span></span>|<span data-ttu-id="07fcc-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07fcc-137">**TTL**</span></span>|<span data-ttu-id="07fcc-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="07fcc-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07fcc-139">TXT</span><span class="sxs-lookup"><span data-stu-id="07fcc-139">TXT</span></span>  <br/> |<span data-ttu-id="07fcc-140">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="07fcc-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="07fcc-141">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="07fcc-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="07fcc-142">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="07fcc-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="07fcc-143">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="07fcc-143">**Note:** This is an example.</span></span> <span data-ttu-id="07fcc-144">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="07fcc-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="07fcc-145">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="07fcc-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="07fcc-146">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-146">Select **Confirm**.</span></span> 
    
    ![OVH confirmar TXT para verificação](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="07fcc-148">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="07fcc-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="07fcc-149">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="07fcc-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="07fcc-150">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="07fcc-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="07fcc-151">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="07fcc-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="07fcc-152">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="07fcc-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="07fcc-153">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="07fcc-154">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="07fcc-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07fcc-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="07fcc-158">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07fcc-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="07fcc-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="07fcc-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="07fcc-160">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="07fcc-160">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="07fcc-161">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="07fcc-161">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="07fcc-163">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="07fcc-165">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-165">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="07fcc-167">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-167">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="07fcc-169">Selecione **MX**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-169">Select **MX**.</span></span>
    
    ![Tipo de registro MX OVH](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="07fcc-171">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="07fcc-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="07fcc-172">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="07fcc-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="07fcc-173">Por padrão, o OVH usa notação relativa para o destino, que adiciona o nome de domínio ao final do registro de destino.</span><span class="sxs-lookup"><span data-stu-id="07fcc-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="07fcc-174">Para usar a notação absoluta em vez disso, adicione um ponto ao registro de destino conforme mostrado na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="07fcc-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="07fcc-175">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="07fcc-175">**Record type**</span></span>|<span data-ttu-id="07fcc-176">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="07fcc-176">**Sub-domain**</span></span>|<span data-ttu-id="07fcc-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07fcc-177">**TTL**</span></span>|<span data-ttu-id="07fcc-178">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="07fcc-178">**Priority**</span></span>|<span data-ttu-id="07fcc-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="07fcc-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07fcc-180">MX</span><span class="sxs-lookup"><span data-stu-id="07fcc-180">MX</span></span>  <br/> |<span data-ttu-id="07fcc-181">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="07fcc-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="07fcc-182">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="07fcc-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="07fcc-183">10 </span><span class="sxs-lookup"><span data-stu-id="07fcc-183">10</span></span>  <br/> <span data-ttu-id="07fcc-184">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="07fcc-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="07fcc-185">\<domain-key\>. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="07fcc-186">**Observação:** Acesse sua  *\<domain-key\>*  conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07fcc-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="07fcc-187">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="07fcc-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH registro MX para email](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="07fcc-189">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-189">Select **Next**.</span></span>
    
    ![Registro MX OVH Selecione Avançar](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="07fcc-191">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-191">Select **Confirm**.</span></span>
    
    ![Registro MX OVH selecione confirmar](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="07fcc-193">Se houver outros registros MX, exclua todos na lista na página **zona DNS** .</span><span class="sxs-lookup"><span data-stu-id="07fcc-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="07fcc-194">Selecione cada registro e, na coluna **ações** , selecione o ícone lixeira-pode **excluir** .</span><span class="sxs-lookup"><span data-stu-id="07fcc-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH excluir registro MX](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="07fcc-196">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="07fcc-197">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="07fcc-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="07fcc-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="07fcc-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="07fcc-199">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="07fcc-199">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="07fcc-200">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="07fcc-200">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="07fcc-202">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="07fcc-204">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-204">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="07fcc-206">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-206">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="07fcc-208">Selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-208">Select **CNAME**.</span></span>
    
    ![OVH adicionar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="07fcc-210">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="07fcc-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="07fcc-211">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="07fcc-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="07fcc-212">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="07fcc-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="07fcc-213">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="07fcc-213">**Record type**</span></span>|<span data-ttu-id="07fcc-214">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="07fcc-214">**Sub-domain**</span></span>|<span data-ttu-id="07fcc-215">**Destino**</span><span class="sxs-lookup"><span data-stu-id="07fcc-215">**Target**</span></span>|<span data-ttu-id="07fcc-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07fcc-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07fcc-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="07fcc-217">CNAME</span></span>  <br/> |<span data-ttu-id="07fcc-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="07fcc-218">autodiscover</span></span>  <br/> |<span data-ttu-id="07fcc-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="07fcc-220">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="07fcc-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="07fcc-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="07fcc-221">CNAME</span></span>  <br/> |<span data-ttu-id="07fcc-222">sip</span><span class="sxs-lookup"><span data-stu-id="07fcc-222">sip</span></span>  <br/> |<span data-ttu-id="07fcc-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="07fcc-224">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="07fcc-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="07fcc-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="07fcc-225">CNAME</span></span>  <br/> |<span data-ttu-id="07fcc-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="07fcc-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="07fcc-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="07fcc-228">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="07fcc-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="07fcc-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="07fcc-229">CNAME</span></span>  <br/> |<span data-ttu-id="07fcc-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="07fcc-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="07fcc-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="07fcc-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="07fcc-232">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="07fcc-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="07fcc-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="07fcc-233">CNAME</span></span>  <br/> |<span data-ttu-id="07fcc-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="07fcc-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="07fcc-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="07fcc-236">3600 segundos</span><span class="sxs-lookup"><span data-stu-id="07fcc-236">3600 seconds</span></span>  <br/> |
   
    ![Registro CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="07fcc-238">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-238">Select **Next**.</span></span>
    
    ![OVH adicionar valores CNAME e selecionar avançar](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="07fcc-240">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="07fcc-241">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="07fcc-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="07fcc-242">Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="07fcc-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="07fcc-243">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="07fcc-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="07fcc-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="07fcc-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="07fcc-245">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="07fcc-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="07fcc-246">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="07fcc-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="07fcc-247">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07fcc-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="07fcc-248">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="07fcc-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="07fcc-249">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="07fcc-249">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="07fcc-250">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="07fcc-250">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="07fcc-252">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="07fcc-254">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-254">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="07fcc-256">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-256">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="07fcc-258">Selecione **txt**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="07fcc-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="07fcc-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="07fcc-260">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="07fcc-260">**Record type**</span></span>|<span data-ttu-id="07fcc-261">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="07fcc-261">**Sub-domain**</span></span>|<span data-ttu-id="07fcc-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07fcc-262">**TTL**</span></span>|<span data-ttu-id="07fcc-263">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="07fcc-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07fcc-264">TXT</span><span class="sxs-lookup"><span data-stu-id="07fcc-264">TXT</span></span>  <br/> |<span data-ttu-id="07fcc-265">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="07fcc-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="07fcc-266">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="07fcc-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="07fcc-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="07fcc-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="07fcc-268">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="07fcc-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH adicionar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="07fcc-270">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-270">Select **Next**.</span></span>
    
    ![OVH adicionar registro TXT para SPF e selecione avançar](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="07fcc-272">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-272">Select **Confirm**.</span></span>
    
    ![OVH adicionar registro TXT para SPF e Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="07fcc-274">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="07fcc-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="07fcc-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="07fcc-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="07fcc-276">Para começar, vá até a sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/).</span><span class="sxs-lookup"><span data-stu-id="07fcc-276">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="07fcc-277">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="07fcc-277">You'll be prompted to log in.</span></span>
    
    ![Login do OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="07fcc-279">Em **domínios**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="07fcc-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="07fcc-281">Selecione **zona DNS**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-281">Select **DNS zone**.</span></span>
    
    ![OVH selecionar zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="07fcc-283">Selecione **Adicionar uma entrada**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-283">Select **Add an entry**.</span></span>
    
    ![OVH adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="07fcc-285">Selecione **SRV**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-285">Select **SRV**.</span></span>
    
    ![OVH selecionar o tipo de registro SRV](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="07fcc-287">Crie o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="07fcc-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="07fcc-288">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="07fcc-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="07fcc-289">Para atribuir um valor de TTL, escolha **personalizado** na lista suspensa e digite o valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="07fcc-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="07fcc-290">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="07fcc-290">**Record type**</span></span>|<span data-ttu-id="07fcc-291">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="07fcc-291">**Sub-domain**</span></span>|<span data-ttu-id="07fcc-292">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="07fcc-292">**Priority**</span></span>|<span data-ttu-id="07fcc-293">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="07fcc-293">**Weight**</span></span>|<span data-ttu-id="07fcc-294">**Porta**</span><span class="sxs-lookup"><span data-stu-id="07fcc-294">**Port**</span></span>|<span data-ttu-id="07fcc-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07fcc-295">**TTL**</span></span>|<span data-ttu-id="07fcc-296">**Target**</span><span class="sxs-lookup"><span data-stu-id="07fcc-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07fcc-297">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="07fcc-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="07fcc-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="07fcc-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="07fcc-299">100</span><span class="sxs-lookup"><span data-stu-id="07fcc-299">100</span></span>  <br/> |<span data-ttu-id="07fcc-300">1</span><span class="sxs-lookup"><span data-stu-id="07fcc-300">1</span></span>  <br/> |<span data-ttu-id="07fcc-301">443</span><span class="sxs-lookup"><span data-stu-id="07fcc-301">443</span></span>  <br/> |<span data-ttu-id="07fcc-302">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="07fcc-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="07fcc-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="07fcc-304">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="07fcc-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="07fcc-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="07fcc-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="07fcc-306">100</span><span class="sxs-lookup"><span data-stu-id="07fcc-306">100</span></span>  <br/> |<span data-ttu-id="07fcc-307">1</span><span class="sxs-lookup"><span data-stu-id="07fcc-307">1</span></span>  <br/> |<span data-ttu-id="07fcc-308">5061</span><span class="sxs-lookup"><span data-stu-id="07fcc-308">5061</span></span>  <br/> |<span data-ttu-id="07fcc-309">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="07fcc-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="07fcc-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="07fcc-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![Registro SRV OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="07fcc-312">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-312">Select **Next**.</span></span>
    
    ![Registro SRV OVH Selecione Avançar](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="07fcc-314">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="07fcc-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="07fcc-315">Repita as etapas anteriores para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="07fcc-315">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="07fcc-316">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="07fcc-316">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="07fcc-p120">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07fcc-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
