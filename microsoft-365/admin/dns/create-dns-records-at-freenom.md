---
title: Criar registros DNS no Freenom para a Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Freenom para Microsoft.
ms.openlocfilehash: 8332d63acf34a7f999b549467494b7819cebf092
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910349"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="0c059-103">Criar registros DNS no Freenom para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c059-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="0c059-104">[Verifique as Perguntas Frequentes de ](../setup/domains-faq.yml) Domínios se você não encontrar o que está procurando.</span><span class="sxs-lookup"><span data-stu-id="0c059-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="0c059-105">O site do Freenom não dá suporte a registros SRV, o que significa que vários recursos do Skype for Business Online e do Outlook Web App não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="0c059-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="0c059-106">Não importa qual plano da Microsoft você use, há limitações significativas de serviço e talvez você queira alternar para um provedor de hospedagem DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="0c059-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="0c059-107">Se, apesar das limitações de serviço, você optar por gerenciar seus próprios registros DNS da Microsoft no Freenom, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="0c059-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="0c059-p102">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c059-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0c059-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="0c059-111">Add a TXT record for verification</span></span>
<span data-ttu-id="0c059-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="0c059-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="0c059-p103">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="0c059-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c059-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="0c059-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0c059-117">Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="0c059-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0c059-118">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0c059-118">You'll be prompted to log in.</span></span>
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0c059-120">Selecione **Serviços** e selecione **Meus Domínios.**</span><span class="sxs-lookup"><span data-stu-id="0c059-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0c059-122">Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.</span><span class="sxs-lookup"><span data-stu-id="0c059-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0c059-124">Selecione **Gerenciar DNS do Freenom**.</span><span class="sxs-lookup"><span data-stu-id="0c059-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="0c059-126">Em **Adicionar Registro**, na coluna **Tipo,** escolha **TXT** no menu.</span><span class="sxs-lookup"><span data-stu-id="0c059-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="0c059-128">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="0c059-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="0c059-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c059-129">**Name**</span></span>|<span data-ttu-id="0c059-130">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0c059-130">**Type**</span></span>|<span data-ttu-id="0c059-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c059-131">**TTL**</span></span>|<span data-ttu-id="0c059-132">**Target**</span><span class="sxs-lookup"><span data-stu-id="0c059-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c059-133">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="0c059-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="0c059-134">TXT</span><span class="sxs-lookup"><span data-stu-id="0c059-134">TXT</span></span>  <br/> |<span data-ttu-id="0c059-135">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-136">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="0c059-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="0c059-137">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0c059-137">**Note:** This is an example.</span></span> <span data-ttu-id="0c059-138">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="0c059-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="0c059-139">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="0c059-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Valores TXT do Freenom para verificação](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="0c059-141">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0c059-141">Select **Save Changes**.</span></span>
    
    ![Registro TXT do Freenom Salvar Alterações](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="0c059-143">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="0c059-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0c059-144">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="0c059-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0c059-145">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="0c059-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0c059-146">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="0c059-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0c059-147">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="0c059-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0c059-148">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="0c059-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0c059-149">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="0c059-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0c059-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c059-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0c059-153">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c059-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0c059-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="0c059-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="0c059-155">Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="0c059-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0c059-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0c059-156">You'll be prompted to log in.</span></span>
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0c059-158">Selecione **Serviços** e selecione **Meus Domínios.**</span><span class="sxs-lookup"><span data-stu-id="0c059-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0c059-160">Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.</span><span class="sxs-lookup"><span data-stu-id="0c059-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0c059-162">De definir o nome serve para o seu domínio para os servidores de nome padrão do Freenom.</span><span class="sxs-lookup"><span data-stu-id="0c059-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="0c059-163">Selecione **Ferramentas de Gerenciamento** e selecione **Nameservers**.</span><span class="sxs-lookup"><span data-stu-id="0c059-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Configuração de Nameservers freenom](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="0c059-165">**Certifique-se de usar os nameservers padrão** selecionados e selecione Alterar **Nameservers**.</span><span class="sxs-lookup"><span data-stu-id="0c059-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="0c059-167">Selecione **Gerenciar DNS do Freenom**.</span><span class="sxs-lookup"><span data-stu-id="0c059-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecione Gerenciar DNS do Freenom](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="0c059-169">Em **Adicionar Registro**, na coluna **Tipo,** escolha **MX** no menu.</span><span class="sxs-lookup"><span data-stu-id="0c059-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="0c059-171">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0c059-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="0c059-172">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c059-172">**Name**</span></span>|<span data-ttu-id="0c059-173">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0c059-173">**Type**</span></span>|<span data-ttu-id="0c059-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c059-174">**TTL**</span></span>|<span data-ttu-id="0c059-175">**Target**</span><span class="sxs-lookup"><span data-stu-id="0c059-175">**Target**</span></span>|<span data-ttu-id="0c059-176">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="0c059-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c059-177">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="0c059-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="0c059-178">Servidor de mensagens (MX)</span><span class="sxs-lookup"><span data-stu-id="0c059-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="0c059-179">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-180">\<domain-key\>.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0c059-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0c059-181">**Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c059-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="0c059-182">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="0c059-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0c059-183">10 </span><span class="sxs-lookup"><span data-stu-id="0c059-183">10</span></span>  <br/> <span data-ttu-id="0c059-184">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="0c059-184">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
   ![Registro MX do Freenom](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="0c059-186">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0c059-186">Select **Save Changes**.</span></span>
    
    ![Registro MX do Freenom Salvar Alterações](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="0c059-188">Se houver outros registros MX, exclua-os todos.</span><span class="sxs-lookup"><span data-stu-id="0c059-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="0c059-189">Para cada registro, selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0c059-189">For each record, select **Delete**.</span></span> <span data-ttu-id="0c059-190">Quando a mensagem **Você realmente deseja remover essa entrada?** é exibida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c059-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0c059-191">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c059-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0c059-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="0c059-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="0c059-193">Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="0c059-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0c059-194">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0c059-194">You'll be prompted to log in.</span></span>
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0c059-196">Selecione **Serviços** e selecione **Meus Domínios.**</span><span class="sxs-lookup"><span data-stu-id="0c059-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0c059-198">Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.</span><span class="sxs-lookup"><span data-stu-id="0c059-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0c059-200">Selecione **Gerenciar DNS do Freenom**.</span><span class="sxs-lookup"><span data-stu-id="0c059-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecione Gerenciar DNS do Freenom](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="0c059-202">Em **Adicionar Registro**, na coluna **Tipo,** escolha **CNAME** no menu.</span><span class="sxs-lookup"><span data-stu-id="0c059-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="0c059-204">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="0c059-204">Create the first CNAME record.</span></span> <span data-ttu-id="0c059-205">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0c059-205">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="0c059-206">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c059-206">**Name**</span></span>|<span data-ttu-id="0c059-207">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="0c059-207">**Record type**</span></span>|<span data-ttu-id="0c059-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c059-208">**TTL**</span></span>|<span data-ttu-id="0c059-209">**Target**</span><span class="sxs-lookup"><span data-stu-id="0c059-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c059-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0c059-210">autodiscover</span></span>  <br/> |<span data-ttu-id="0c059-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c059-211">CNAME</span></span>  <br/> |<span data-ttu-id="0c059-212">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0c059-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="0c059-214">sip</span><span class="sxs-lookup"><span data-stu-id="0c059-214">sip</span></span>  <br/> |<span data-ttu-id="0c059-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c059-215">CNAME</span></span>  <br/> |<span data-ttu-id="0c059-216">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c059-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0c059-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0c059-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0c059-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c059-219">CNAME</span></span>  <br/> |<span data-ttu-id="0c059-220">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c059-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0c059-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0c059-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0c059-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c059-223">CNAME</span></span>  <br/> |<span data-ttu-id="0c059-224">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0c059-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="0c059-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0c059-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0c059-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="0c059-227">CNAME</span></span>  <br/> |<span data-ttu-id="0c059-228">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0c059-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Valores CNAME do Freenom](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="0c059-231">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0c059-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Salvar Alterações](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="0c059-233">Repita as etapas anteriores para criar os outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="0c059-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="0c059-234">Para cada registro, digite ou copie e copie os valores da próxima linha da tabela acima nas caixas desse registro.</span><span class="sxs-lookup"><span data-stu-id="0c059-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0c059-235">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="0c059-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0c059-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="0c059-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c059-237">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="0c059-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0c059-238">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="0c059-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0c059-239">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c059-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0c059-240">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="0c059-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="0c059-241">Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="0c059-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0c059-242">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0c059-242">You'll be prompted to log in.</span></span>
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0c059-244">Selecione **Serviços** e selecione **Meus Domínios.**</span><span class="sxs-lookup"><span data-stu-id="0c059-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0c059-246">Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.</span><span class="sxs-lookup"><span data-stu-id="0c059-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0c059-248">Selecione **Gerenciar DNS do Freenom**.</span><span class="sxs-lookup"><span data-stu-id="0c059-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecione Gerenciar DNS do Freenom](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="0c059-250">Em **Adicionar Registro**, na coluna **Tipo,** escolha **TXT** no menu.</span><span class="sxs-lookup"><span data-stu-id="0c059-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="0c059-252">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="0c059-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="0c059-253">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0c059-253">**Name**</span></span>|<span data-ttu-id="0c059-254">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="0c059-254">**Record type**</span></span>|<span data-ttu-id="0c059-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0c059-255">**TTL**</span></span>|<span data-ttu-id="0c059-256">**Target**</span><span class="sxs-lookup"><span data-stu-id="0c059-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c059-257">(deixar em branco)</span><span class="sxs-lookup"><span data-stu-id="0c059-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="0c059-258">TXT</span><span class="sxs-lookup"><span data-stu-id="0c059-258">TXT</span></span>  <br/> |<span data-ttu-id="0c059-259">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="0c059-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0c059-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0c059-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0c059-261">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="0c059-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Valores TXT do Freenom para SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="0c059-263">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0c059-263">Select **Save Changes**.</span></span>
    
    ![Registro TXT do Freenom para Alterações de Salvar SPF](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
