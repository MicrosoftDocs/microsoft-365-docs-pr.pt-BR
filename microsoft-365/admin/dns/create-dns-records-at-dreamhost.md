---
title: Criar registros DNS noHost da Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços noHost da Microsoft.
ms.openlocfilehash: 2faf7cae1fd9a0f9308e303c0588958e56b223e1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658118"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="1c285-103">Criar registros DNS noHost da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1c285-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="1c285-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="1c285-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1c285-105">Se oHosthost for seu provedor de hospedagem DNS, siga as etapas neste artigo para verificar seu domínio e configurar registros DNS para email, Lync e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="1c285-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="1c285-106">Depois que você adicionar esses registros noHosthost, seu domínio será definido para funcionar com os serviços Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c285-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="1c285-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1c285-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1c285-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="1c285-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1c285-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1c285-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1c285-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="1c285-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c285-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="1c285-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1c285-116">To get started, go to your domains page atHost by using [this link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="1c285-116">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="1c285-117">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="1c285-117">You'll be prompted to Sign in.</span></span>
    
    ![Host-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="1c285-119">Na página **Painel,** selecione **Domínios** e **Gerencie Domínios.**</span><span class="sxs-lookup"><span data-stu-id="1c285-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Host-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="1c285-121">Na página **Gerenciar Domínios,** na seção **Domínio,** selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="1c285-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Host-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="1c285-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c285-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1c285-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="1c285-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="1c285-125">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="1c285-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c285-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="1c285-126">**Name**</span></span>|<span data-ttu-id="1c285-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c285-127">**Type**</span></span>|<span data-ttu-id="1c285-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1c285-128">**Value**</span></span>|<span data-ttu-id="1c285-129">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="1c285-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1c285-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1c285-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1c285-131">TXT</span><span class="sxs-lookup"><span data-stu-id="1c285-131">TXT</span></span>  <br/> |<span data-ttu-id="1c285-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1c285-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1c285-133">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="1c285-133">**Note:** This is an example.</span></span> <span data-ttu-id="1c285-134">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="1c285-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1c285-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="1c285-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1c285-136">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-136">(This field is optional.)</span></span>  <br/> |
   
   ![Host-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="1c285-138">Selecione **Adicionar Registro Agora!**</span><span class="sxs-lookup"><span data-stu-id="1c285-138">Select **Add Record Now!**</span></span>
    
    ![Host-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="1c285-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="1c285-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1c285-141">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="1c285-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1c285-142">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="1c285-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1c285-143">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="1c285-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1c285-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="1c285-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1c285-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="1c285-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1c285-146">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="1c285-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1c285-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1c285-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1c285-150">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c285-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1c285-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1c285-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1c285-152">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1c285-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="1c285-153">To get started, go to your domains page atHost by using [this link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="1c285-153">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="1c285-154">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="1c285-154">You'll be prompted to Sign in.</span></span>
    
    ![Host-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="1c285-156">Na página **Painel,** selecione **Email** e, em **seguida, MX Personalizado.**</span><span class="sxs-lookup"><span data-stu-id="1c285-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Host-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="1c285-158">Na seção **Gerenciar Entrega de Email,** na coluna **Ações,** selecione **Editar** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="1c285-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Host-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="1c285-160">Na seção **Registro MX Personalizado,** nas caixas do novo registro, digite ou copie e copie e copie os seguintes valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1c285-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="1c285-161">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="1c285-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="1c285-162">(Se houver outros registros MX existentes, marque esses registros a serem excluídos.)</span><span class="sxs-lookup"><span data-stu-id="1c285-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="1c285-163">**Registro MX (obrigatório)**</span><span class="sxs-lookup"><span data-stu-id="1c285-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="1c285-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1c285-165">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1c285-p108">O 0 é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="1c285-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="1c285-168">**Observação:** Obter o  *\<domain-key\>*  seu da sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c285-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1c285-169">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="1c285-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Host-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="1c285-171">Selecione **Alterar este domínio para usar registros MX personalizados agora!**</span><span class="sxs-lookup"><span data-stu-id="1c285-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Host-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="1c285-173">Se houver outros registros MX, exclua cada registro selecionando a entrada e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="1c285-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Host-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="1c285-175">Se você excluiu algum registro, selecione **Atualizar seus registros MX personalizados agora!**</span><span class="sxs-lookup"><span data-stu-id="1c285-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Host-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1c285-177">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1c285-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1c285-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1c285-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1c285-179">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1c285-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="1c285-180">To get started, go to your domains page atHost by using [this link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="1c285-180">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="1c285-181">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="1c285-181">You'll be prompted to Sign in.</span></span>
    
    ![Host-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="1c285-183">Na página **Painel,** selecione **Domínios** e **Gerencie Domínios.**</span><span class="sxs-lookup"><span data-stu-id="1c285-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Host-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="1c285-185">Na página **Gerenciar Domínios,** na seção **Domínio,** selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="1c285-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Host-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="1c285-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span><span class="sxs-lookup"><span data-stu-id="1c285-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="1c285-188">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="1c285-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="1c285-189">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="1c285-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c285-190">**Name**</span><span class="sxs-lookup"><span data-stu-id="1c285-190">**Name**</span></span>|<span data-ttu-id="1c285-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c285-191">**Type**</span></span>|<span data-ttu-id="1c285-192">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1c285-192">**Value**</span></span>|<span data-ttu-id="1c285-193">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="1c285-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1c285-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1c285-194">autodiscover</span></span>  <br/> |<span data-ttu-id="1c285-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c285-195">CNAME</span></span>  <br/> |<span data-ttu-id="1c285-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1c285-197">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-198">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="1c285-199">sip</span><span class="sxs-lookup"><span data-stu-id="1c285-199">sip</span></span>  <br/> |<span data-ttu-id="1c285-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c285-200">CNAME</span></span>  <br/> |<span data-ttu-id="1c285-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1c285-202">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-203">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="1c285-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1c285-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1c285-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c285-205">CNAME</span></span>  <br/> |<span data-ttu-id="1c285-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1c285-207">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-208">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="1c285-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1c285-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1c285-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c285-210">CNAME</span></span>  <br/> |<span data-ttu-id="1c285-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1c285-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1c285-212">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-213">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="1c285-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1c285-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1c285-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="1c285-215">CNAME</span></span>  <br/> |<span data-ttu-id="1c285-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1c285-217">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-218">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-218">(This field is optional.)</span></span>  <br/> |
   
    ![Host-BP-Configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="1c285-220">Selecione **Adicionar Registro Agora!**</span><span class="sxs-lookup"><span data-stu-id="1c285-220">Select **Add Record Now!**</span></span>
    
    ![Host-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="1c285-222">Usando as duas etapas anteriores e os valores das outras cinco linhas na tabela, adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1c285-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1c285-223">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="1c285-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1c285-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1c285-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c285-225">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="1c285-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1c285-226">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="1c285-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1c285-227">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c285-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1c285-228">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="1c285-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="1c285-229">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1c285-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="1c285-230">To get started, go to your domains page atHost by using [this link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="1c285-230">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="1c285-231">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="1c285-231">You'll be prompted to Sign in.</span></span>
    
    ![Host-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="1c285-233">Na página **Painel,** selecione **Domínios** e **Gerencie Domínios.**</span><span class="sxs-lookup"><span data-stu-id="1c285-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Host-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="1c285-235">Na página **Gerenciar Domínios,** na seção **Domínio,** selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="1c285-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Host-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="1c285-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span><span class="sxs-lookup"><span data-stu-id="1c285-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="1c285-238">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="1c285-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="1c285-239">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="1c285-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c285-240">**Name**</span><span class="sxs-lookup"><span data-stu-id="1c285-240">**Name**</span></span>|<span data-ttu-id="1c285-241">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c285-241">**Type**</span></span>|<span data-ttu-id="1c285-242">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1c285-242">**Value**</span></span>|<span data-ttu-id="1c285-243">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="1c285-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1c285-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1c285-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1c285-245">TXT</span><span class="sxs-lookup"><span data-stu-id="1c285-245">TXT</span></span>  <br/> |<span data-ttu-id="1c285-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1c285-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1c285-247">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="1c285-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1c285-248">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-248">(This field is optional.)</span></span>  <br/> |
   
   ![Host-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="1c285-250">Selecione **Adicionar Registro Agora!**</span><span class="sxs-lookup"><span data-stu-id="1c285-250">Select **Add Record Now!**</span></span>
    
    ![Host-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="1c285-252">Usando as duas etapas anteriores e os valores da segunda linha na tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="1c285-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1c285-253">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1c285-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1c285-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1c285-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1c285-255">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1c285-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="1c285-256">To get started, go to your domains page atHost by using [this link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="1c285-256">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="1c285-257">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="1c285-257">You'll be prompted to Sign in.</span></span>
    
    ![Host-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="1c285-259">Na página **Painel,** selecione **Domínios** e **Gerencie Domínios.**</span><span class="sxs-lookup"><span data-stu-id="1c285-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Host-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="1c285-261">Na página **Gerenciar Domínios,** na seção **Domínio,** selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="1c285-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Host-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="1c285-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span><span class="sxs-lookup"><span data-stu-id="1c285-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="1c285-264">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="1c285-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="1c285-265">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="1c285-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1c285-266">**Name**</span><span class="sxs-lookup"><span data-stu-id="1c285-266">**Name**</span></span>|<span data-ttu-id="1c285-267">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1c285-267">**Type**</span></span>|<span data-ttu-id="1c285-268">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1c285-268">**Value**</span></span>|<span data-ttu-id="1c285-269">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="1c285-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1c285-270">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1c285-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="1c285-271">SRV</span><span class="sxs-lookup"><span data-stu-id="1c285-271">SRV</span></span>  <br/> |<span data-ttu-id="1c285-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="1c285-272">100 1 443</span></span>  <br/> <span data-ttu-id="1c285-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1c285-274">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-275">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="1c285-276">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1c285-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1c285-277">SRV</span><span class="sxs-lookup"><span data-stu-id="1c285-277">SRV</span></span>  <br/> |<span data-ttu-id="1c285-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="1c285-278">100 1 5061</span></span>  <br/> <span data-ttu-id="1c285-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1c285-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="1c285-280">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="1c285-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1c285-281">(Este campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="1c285-281">(This field is optional.)</span></span>  <br/> |
   
    ![Host-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="1c285-283">Selecione **Adicionar Registro Agora!**.</span><span class="sxs-lookup"><span data-stu-id="1c285-283">Select **Add Record Now!**.</span></span>
    
    ![Host-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="1c285-285">Usando as duas etapas anteriores e os valores da segunda linha na tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="1c285-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="1c285-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1c285-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
