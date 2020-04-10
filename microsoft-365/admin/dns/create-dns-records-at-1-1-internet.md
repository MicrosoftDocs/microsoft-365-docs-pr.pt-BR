---
title: Criar registros DNS em 1&1 IONOS para o Office 365
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em 1&1 IONOS para o Office 365.
ms.openlocfilehash: e31c9d9d08e29156ff6197c030de6b0f4169b5f4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211866"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="29ff5-103">Criar registros DNS em 1&1 IONOS para o Office 365</span><span class="sxs-lookup"><span data-stu-id="29ff5-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="29ff5-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="29ff5-105">Observe que 1&1 do IONOS não permite que um domínio tenha um registro MX e um registro CNAME de descoberta automática de nível superior.</span><span class="sxs-lookup"><span data-stu-id="29ff5-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="29ff5-106">Isso limita as formas de configurar o Exchange Online para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ff5-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="29ff5-107">Há uma solução alternativa, mas recomendamos o seu emprego **somente** se você já tiver experiência com a criação de subdomínios em 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="29ff5-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="29ff5-108">> se apesar desta [limitação de serviço](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) você optar por gerenciar seus próprios registros DNS do Office 365 em 1&1 IONOS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="29ff5-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="29ff5-109">Depois que você adicionar esses registros na 1&1 IONOS, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ff5-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="29ff5-110">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="29ff5-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ff5-111">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="29ff5-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="29ff5-112">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="29ff5-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="29ff5-113">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="29ff5-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="29ff5-114">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="29ff5-114">Add a TXT record for verification</span></span>

