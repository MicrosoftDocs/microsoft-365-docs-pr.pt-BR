---
title: Criar registros DNS na 1&1 IONOS para Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em 1&1 IONOS para a Microsoft.
ms.openlocfilehash: 2b029856617c853047a0c1da9aeb0f07a158a88e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939374"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="8b919-103">Criar registros DNS na 1&1 IONOS para Microsoft</span><span class="sxs-lookup"><span data-stu-id="8b919-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="8b919-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8b919-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="8b919-105">Observe que 1&1 do IONOS não permite que um domínio tenha um registro MX e um registro CNAME de descoberta automática de nível superior.</span><span class="sxs-lookup"><span data-stu-id="8b919-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="8b919-106">Isso limita as maneiras nas quais você pode configurar o Exchange Online para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b919-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="8b919-107">Há uma solução alternativa, mas recomendamos o seu emprego **somente** se você já tiver experiência com a criação de subdomínios em 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="8b919-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="8b919-108">> se apesar desta [limitação de serviço](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) você optar por gerenciar seus próprios registros DNS da Microsoft em 1&1 IONOS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8b919-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="8b919-109">Depois que você adicionar esses registros na 1&1 IONOS, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b919-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="8b919-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8b919-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8b919-111">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8b919-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8b919-112">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8b919-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8b919-113">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="8b919-113">Add a TXT record for verification</span></span>

