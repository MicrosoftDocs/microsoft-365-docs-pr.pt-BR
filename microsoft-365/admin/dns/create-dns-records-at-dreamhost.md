---
title: Criar registros DNS no Dreamhost para o Office 365
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Dreamhost para o Office 365.
ms.openlocfilehash: 1997af6e14dcb6a118dfcc3558037ed56d07ea87
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211782"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="029a2-103">Criar registros DNS no Dreamhost para o Office 365</span><span class="sxs-lookup"><span data-stu-id="029a2-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="029a2-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="029a2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="029a2-105">Se o DreamHost for seu provedor de Hospedagem de DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Lync e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="029a2-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="029a2-106">Depois que você adicionar esses registros no DreamHost, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="029a2-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="029a2-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="029a2-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="029a2-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="029a2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="029a2-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="029a2-111">Add a TXT record for verification</span></span>
<span data-ttu-id="029a2-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="029a2-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="029a2-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="029a2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="029a2-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="029a2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="029a2-117">Para começar, vá até a sua página de domínios no DreamHost usando [este link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="029a2-117">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="029a2-118">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="029a2-118">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="029a2-120">Na página **painel** , selecione **domínios**e, em seguida, **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="029a2-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="029a2-122">Na página **gerenciar domínios** , na seção **domínio** , selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="029a2-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="029a2-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="029a2-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="029a2-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="029a2-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="029a2-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="029a2-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="029a2-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="029a2-127">**Name**</span></span>|<span data-ttu-id="029a2-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="029a2-128">**Type**</span></span>|<span data-ttu-id="029a2-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="029a2-129">**Value**</span></span>|<span data-ttu-id="029a2-130">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="029a2-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="029a2-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="029a2-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="029a2-132">TXT</span><span class="sxs-lookup"><span data-stu-id="029a2-132">TXT</span></span>  <br/> |<span data-ttu-id="029a2-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="029a2-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="029a2-134">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="029a2-134">**Note:** This is an example.</span></span> <span data-ttu-id="029a2-135">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="029a2-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="029a2-136">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="029a2-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="029a2-137">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="029a2-139">Selecione **adicionar registro agora!**</span><span class="sxs-lookup"><span data-stu-id="029a2-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="029a2-141">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="029a2-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="029a2-142">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="029a2-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="029a2-143">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="029a2-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="029a2-144">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="029a2-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="029a2-145">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="029a2-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="029a2-146">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="029a2-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="029a2-147">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="029a2-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="029a2-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="029a2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="029a2-151">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="029a2-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="029a2-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="029a2-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="029a2-153">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="029a2-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="029a2-154">Para começar, vá até a sua página de domínios no DreamHost usando [este link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="029a2-154">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="029a2-155">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="029a2-155">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="029a2-157">Na página **painel** , selecione **email**e, em seguida, **personalizado MX**.</span><span class="sxs-lookup"><span data-stu-id="029a2-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="029a2-159">Na seção **gerenciar entrega de email** , na coluna **ações** , selecione **Editar** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="029a2-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="029a2-161">Na seção **registro MX personalizado** , nas caixas do novo registro, digite ou copie e cole os seguintes valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="029a2-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="029a2-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="029a2-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="029a2-163">(Se houver outros registros MX existentes, marque os registros a serem excluídos.)</span><span class="sxs-lookup"><span data-stu-id="029a2-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="029a2-164">**Registro MX (obrigatório)**</span><span class="sxs-lookup"><span data-stu-id="029a2-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="029a2-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="029a2-166">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="029a2-p108">O 0 é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="029a2-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="029a2-169">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="029a2-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="029a2-170">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="029a2-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="029a2-172">Selecione **alterar este domínio para usar registros MX personalizados agora!**</span><span class="sxs-lookup"><span data-stu-id="029a2-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="029a2-174">Se houver outros registros MX existentes, exclua cada registro selecionando a entrada e pressionando a tecla **delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="029a2-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="029a2-176">Se você tiver excluído qualquer registro, selecione **atualizar seus registros MX personalizados agora!**</span><span class="sxs-lookup"><span data-stu-id="029a2-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="029a2-178">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="029a2-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="029a2-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="029a2-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="029a2-180">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="029a2-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="029a2-181">Para começar, vá até a sua página de domínios no DreamHost usando [este link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="029a2-181">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="029a2-182">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="029a2-182">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="029a2-184">Na página **painel** , selecione **domínios**e, em seguida, **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="029a2-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="029a2-186">Na página **gerenciar domínios** , na seção **domínio** , selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="029a2-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="029a2-188">Na seção **Adicionar um registro DNS personalizado** , nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="029a2-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="029a2-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="029a2-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="029a2-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="029a2-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="029a2-191">**Nome**</span><span class="sxs-lookup"><span data-stu-id="029a2-191">**Name**</span></span>|<span data-ttu-id="029a2-192">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="029a2-192">**Type**</span></span>|<span data-ttu-id="029a2-193">**Valor**</span><span class="sxs-lookup"><span data-stu-id="029a2-193">**Value**</span></span>|<span data-ttu-id="029a2-194">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="029a2-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="029a2-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="029a2-195">autodiscover</span></span>  <br/> |<span data-ttu-id="029a2-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="029a2-196">CNAME</span></span>  <br/> |<span data-ttu-id="029a2-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="029a2-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-199">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="029a2-200">sip</span><span class="sxs-lookup"><span data-stu-id="029a2-200">sip</span></span>  <br/> |<span data-ttu-id="029a2-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="029a2-201">CNAME</span></span>  <br/> |<span data-ttu-id="029a2-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="029a2-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-204">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="029a2-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="029a2-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="029a2-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="029a2-206">CNAME</span></span>  <br/> |<span data-ttu-id="029a2-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="029a2-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-209">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="029a2-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="029a2-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="029a2-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="029a2-211">CNAME</span></span>  <br/> |<span data-ttu-id="029a2-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="029a2-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="029a2-213">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-214">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="029a2-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="029a2-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="029a2-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="029a2-216">CNAME</span></span>  <br/> |<span data-ttu-id="029a2-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="029a2-218">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-219">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="029a2-221">Selecione **adicionar registro agora!**</span><span class="sxs-lookup"><span data-stu-id="029a2-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="029a2-223">Usando as duas etapas anteriores e os valores das outras cinco linhas na tabela, adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="029a2-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="029a2-224">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="029a2-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="029a2-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="029a2-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="029a2-226">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="029a2-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="029a2-227">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="029a2-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="029a2-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="029a2-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="029a2-229">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="029a2-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="029a2-230">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="029a2-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="029a2-231">Para começar, vá até a sua página de domínios no DreamHost usando [este link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="029a2-231">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="029a2-232">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="029a2-232">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="029a2-234">Na página **painel** , selecione **domínios**e, em seguida, **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="029a2-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="029a2-236">Na página **gerenciar domínios** , na seção **domínio** , selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="029a2-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="029a2-238">Na seção **Adicionar um registro DNS personalizado** , nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="029a2-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="029a2-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="029a2-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="029a2-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="029a2-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="029a2-241">**Nome**</span><span class="sxs-lookup"><span data-stu-id="029a2-241">**Name**</span></span>|<span data-ttu-id="029a2-242">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="029a2-242">**Type**</span></span>|<span data-ttu-id="029a2-243">**Valor**</span><span class="sxs-lookup"><span data-stu-id="029a2-243">**Value**</span></span>|<span data-ttu-id="029a2-244">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="029a2-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="029a2-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="029a2-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="029a2-246">TXT</span><span class="sxs-lookup"><span data-stu-id="029a2-246">TXT</span></span>  <br/> |<span data-ttu-id="029a2-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="029a2-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="029a2-248">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="029a2-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="029a2-249">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="029a2-251">Selecione **adicionar registro agora!**</span><span class="sxs-lookup"><span data-stu-id="029a2-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="029a2-253">Usando as duas etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="029a2-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="029a2-254">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="029a2-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="029a2-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="029a2-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="029a2-256">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="029a2-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="029a2-257">Para começar, vá até a sua página de domínios no DreamHost usando [este link](https://panel.dreamhost.com/).</span><span class="sxs-lookup"><span data-stu-id="029a2-257">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="029a2-258">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="029a2-258">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="029a2-260">Na página **painel** , selecione **domínios**e, em seguida, **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="029a2-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="029a2-262">Na página **gerenciar domínios** , na seção **domínio** , selecione **DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="029a2-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="029a2-264">Na seção **Adicionar um registro DNS personalizado** , nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="029a2-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="029a2-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="029a2-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="029a2-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="029a2-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="029a2-267">**Nome**</span><span class="sxs-lookup"><span data-stu-id="029a2-267">**Name**</span></span>|<span data-ttu-id="029a2-268">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="029a2-268">**Type**</span></span>|<span data-ttu-id="029a2-269">**Valor**</span><span class="sxs-lookup"><span data-stu-id="029a2-269">**Value**</span></span>|<span data-ttu-id="029a2-270">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="029a2-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="029a2-271">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="029a2-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="029a2-272">SRV</span><span class="sxs-lookup"><span data-stu-id="029a2-272">SRV</span></span>  <br/> |<span data-ttu-id="029a2-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="029a2-273">100 1 443</span></span>  <br/> <span data-ttu-id="029a2-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="029a2-275">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-276">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="029a2-277">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="029a2-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="029a2-278">SRV</span><span class="sxs-lookup"><span data-stu-id="029a2-278">SRV</span></span>  <br/> |<span data-ttu-id="029a2-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="029a2-279">100 1 5061</span></span>  <br/> <span data-ttu-id="029a2-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="029a2-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="029a2-281">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="029a2-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="029a2-282">(Esse campo é opcional.)</span><span class="sxs-lookup"><span data-stu-id="029a2-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="029a2-284">Selecione **adicionar registro agora!**.</span><span class="sxs-lookup"><span data-stu-id="029a2-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="029a2-286">Usando as duas etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="029a2-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="029a2-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="029a2-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
