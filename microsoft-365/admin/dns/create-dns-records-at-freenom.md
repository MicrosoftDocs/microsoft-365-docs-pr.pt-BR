---
title: Criar registros DNS no Freenom para Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Freenom para a Microsoft.
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629558"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="40460-103">Criar registros DNS no Freenom para Microsoft</span><span class="sxs-lookup"><span data-stu-id="40460-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="40460-104">[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md) se não encontrar o que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="40460-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="40460-105">O site do Freenom não dá suporte a registros SRV, o que significa que vários recursos do Skype for Business Online e do Outlook Web App não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="40460-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="40460-106">Independentemente do Microsoft Plan que você usa, há limitações de serviço significativas e você pode querer mudar para um provedor de Hospedagem de DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="40460-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="40460-107">Se, apesar das limitações de serviço, você optar por gerenciar seus próprios registros DNS da Microsoft em Freenom, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="40460-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="40460-108">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="40460-108">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="40460-p102">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="40460-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="40460-112">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="40460-112">Add a TXT record for verification</span></span>
<span data-ttu-id="40460-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="40460-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="40460-114">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="40460-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="40460-115">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="40460-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40460-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="40460-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="40460-118">Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="40460-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="40460-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="40460-119">You'll be prompted to log in.</span></span>
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="40460-121">Selecione **Serviços**e, em seguida, selecione **meus domínios**.</span><span class="sxs-lookup"><span data-stu-id="40460-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="40460-123">Para o domínio que você deseja editar, selecione **gerenciar domínio**.</span><span class="sxs-lookup"><span data-stu-id="40460-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="40460-125">Selecione **gerenciar FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="40460-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom gerenciar Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="40460-127">Em **adicionar registro**, na coluna **tipo** , escolha **txt** no menu.</span><span class="sxs-lookup"><span data-stu-id="40460-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom adicionar tipo de registro TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="40460-129">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="40460-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="40460-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="40460-130">**Name**</span></span>|<span data-ttu-id="40460-131">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="40460-131">**Type**</span></span>|<span data-ttu-id="40460-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="40460-132">**TTL**</span></span>|<span data-ttu-id="40460-133">**Destino**</span><span class="sxs-lookup"><span data-stu-id="40460-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40460-134">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="40460-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="40460-135">TXT</span><span class="sxs-lookup"><span data-stu-id="40460-135">TXT</span></span>  <br/> |<span data-ttu-id="40460-136">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="40460-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="40460-138">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="40460-138">**Note:** This is an example.</span></span> <span data-ttu-id="40460-139">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="40460-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="40460-140">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="40460-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom valores TXT para verificação](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="40460-142">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="40460-142">Select **Save Changes**.</span></span>
    
    ![Registro TXT do Freenom salvar alterações](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="40460-144">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="40460-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="40460-145">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="40460-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="40460-146">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="40460-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="40460-147">No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="40460-147">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="40460-148">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="40460-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="40460-149">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="40460-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="40460-150">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="40460-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="40460-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="40460-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="40460-154">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="40460-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="40460-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="40460-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="40460-156">Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="40460-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="40460-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="40460-157">You'll be prompted to log in.</span></span>
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="40460-159">Selecione **Serviços**e, em seguida, selecione **meus domínios**.</span><span class="sxs-lookup"><span data-stu-id="40460-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="40460-161">Para o domínio que você deseja editar, selecione **gerenciar domínio**.</span><span class="sxs-lookup"><span data-stu-id="40460-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="40460-163">Definir o nome serve para o seu domínio para os servidores de nomes padrão do Freenom.</span><span class="sxs-lookup"><span data-stu-id="40460-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="40460-164">Selecione **ferramentas de gerenciamento**e, em seguida, selecione **nameservers**.</span><span class="sxs-lookup"><span data-stu-id="40460-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Configuração de nameservers do Freenom](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="40460-166">Certifique-se de que **usar nameservers padrão** está selecionado e selecione **alterar nameservers**.</span><span class="sxs-lookup"><span data-stu-id="40460-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom alterar nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="40460-168">Selecione **gerenciar FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="40460-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecione Gerenciar Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="40460-170">Em **adicionar registro**, na coluna **tipo** , escolha **MX** no menu.</span><span class="sxs-lookup"><span data-stu-id="40460-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom adicionar tipo de registro MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="40460-172">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="40460-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="40460-173">**Nome**</span><span class="sxs-lookup"><span data-stu-id="40460-173">**Name**</span></span>|<span data-ttu-id="40460-174">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="40460-174">**Type**</span></span>|<span data-ttu-id="40460-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="40460-175">**TTL**</span></span>|<span data-ttu-id="40460-176">**Destino**</span><span class="sxs-lookup"><span data-stu-id="40460-176">**Target**</span></span>|<span data-ttu-id="40460-177">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="40460-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40460-178">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="40460-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="40460-179">Servidor de mensagens (MX)</span><span class="sxs-lookup"><span data-stu-id="40460-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="40460-180">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-181">\<Domain-Key\>. mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="40460-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="40460-182">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40460-182">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="40460-183">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="40460-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="40460-184">10 </span><span class="sxs-lookup"><span data-stu-id="40460-184">10</span></span>  <br/> <span data-ttu-id="40460-185">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="40460-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Registro MX Freenom](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="40460-187">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="40460-187">Select **Save Changes**.</span></span>
    
    ![Registro MX Freenom salvar alterações](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="40460-189">Se houver outros registros MX, exclua todos.</span><span class="sxs-lookup"><span data-stu-id="40460-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="40460-190">Para cada registro, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="40460-190">For each record, select **Delete**.</span></span> <span data-ttu-id="40460-191">Quando a mensagem **você realmente deseja remover essa entrada?** é exibida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="40460-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="40460-192">Adicionar os registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="40460-192">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="40460-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="40460-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="40460-194">Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="40460-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="40460-195">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="40460-195">You'll be prompted to log in.</span></span>
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="40460-197">Selecione **Serviços**e, em seguida, selecione **meus domínios**.</span><span class="sxs-lookup"><span data-stu-id="40460-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="40460-199">Para o domínio que você deseja editar, selecione **gerenciar domínio**.</span><span class="sxs-lookup"><span data-stu-id="40460-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="40460-201">Selecione **gerenciar FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="40460-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecione Gerenciar Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="40460-203">Em **adicionar registro**, na coluna **tipo** , escolha **CNAME** no menu.</span><span class="sxs-lookup"><span data-stu-id="40460-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom adicionar tipo de registro CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="40460-205">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="40460-205">Create the first CNAME record.</span></span> <span data-ttu-id="40460-206">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="40460-206">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="40460-207">**Nome**</span><span class="sxs-lookup"><span data-stu-id="40460-207">**Name**</span></span>|<span data-ttu-id="40460-208">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="40460-208">**Record type**</span></span>|<span data-ttu-id="40460-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="40460-209">**TTL**</span></span>|<span data-ttu-id="40460-210">**Destino**</span><span class="sxs-lookup"><span data-stu-id="40460-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40460-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="40460-211">autodiscover</span></span>  <br/> |<span data-ttu-id="40460-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="40460-212">CNAME</span></span>  <br/> |<span data-ttu-id="40460-213">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="40460-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="40460-215">sip</span><span class="sxs-lookup"><span data-stu-id="40460-215">sip</span></span>  <br/> |<span data-ttu-id="40460-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="40460-216">CNAME</span></span>  <br/> |<span data-ttu-id="40460-217">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="40460-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="40460-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="40460-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="40460-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="40460-220">CNAME</span></span>  <br/> |<span data-ttu-id="40460-221">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="40460-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="40460-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="40460-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="40460-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="40460-224">CNAME</span></span>  <br/> |<span data-ttu-id="40460-225">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="40460-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="40460-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="40460-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="40460-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="40460-228">CNAME</span></span>  <br/> |<span data-ttu-id="40460-229">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="40460-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom valores CNAME](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="40460-232">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="40460-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME salvar alterações](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="40460-234">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="40460-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="40460-235">Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="40460-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="40460-236">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="40460-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="40460-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="40460-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="40460-238">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="40460-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="40460-239">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="40460-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="40460-240">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40460-240">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="40460-241">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="40460-241">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="40460-242">Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="40460-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="40460-243">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="40460-243">You'll be prompted to log in.</span></span>
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="40460-245">Selecione **Serviços**e, em seguida, selecione **meus domínios**.</span><span class="sxs-lookup"><span data-stu-id="40460-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="40460-247">Para o domínio que você deseja editar, selecione **gerenciar domínio**.</span><span class="sxs-lookup"><span data-stu-id="40460-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="40460-249">Selecione **gerenciar FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="40460-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecione Gerenciar Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="40460-251">Em **adicionar registro**, na coluna **tipo** , escolha **txt** no menu.</span><span class="sxs-lookup"><span data-stu-id="40460-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom adicionar tipo de registro TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="40460-253">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="40460-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="40460-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="40460-254">**Name**</span></span>|<span data-ttu-id="40460-255">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="40460-255">**Record type**</span></span>|<span data-ttu-id="40460-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="40460-256">**TTL**</span></span>|<span data-ttu-id="40460-257">**Destino**</span><span class="sxs-lookup"><span data-stu-id="40460-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40460-258">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="40460-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="40460-259">TXT</span><span class="sxs-lookup"><span data-stu-id="40460-259">TXT</span></span>  <br/> |<span data-ttu-id="40460-260">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="40460-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="40460-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="40460-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="40460-262">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="40460-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom valores TXT para SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="40460-264">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="40460-264">Select **Save Changes**.</span></span>
    
    ![Freenom registro TXT para alterações de salvamento de SPF](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