<span data-ttu-id="8b919-p103">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b919-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="8b919-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8b919-118">Siga as etapas abaixo ou [assista ao vídeo (início em 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8b919-118">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8b919-119">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="8b919-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="8b919-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8b919-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="8b919-121">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="8b919-122">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="8b919-123">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="8b919-124">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="8b919-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="8b919-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8b919-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8b919-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8b919-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="8b919-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8b919-127">**Type**</span></span> <br/> |<span data-ttu-id="8b919-128">**Prefixo**</span><span class="sxs-lookup"><span data-stu-id="8b919-128">**Prefix**</span></span> <br/> |<span data-ttu-id="8b919-129">**Valor do Nome**</span><span class="sxs-lookup"><span data-stu-id="8b919-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="8b919-130">TXT</span><span class="sxs-lookup"><span data-stu-id="8b919-130">TXT</span></span>  <br/> |<span data-ttu-id="8b919-131">(Deixe este campo em branco)</span><span class="sxs-lookup"><span data-stu-id="8b919-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="8b919-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8b919-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8b919-133">Observação: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8b919-133">NOTE: This is an example.</span></span> <span data-ttu-id="8b919-134">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="8b919-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="8b919-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="8b919-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="8b919-136">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="8b919-137">Selecione **salvar** novamente.</span><span class="sxs-lookup"><span data-stu-id="8b919-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="8b919-138">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b919-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="8b919-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="8b919-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8b919-140">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="8b919-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="8b919-141">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="8b919-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8b919-142">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="8b919-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8b919-143">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="8b919-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8b919-144">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="8b919-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8b919-145">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b919-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8b919-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8b919-147">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8b919-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8b919-148">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8b919-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8b919-149">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b919-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8b919-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8b919-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8b919-151">Siga as etapas abaixo ou [assista ao vídeo (início em 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8b919-151">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b919-152">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="8b919-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="8b919-153">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="8b919-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="8b919-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8b919-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="8b919-155">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="8b919-156">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="8b919-157">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="8b919-158">Na seção **registros MX** , na área **trocador de mensagens (registro MX)** , selecione **outro servidor de email**.</span><span class="sxs-lookup"><span data-stu-id="8b919-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="8b919-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8b919-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="8b919-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="8b919-161">Se houver registros MX já listados, exclua-os selecionando o registro e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="8b919-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="8b919-162">(Se não houver nenhum registro MX já listado, continue na próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="8b919-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="8b919-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="8b919-164">Nas caixas do registro **MX 1**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b919-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="8b919-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="8b919-165">**MX 1**</span></span>|<span data-ttu-id="8b919-166">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8b919-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="8b919-167">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8b919-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="8b919-168">Observação: Obtenha sua \<chave\> de domínio de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b919-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="8b919-169">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="8b919-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8b919-170">10 </span><span class="sxs-lookup"><span data-stu-id="8b919-170">10</span></span>  <br/> <span data-ttu-id="8b919-171">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="8b919-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 e 1-configurar 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="8b919-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-173">Select **Save**.</span></span><br/><span data-ttu-id="8b919-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8b919-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="8b919-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="8b919-176">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b919-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="8b919-177">![Selecionar Sim na caixa de diálogo Editar configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8b919-178">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="8b919-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8b919-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8b919-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8b919-180">1&1 IONOS requer uma solução alternativa para que você possa usar um registro MX junto com os registros CNAME necessários para os serviços de email da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b919-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="8b919-181">Essa solução alternativa requer que você crie um conjunto de subdomínios em 1&1 IONOS e atribua-os aos registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8b919-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8b919-182">Verifique se você tem pelo menos dois subdomínios disponíveis antes de iniciar esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="8b919-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="8b919-183">Recomendamos esta solução somente se você já tem experiência com a criação de subdomínios em 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="8b919-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="8b919-184">Registros CNAME básicos</span><span class="sxs-lookup"><span data-stu-id="8b919-184">Basic CNAME records</span></span>

<span data-ttu-id="8b919-185">Siga as etapas abaixo ou [assista ao vídeo (início em 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8b919-185">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b919-186">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="8b919-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="8b919-187">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="8b919-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="8b919-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8b919-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="8b919-189">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="8b919-190">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione **gerenciar subdomínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="8b919-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="8b919-192">Agora, você vai criar dois subdomínios e definir um valor **Alias** para cada um.</span><span class="sxs-lookup"><span data-stu-id="8b919-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="8b919-193">(Isso é necessário porque 1&1 IONOS suporta apenas um registro CNAME de nível superior, mas a Microsoft requer vários registros CNAME.)</span><span class="sxs-lookup"><span data-stu-id="8b919-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="8b919-194">Primeiro, você criará o subdomínio Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="8b919-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="8b919-195">Na seção **visão geral de subdomínio** , selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="8b919-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="8b919-p113">Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)</span><span class="sxs-lookup"><span data-stu-id="8b919-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="8b919-199">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-199">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8b919-201">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="8b919-201">autodiscover</span></span>  <br/> |<span data-ttu-id="8b919-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8b919-202">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="8b919-204">Selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="8b919-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="8b919-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="8b919-206">Na seção **visão geral de subdomínio** , localize o subdomínio de **descoberta automática** que você acabou de criar e selecione o controle de **painel (v)** para esse subdomínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="8b919-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="8b919-208">Na área **configurações de subdomínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="8b919-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="8b919-210">Na seção **registros a/aaaa (endereços IP)** , na área **endereço IP (registro)** , selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="8b919-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="8b919-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="8b919-212">Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b919-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="8b919-213">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-213">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8b919-215">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="8b919-215">autodiscover</span></span>  <br/> |<span data-ttu-id="8b919-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8b919-216">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="8b919-218">Marque a caixa de seleção para a isenção de responsabilidade **Estou ciente**.</span><span class="sxs-lookup"><span data-stu-id="8b919-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="8b919-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="8b919-220">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-220">Select **Save**.</span></span><br/><span data-ttu-id="8b919-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="8b919-222">Registros CNAME adicionais</span><span class="sxs-lookup"><span data-stu-id="8b919-222">Additional CNAME records</span></span>

<span data-ttu-id="8b919-p114">Os registros CNAME adicionais criados no procedimento a seguir habilitam os serviços do Skype for Business Online. Você usará as mesmas etapas que usou para criar os dois registros CNAME já criados.</span><span class="sxs-lookup"><span data-stu-id="8b919-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="8b919-225">Crie o terceiro subdomínio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="8b919-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="8b919-226">Na seção **visão geral de subdomínio** , selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="8b919-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="8b919-p115">Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)</span><span class="sxs-lookup"><span data-stu-id="8b919-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="8b919-229">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-229">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8b919-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8b919-231">lyncdiscover</span></span>   |<span data-ttu-id="8b919-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b919-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="8b919-233">Selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="8b919-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="8b919-234">Na página **centro de domínio** , selecione **gerenciar subdomínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="8b919-235">Na seção **visão geral de subdomínio** , encontre o subdomínio **lyncdiscover** que você acabou de criar e selecione o controle de **painel (v)** para esse subdomínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="8b919-236">Na área **configurações de subdomínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="8b919-237">Na seção **registros a/aaaa (endereços IP)** , na área **endereço IP (registro)** , selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="8b919-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="8b919-238">Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b919-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="8b919-239">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-239">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8b919-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8b919-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8b919-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b919-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="8b919-243">Marque a caixa de seleção para a isenção de responsabilidade estou **ciente** e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="8b919-244">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b919-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="8b919-245">Crie o quarto subdomínio (SIP):</span><span class="sxs-lookup"><span data-stu-id="8b919-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="8b919-246">Na seção **visão geral de subdomínio** , selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="8b919-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="8b919-p116">Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)</span><span class="sxs-lookup"><span data-stu-id="8b919-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="8b919-249">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-249">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8b919-251">sip</span><span class="sxs-lookup"><span data-stu-id="8b919-251">sip</span></span>  <br/> |<span data-ttu-id="8b919-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b919-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="8b919-253">Selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="8b919-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="8b919-254">Na página **centro de domínio** , selecione **gerenciar subdomínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="8b919-255">Na seção **visão geral de subdomínio** , encontre o subdomínio **SIP** que você acabou de criar e selecione o controle de **painel (v)** para esse subdomínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="8b919-256">Na área **configurações de subdomínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="8b919-257">Na seção **registros a/aaaa (endereços IP)** , na área **endereço IP (registro)** , selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="8b919-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="8b919-258">Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b919-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="8b919-259">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-259">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8b919-261">sip</span><span class="sxs-lookup"><span data-stu-id="8b919-261">sip</span></span>  <br/> |<span data-ttu-id="8b919-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b919-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="8b919-263">Marque a caixa de seleção para a isenção de responsabilidade estou **ciente** e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="8b919-264">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b919-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="8b919-265">Registros CNAME necessários para o MDM</span><span class="sxs-lookup"><span data-stu-id="8b919-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b919-266">Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b919-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="8b919-267">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="8b919-267">**Create Subdomain**</span></span>|<span data-ttu-id="8b919-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b919-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b919-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8b919-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8b919-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8b919-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="8b919-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8b919-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8b919-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b919-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8b919-273">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="8b919-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b919-274">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8b919-275">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="8b919-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8b919-276">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b919-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8b919-277">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8b919-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="8b919-278">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="8b919-278">Need examples?</span></span> <span data-ttu-id="8b919-279">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="8b919-279">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="8b919-280">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8b919-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="8b919-281">Siga as etapas abaixo ou [assista ao vídeo (início em 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8b919-281">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b919-282">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="8b919-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="8b919-283">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="8b919-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="8b919-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8b919-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="8b919-285">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="8b919-286">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** (**v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="8b919-287">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="8b919-288">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="8b919-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="8b919-289">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="8b919-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="8b919-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8b919-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="8b919-291">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8b919-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="8b919-292">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8b919-292">**Type**</span></span>|<span data-ttu-id="8b919-293">**Prefixo**</span><span class="sxs-lookup"><span data-stu-id="8b919-293">**Prefix**</span></span>|<span data-ttu-id="8b919-294">**Valor do Nome**</span><span class="sxs-lookup"><span data-stu-id="8b919-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8b919-295">TXT</span><span class="sxs-lookup"><span data-stu-id="8b919-295">TXT</span></span>  <br/> |<span data-ttu-id="8b919-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="8b919-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8b919-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8b919-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8b919-298">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="8b919-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Registro TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="8b919-300">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-300">Select **Save**.</span></span><br/><span data-ttu-id="8b919-301">![Adicionar registro](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="8b919-302">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-302">Select **Save**.</span></span><br/><span data-ttu-id="8b919-303">![Salvar registro](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="8b919-304">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b919-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="8b919-305">![Selecionar Sim na caixa de diálogo Editar configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8b919-306">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8b919-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="8b919-307">Siga as etapas abaixo ou [assista ao vídeo (início em 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8b919-307">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b919-308">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="8b919-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="8b919-309">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="8b919-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="8b919-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="8b919-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="8b919-311">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="8b919-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="8b919-312">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="8b919-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="8b919-313">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="8b919-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="8b919-314">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="8b919-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="8b919-315">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="8b919-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="8b919-316">Na área **Adicionar Registro**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b919-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="8b919-317">(Escolha os valores de **tipo** e **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="8b919-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8b919-318">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8b919-318">**Type**</span></span>|<span data-ttu-id="8b919-319">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="8b919-319">**Service**</span></span>|<span data-ttu-id="8b919-320">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="8b919-320">**Protocol**</span></span>|<span data-ttu-id="8b919-321">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8b919-321">**Name**</span></span>|<span data-ttu-id="8b919-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="8b919-322">**Host**</span></span>|<span data-ttu-id="8b919-323">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8b919-323">**Priority**</span></span>|<span data-ttu-id="8b919-324">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="8b919-324">**Weight**</span></span>|<span data-ttu-id="8b919-325">**Porta**</span><span class="sxs-lookup"><span data-stu-id="8b919-325">**Port**</span></span>|<span data-ttu-id="8b919-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8b919-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8b919-327">SRV</span><span class="sxs-lookup"><span data-stu-id="8b919-327">SRV</span></span>  <br/> |<span data-ttu-id="8b919-328">sip</span><span class="sxs-lookup"><span data-stu-id="8b919-328">sip</span></span>  <br/> |<span data-ttu-id="8b919-329">tls</span><span class="sxs-lookup"><span data-stu-id="8b919-329">tls</span></span>  <br/> |<span data-ttu-id="8b919-330">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="8b919-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8b919-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b919-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="8b919-332">100</span><span class="sxs-lookup"><span data-stu-id="8b919-332">100</span></span>  <br/> |<span data-ttu-id="8b919-333">1</span><span class="sxs-lookup"><span data-stu-id="8b919-333">1</span></span>  <br/> |<span data-ttu-id="8b919-334">443</span><span class="sxs-lookup"><span data-stu-id="8b919-334">443</span></span>  <br/> |<span data-ttu-id="8b919-335">3.600 (1 hora)</span><span class="sxs-lookup"><span data-stu-id="8b919-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="8b919-336">SRV</span><span class="sxs-lookup"><span data-stu-id="8b919-336">SRV</span></span>  <br/> |<span data-ttu-id="8b919-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8b919-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="8b919-338">tcp</span><span class="sxs-lookup"><span data-stu-id="8b919-338">tcp</span></span>  <br/> |<span data-ttu-id="8b919-339">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="8b919-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8b919-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b919-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="8b919-341">100</span><span class="sxs-lookup"><span data-stu-id="8b919-341">100</span></span>  <br/> |<span data-ttu-id="8b919-342">1</span><span class="sxs-lookup"><span data-stu-id="8b919-342">1</span></span>  <br/> |<span data-ttu-id="8b919-343">5061</span><span class="sxs-lookup"><span data-stu-id="8b919-343">5061</span></span>  <br/> |<span data-ttu-id="8b919-344">3.600 (1 hora)</span><span class="sxs-lookup"><span data-stu-id="8b919-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="8b919-346">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-346">Select **Save**.</span></span> <br/><span data-ttu-id="8b919-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="8b919-348">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b919-348">Select **Save**.</span></span> <br/><span data-ttu-id="8b919-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="8b919-350">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b919-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="8b919-351">![Selecionar Sim na caixa de diálogo Editar configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="8b919-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="8b919-352">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="8b919-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="8b919-353">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="8b919-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="8b919-354">Na área **adicionar registro** , crie um registro usando os valores da outra linha da tabela e, em seguida, selecione **Adicionar**, **salvar**e **Sim** novamente para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="8b919-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8b919-355">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8b919-355">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8b919-356">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8b919-356">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8b919-357">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8b919-357">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
