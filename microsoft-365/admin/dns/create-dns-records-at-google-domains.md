---
title: Criar registros DNS no site Google Domains para o Office 365
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Lync e outros serviços no Google Domains for Office 365.
ms.openlocfilehash: c59a3d63797f20b0d3a42647eb68d7699ed63450
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238882"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="cdf1e-103">Criar registros DNS no site Google Domains para o Office 365</span><span class="sxs-lookup"><span data-stu-id="cdf1e-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="cdf1e-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cdf1e-105">Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="cdf1e-106">Depois que você adicionar esses registros no Google Domains, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cdf1e-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="cdf1e-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdf1e-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cdf1e-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cdf1e-110">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cdf1e-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cdf1e-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="cdf1e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cdf1e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cdf1e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cdf1e-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdf1e-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cdf1e-p104">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="cdf1e-120">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="cdf1e-121">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="cdf1e-122">Na página **meus domínios** , localize o domínio que você deseja usar com o Office 365 e selecione o link **gerenciar** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="cdf1e-123">No painel de navegação à esquerda, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="cdf1e-124">Na seção \* \* registros de recursos personalizados \* \*, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cdf1e-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cdf1e-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdf1e-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-127">**Name**</span></span> <br/> |<span data-ttu-id="cdf1e-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-128">**Type**</span></span> <br/> |<span data-ttu-id="cdf1e-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-129">**TTL**</span></span> <br/> |<span data-ttu-id="cdf1e-130">**Dados**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="cdf1e-131">TXT</span><span class="sxs-lookup"><span data-stu-id="cdf1e-131">TXT</span></span>  <br/> |<span data-ttu-id="cdf1e-132">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-132">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cdf1e-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cdf1e-134">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-134">**Note:** This is an example.</span></span> <span data-ttu-id="cdf1e-135">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cdf1e-136">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="cdf1e-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="cdf1e-137">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="cdf1e-138">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cdf1e-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cdf1e-140">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cdf1e-141">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="cdf1e-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cdf1e-142">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cdf1e-143">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cdf1e-144">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cdf1e-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cdf1e-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cdf1e-147">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cdf1e-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cdf1e-148">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="cdf1e-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cdf1e-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cdf1e-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cdf1e-p108">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="cdf1e-153">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="cdf1e-154">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="cdf1e-155">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdf1e-p109">Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta. Os registros MX do G Suite impedem que você adicione outros registros MX, incluindo aqueles necessários para o Office 365. Excluir os registros do G Suite não exclui sua conta do G Suite. Para excluir os registros MX do G Suite, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="cdf1e-160">Na seção **registros sintéticos** , na área **G Suite** , selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="cdf1e-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-161">(You may have to scroll down.)</span></span>
    
    ![Selecione Excluir na seção registros sintéticos](../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="cdf1e-163">Selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-163">Select **Delete**.</span></span>
    
    ![Selecione Excluir](../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="cdf1e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cdf1e-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cdf1e-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cdf1e-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-168">**Name**</span></span>|<span data-ttu-id="cdf1e-169">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-169">**Type**</span></span>|<span data-ttu-id="cdf1e-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-170">**TTL**</span></span>|<span data-ttu-id="cdf1e-171">**Dados**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cdf1e-172">MX</span><span class="sxs-lookup"><span data-stu-id="cdf1e-172">MX</span></span>  <br/> |<span data-ttu-id="cdf1e-173">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-173">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-174">0  *\<chave-de-domínio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cdf1e-175">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cdf1e-p110">O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  </span><span class="sxs-lookup"><span data-stu-id="cdf1e-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cdf1e-178">**Observação:** Obtenha sua \< *chave* \> de domínio de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="cdf1e-179">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="cdf1e-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="cdf1e-180">Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="cdf1e-182">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-182">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="cdf1e-184">Se houver outros registros MX personalizados, remova-os:</span><span class="sxs-lookup"><span data-stu-id="cdf1e-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="cdf1e-185">Selecione **Editar** na linha do registro MX.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Selecionar Editar na linha do registro MX](../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="cdf1e-187">Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **dados** e, em seguida, pressione a tecla **delete** no teclado para excluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="cdf1e-188">Continue até excluir a entrada **Dados** para cada um dos outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="cdf1e-190">Quando tiver excluído a entrada de **dados** de cada um dos outros registros MX, selecione **salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Selecione salvar](../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cdf1e-192">Adicionar os cinco registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="cdf1e-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="cdf1e-193">Para começar, vá até a sua página [Google Domains] (https://domains.google.com/registrar) e entre.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="cdf1e-194">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cdf1e-195">Adicione o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="cdf1e-196">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="cdf1e-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cdf1e-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cdf1e-199">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-199">**Name**</span></span>|<span data-ttu-id="cdf1e-200">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-200">**Type**</span></span>|<span data-ttu-id="cdf1e-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-201">**TTL**</span></span>|<span data-ttu-id="cdf1e-202">**Dados**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdf1e-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cdf1e-203">autodiscover</span></span>  <br/> |<span data-ttu-id="cdf1e-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdf1e-204">CNAME</span></span>  <br/> |<span data-ttu-id="cdf1e-205">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-205">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cdf1e-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cdf1e-208">sip</span><span class="sxs-lookup"><span data-stu-id="cdf1e-208">sip</span></span>  <br/> |<span data-ttu-id="cdf1e-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdf1e-209">CNAME</span></span>  <br/> |<span data-ttu-id="cdf1e-210">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-210">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cdf1e-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cdf1e-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cdf1e-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cdf1e-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdf1e-214">CNAME</span></span>  <br/> |<span data-ttu-id="cdf1e-215">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-215">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cdf1e-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cdf1e-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cdf1e-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cdf1e-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdf1e-219">CNAME</span></span>  <br/> |<span data-ttu-id="cdf1e-220">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-220">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cdf1e-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cdf1e-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cdf1e-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cdf1e-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdf1e-224">CNAME</span></span>  <br/> |<span data-ttu-id="cdf1e-225">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-225">1H</span></span>  <br/> |<span data-ttu-id="cdf1e-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cdf1e-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="cdf1e-229">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-229">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="cdf1e-231">Adicione os outros quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="cdf1e-232">Na seção **registros de recursos personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="cdf1e-233">Repita esse processo até ter criado todos os registros CNAME necessários.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cdf1e-234">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="cdf1e-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdf1e-235">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cdf1e-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cdf1e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cdf1e-238">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="cdf1e-239">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="cdf1e-239">Need examples?</span></span> <span data-ttu-id="cdf1e-240">Confira estes [registros de sistema de nomes de domínio externo para o Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="cdf1e-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="cdf1e-241">Para validar o seu registro SPF, use uma destas [ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="cdf1e-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="cdf1e-p113">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="cdf1e-245">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="cdf1e-246">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="cdf1e-247">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cdf1e-248">Na seção **registros de recursos personalizados** , na linha do registro TXT, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdf1e-p114">O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Selecionar Editar na linha do registro TXT](../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="cdf1e-253">Selecione o controle **(+)** .</span><span class="sxs-lookup"><span data-stu-id="cdf1e-253">Select the **(+)** control.</span></span> 
    
    ![Selecione o controle de adição](../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="cdf1e-255">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cdf1e-256">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cdf1e-257">**Dados**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="cdf1e-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cdf1e-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="cdf1e-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Digitar ou colar valores na seção registros de recursos personalizados](../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="cdf1e-261">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-261">Select **Save**.</span></span>
    
    ![Selecione salvar](../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cdf1e-263">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="cdf1e-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cdf1e-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cdf1e-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cdf1e-p115">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="cdf1e-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="cdf1e-268">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="cdf1e-269">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="cdf1e-270">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="cdf1e-271">Adicione o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="cdf1e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cdf1e-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cdf1e-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cdf1e-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cdf1e-275">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-275">**Name**</span></span>|<span data-ttu-id="cdf1e-276">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-276">**Type**</span></span>|<span data-ttu-id="cdf1e-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-277">**TTL**</span></span>|<span data-ttu-id="cdf1e-278">**Dados**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdf1e-279">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="cdf1e-279">_sip._tls</span></span>|<span data-ttu-id="cdf1e-280">SRV</span><span class="sxs-lookup"><span data-stu-id="cdf1e-280">SRV</span></span>|<span data-ttu-id="cdf1e-281">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-281">1H</span></span>|<span data-ttu-id="cdf1e-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="cdf1e-283">**Esse valor deve terminar com um ponto (.)** **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="cdf1e-284">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="cdf1e-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="cdf1e-285">SRV</span><span class="sxs-lookup"><span data-stu-id="cdf1e-285">SRV</span></span>|<span data-ttu-id="cdf1e-286">1H</span><span class="sxs-lookup"><span data-stu-id="cdf1e-286">1H</span></span>|<span data-ttu-id="cdf1e-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="cdf1e-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdf1e-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="cdf1e-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="cdf1e-291">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-291">Select **Add**.</span></span>
    
    ![Selecione Adicionar](../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="cdf1e-293">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="cdf1e-294">Na seção **registros de recursos personalizados** , crie um registro usando os valores da segunda linha da tabela e, em seguida, selecione **Adicionar** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cdf1e-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cdf1e-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cdf1e-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cdf1e-297">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cdf1e-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