<span data-ttu-id="29ff5-p103">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ff5-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="29ff5-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="29ff5-119">Siga as etapas abaixo ou [assista ao vídeo (início em 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="29ff5-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="29ff5-120">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="29ff5-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="29ff5-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="29ff5-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="29ff5-122">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="29ff5-123">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="29ff5-124">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="29ff5-125">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="29ff5-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="29ff5-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="29ff5-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="29ff5-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="29ff5-128">**Type**</span></span> <br/> |<span data-ttu-id="29ff5-129">**Prefixo**</span><span class="sxs-lookup"><span data-stu-id="29ff5-129">**Prefix**</span></span> <br/> |<span data-ttu-id="29ff5-130">**Valor do Nome**</span><span class="sxs-lookup"><span data-stu-id="29ff5-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="29ff5-131">TXT</span><span class="sxs-lookup"><span data-stu-id="29ff5-131">TXT</span></span>  <br/> |<span data-ttu-id="29ff5-132">(Deixe este campo em branco)</span><span class="sxs-lookup"><span data-stu-id="29ff5-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="29ff5-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="29ff5-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="29ff5-134">Observação: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="29ff5-134">NOTE: This is an example.</span></span> <span data-ttu-id="29ff5-135">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ff5-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="29ff5-136">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="29ff5-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="29ff5-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="29ff5-138">Selecione **salvar** novamente.</span><span class="sxs-lookup"><span data-stu-id="29ff5-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="29ff5-139">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="29ff5-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="29ff5-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="29ff5-141">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="29ff5-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="29ff5-142">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="29ff5-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="29ff5-143">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="29ff5-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="29ff5-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="29ff5-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="29ff5-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="29ff5-146">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="29ff5-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="29ff5-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="29ff5-148">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="29ff5-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="29ff5-149">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="29ff5-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="29ff5-150">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="29ff5-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="29ff5-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="29ff5-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="29ff5-152">Siga as etapas abaixo ou [assista ao vídeo (início em 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="29ff5-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ff5-153">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="29ff5-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="29ff5-154">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="29ff5-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="29ff5-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="29ff5-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="29ff5-156">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="29ff5-157">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="29ff5-158">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="29ff5-159">Na seção **Registros MX**, na área \*\* Servidor de Mensagens (Registro MX) \*\*, selecione **Outro servidor de email**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="29ff5-160">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="29ff5-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="29ff5-162">Se houver registros MX já listados, exclua-os selecionando o registro e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="29ff5-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="29ff5-163">(Se não houver nenhum registro MX já listado, continue na próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="29ff5-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="29ff5-165">Nas caixas do registro **MX 1**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="29ff5-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="29ff5-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="29ff5-166">**MX 1**</span></span>|<span data-ttu-id="29ff5-167">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="29ff5-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="29ff5-168">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="29ff5-169">Observação: Obtenha sua \<chave\> de domínio de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ff5-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="29ff5-170">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="29ff5-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="29ff5-171">10 </span><span class="sxs-lookup"><span data-stu-id="29ff5-171">10</span></span>  <br/> <span data-ttu-id="29ff5-172">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="29ff5-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 e 1-configurar 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="29ff5-174">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-174">Select **Save**.</span></span><br/><span data-ttu-id="29ff5-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="29ff5-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="29ff5-177">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="29ff5-178">![Selecionar Sim na caixa de diálogo Editar configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="29ff5-179">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="29ff5-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="29ff5-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="29ff5-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="29ff5-181">1&1 IONOS requer uma solução alternativa para que você possa usar um registro MX junto com os registros CNAME necessários para os serviços de email do Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ff5-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="29ff5-182">Essa solução alternativa requer que você crie um conjunto de subdomínios em 1&1 IONOS e atribua-os aos registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="29ff5-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="29ff5-183">Verifique se você tem pelo menos dois subdomínios disponíveis antes de iniciar esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="29ff5-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="29ff5-184">Recomendamos esta solução somente se você já tem experiência com a criação de subdomínios em 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="29ff5-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="29ff5-185">Registros CNAME básicos</span><span class="sxs-lookup"><span data-stu-id="29ff5-185">Basic CNAME records</span></span>

<span data-ttu-id="29ff5-186">Siga as etapas abaixo ou [assista ao vídeo (início em 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="29ff5-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ff5-187">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="29ff5-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="29ff5-188">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="29ff5-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="29ff5-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="29ff5-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="29ff5-190">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="29ff5-191">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione **gerenciar subdomínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="29ff5-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="29ff5-193">Agora, você vai criar dois subdomínios e definir um valor **Alias** para cada um.</span><span class="sxs-lookup"><span data-stu-id="29ff5-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="29ff5-194">(Isso é necessário porque 1&1 IONOS suporta apenas um registro CNAME de nível superior, mas o Office 365 requer vários registros CNAME.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="29ff5-195">Primeiro, você criará o subdomínio Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="29ff5-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="29ff5-196">Na seção **visão geral de subdomínio** , selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="29ff5-p113">Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="29ff5-200">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-200">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="29ff5-202">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="29ff5-202">autodiscover</span></span>  <br/> |<span data-ttu-id="29ff5-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="29ff5-205">Selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="29ff5-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="29ff5-207">Na seção **visão geral de subdomínio** , localize o subdomínio de **descoberta automática** que você acabou de criar e selecione o controle de **painel (v)** para esse subdomínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="29ff5-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="29ff5-209">Na área **configurações de subdomínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="29ff5-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="29ff5-211">Na seção **registros a/aaaa (endereços IP)** , na área **endereço IP (registro)** , selecione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="29ff5-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="29ff5-213">Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="29ff5-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="29ff5-214">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-214">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="29ff5-216">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="29ff5-216">autodiscover</span></span>  <br/> |<span data-ttu-id="29ff5-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="29ff5-219">Marque a caixa de seleção para a isenção de responsabilidade **Estou ciente**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="29ff5-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="29ff5-221">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-221">Select **Save**.</span></span><br/><span data-ttu-id="29ff5-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="29ff5-223">Registros CNAME adicionais</span><span class="sxs-lookup"><span data-stu-id="29ff5-223">Additional CNAME records</span></span>

<span data-ttu-id="29ff5-p114">Os registros CNAME adicionais criados no procedimento a seguir habilitam os serviços do Skype for Business Online. Você usará as mesmas etapas que usou para criar os dois registros CNAME já criados.</span><span class="sxs-lookup"><span data-stu-id="29ff5-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="29ff5-226">Crie o terceiro subdomínio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="29ff5-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="29ff5-227">Na seção **visão geral de subdomínio** , selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="29ff5-p115">Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="29ff5-230">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-230">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="29ff5-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="29ff5-232">lyncdiscover</span></span>   |<span data-ttu-id="29ff5-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="29ff5-234">Selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="29ff5-235">Na página **centro de domínio** , selecione **gerenciar subdomínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="29ff5-236">Na seção **visão geral de subdomínio** , encontre o subdomínio **lyncdiscover** que você acabou de criar e selecione o controle de **painel (v)** para esse subdomínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="29ff5-237">Na área **configurações de subdomínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="29ff5-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="29ff5-239">Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="29ff5-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="29ff5-240">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-240">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="29ff5-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="29ff5-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="29ff5-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="29ff5-244">Marque a caixa de seleção para a isenção de responsabilidade estou **ciente** e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="29ff5-245">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="29ff5-246">Crie o quarto subdomínio (SIP):</span><span class="sxs-lookup"><span data-stu-id="29ff5-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="29ff5-247">Na seção **visão geral de subdomínio** , selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="29ff5-p116">Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="29ff5-250">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-250">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="29ff5-252">sip</span><span class="sxs-lookup"><span data-stu-id="29ff5-252">sip</span></span>  <br/> |<span data-ttu-id="29ff5-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="29ff5-254">Selecione **criar subdomínio**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="29ff5-255">Na página **centro de domínio** , selecione **gerenciar subdomínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="29ff5-256">Na seção **visão geral de subdomínio** , encontre o subdomínio **SIP** que você acabou de criar e selecione o controle de **painel (v)** para esse subdomínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="29ff5-257">Na área **configurações de subdomínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="29ff5-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="29ff5-259">Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="29ff5-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="29ff5-260">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-260">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="29ff5-262">sip</span><span class="sxs-lookup"><span data-stu-id="29ff5-262">sip</span></span>  <br/> |<span data-ttu-id="29ff5-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="29ff5-264">Marque a caixa de seleção para a isenção de responsabilidade estou **ciente** e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="29ff5-265">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="29ff5-266">Registros CNAME necessários para o MDM</span><span class="sxs-lookup"><span data-stu-id="29ff5-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29ff5-267">Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="29ff5-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="29ff5-268">**Criar subdomínio**</span><span class="sxs-lookup"><span data-stu-id="29ff5-268">**Create Subdomain**</span></span>|<span data-ttu-id="29ff5-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="29ff5-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29ff5-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="29ff5-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="29ff5-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="29ff5-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="29ff5-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="29ff5-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="29ff5-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="29ff5-274">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="29ff5-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29ff5-275">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="29ff5-276">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="29ff5-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="29ff5-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="29ff5-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="29ff5-278">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="29ff5-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="29ff5-279">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="29ff5-279">Need examples?</span></span> <span data-ttu-id="29ff5-280">Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). </span><span class="sxs-lookup"><span data-stu-id="29ff5-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="29ff5-281">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="29ff5-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="29ff5-282">Siga as etapas abaixo ou [assista ao vídeo (início em 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="29ff5-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ff5-283">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="29ff5-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="29ff5-284">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="29ff5-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="29ff5-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="29ff5-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="29ff5-286">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="29ff5-287">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** (**v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="29ff5-288">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="29ff5-289">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="29ff5-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="29ff5-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="29ff5-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="29ff5-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="29ff5-293">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="29ff5-293">**Type**</span></span>|<span data-ttu-id="29ff5-294">**Prefixo**</span><span class="sxs-lookup"><span data-stu-id="29ff5-294">**Prefix**</span></span>|<span data-ttu-id="29ff5-295">**Valor do Nome**</span><span class="sxs-lookup"><span data-stu-id="29ff5-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="29ff5-296">TXT</span><span class="sxs-lookup"><span data-stu-id="29ff5-296">TXT</span></span>  <br/> |<span data-ttu-id="29ff5-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="29ff5-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="29ff5-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="29ff5-299">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="29ff5-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Registro TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="29ff5-301">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-301">Select **Save**.</span></span><br/><span data-ttu-id="29ff5-302">![Adicionar registro](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="29ff5-303">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-303">Select **Save**.</span></span><br/><span data-ttu-id="29ff5-304">![Salvar registro](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="29ff5-305">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="29ff5-306">![Selecionar Sim na caixa de diálogo Editar configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="29ff5-307">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="29ff5-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="29ff5-308">Siga as etapas abaixo ou [assista ao vídeo (início em 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="29ff5-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ff5-309">Se você tiver registrado o 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="29ff5-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="29ff5-310">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="29ff5-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="29ff5-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="29ff5-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="29ff5-312">Selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="29ff5-313">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="29ff5-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="29ff5-314">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="29ff5-315">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="29ff5-316">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="29ff5-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="29ff5-317">Na área **Adicionar Registro**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="29ff5-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="29ff5-318">(Escolha os valores de **tipo** e **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="29ff5-319">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="29ff5-319">**Type**</span></span>|<span data-ttu-id="29ff5-320">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="29ff5-320">**Service**</span></span>|<span data-ttu-id="29ff5-321">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="29ff5-321">**Protocol**</span></span>|<span data-ttu-id="29ff5-322">**Nome**</span><span class="sxs-lookup"><span data-stu-id="29ff5-322">**Name**</span></span>|<span data-ttu-id="29ff5-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="29ff5-323">**Host**</span></span>|<span data-ttu-id="29ff5-324">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="29ff5-324">**Priority**</span></span>|<span data-ttu-id="29ff5-325">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="29ff5-325">**Weight**</span></span>|<span data-ttu-id="29ff5-326">**Porta**</span><span class="sxs-lookup"><span data-stu-id="29ff5-326">**Port**</span></span>|<span data-ttu-id="29ff5-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="29ff5-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="29ff5-328">SRV</span><span class="sxs-lookup"><span data-stu-id="29ff5-328">SRV</span></span>  <br/> |<span data-ttu-id="29ff5-329">sip</span><span class="sxs-lookup"><span data-stu-id="29ff5-329">sip</span></span>  <br/> |<span data-ttu-id="29ff5-330">tls</span><span class="sxs-lookup"><span data-stu-id="29ff5-330">tls</span></span>  <br/> |<span data-ttu-id="29ff5-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="29ff5-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="29ff5-333">100</span><span class="sxs-lookup"><span data-stu-id="29ff5-333">100</span></span>  <br/> |<span data-ttu-id="29ff5-334">1</span><span class="sxs-lookup"><span data-stu-id="29ff5-334">1</span></span>  <br/> |<span data-ttu-id="29ff5-335">443</span><span class="sxs-lookup"><span data-stu-id="29ff5-335">443</span></span>  <br/> |<span data-ttu-id="29ff5-336">3.600 (1 hora)</span><span class="sxs-lookup"><span data-stu-id="29ff5-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="29ff5-337">SRV</span><span class="sxs-lookup"><span data-stu-id="29ff5-337">SRV</span></span>  <br/> |<span data-ttu-id="29ff5-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="29ff5-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="29ff5-339">tcp</span><span class="sxs-lookup"><span data-stu-id="29ff5-339">tcp</span></span>  <br/> |<span data-ttu-id="29ff5-340">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="29ff5-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="29ff5-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29ff5-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="29ff5-342">100</span><span class="sxs-lookup"><span data-stu-id="29ff5-342">100</span></span>  <br/> |<span data-ttu-id="29ff5-343">1</span><span class="sxs-lookup"><span data-stu-id="29ff5-343">1</span></span>  <br/> |<span data-ttu-id="29ff5-344">5061</span><span class="sxs-lookup"><span data-stu-id="29ff5-344">5061</span></span>  <br/> |<span data-ttu-id="29ff5-345">3.600 (1 hora)</span><span class="sxs-lookup"><span data-stu-id="29ff5-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="29ff5-347">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-347">Select **Save**.</span></span> <br/><span data-ttu-id="29ff5-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="29ff5-349">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-349">Select **Save**.</span></span> <br/><span data-ttu-id="29ff5-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="29ff5-351">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="29ff5-352">![Selecionar Sim na caixa de diálogo Editar configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="29ff5-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="29ff5-353">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="29ff5-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="29ff5-354">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="29ff5-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="29ff5-355">Na área **adicionar registro** , crie um registro usando os valores da outra linha da tabela e, em seguida, selecione **Adicionar**, **salvar**e **Sim** novamente para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="29ff5-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="29ff5-356">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="29ff5-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="29ff5-357">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="29ff5-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="29ff5-358">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="29ff5-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
