---
title: Criar registros DNS na Bluehost para Office 365
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Bluehost para o Office 365.
ms.openlocfilehash: 0e64ed8787dca9822e71a63c57de7a7a3e2b3fe4
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350952"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="f4323-103">Criar registros DNS na Bluehost para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4323-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="f4323-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f4323-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f4323-105">Se você usa a Bluehost como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="f4323-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f4323-106">Depois que você adicionar esses registros na Bluehost, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4323-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f4323-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="f4323-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4323-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f4323-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f4323-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="f4323-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f4323-110">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f4323-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f4323-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="f4323-111">Add a TXT record for verification</span></span>
<span data-ttu-id="f4323-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f4323-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f4323-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4323-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="f4323-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f4323-117">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="f4323-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f4323-118">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="f4323-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4323-119">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f4323-120">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="f4323-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f4323-121">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4323-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f4323-122">Na página \* \* Editor de zona DNS \* \*, na área **adicionar registro DNS** , nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4323-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f4323-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f4323-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f4323-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f4323-124">**Host Record**</span></span> <br/> |<span data-ttu-id="f4323-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4323-125">**TTL**</span></span> <br/> |<span data-ttu-id="f4323-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4323-126">**Type**</span></span> <br/> |<span data-ttu-id="f4323-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="f4323-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="f4323-128">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-128">14400</span></span>  <br/> |<span data-ttu-id="f4323-129">TXT</span><span class="sxs-lookup"><span data-stu-id="f4323-129">TXT</span></span>  <br/> |<span data-ttu-id="f4323-130">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f4323-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f4323-131">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="f4323-131">**Note:** This is an example.</span></span> <span data-ttu-id="f4323-132">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4323-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="f4323-133">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="f4323-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="f4323-134">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="f4323-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="f4323-135">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="f4323-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f4323-136">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="f4323-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f4323-137">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="f4323-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f4323-138">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="f4323-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f4323-139">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="f4323-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f4323-140">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="f4323-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f4323-141">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="f4323-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4323-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f4323-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f4323-143">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="f4323-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f4323-144">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f4323-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f4323-145">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f4323-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f4323-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f4323-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f4323-147">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="f4323-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f4323-148">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="f4323-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4323-149">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f4323-150">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="f4323-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f4323-151">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4323-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f4323-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f4323-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f4323-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f4323-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f4323-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f4323-154">**Host Record**</span></span>|<span data-ttu-id="f4323-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4323-155">**TTL**</span></span>|<span data-ttu-id="f4323-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4323-156">**Type**</span></span>|<span data-ttu-id="f4323-157">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="f4323-157">**Points To**</span></span>|<span data-ttu-id="f4323-158">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="f4323-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f4323-159">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-159">14400</span></span>  <br/> |<span data-ttu-id="f4323-160">MX</span><span class="sxs-lookup"><span data-stu-id="f4323-160">MX</span></span>  <br/> | <span data-ttu-id="f4323-161">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f4323-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="f4323-162">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4323-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="f4323-163">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="f4323-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f4323-164">,0</span><span class="sxs-lookup"><span data-stu-id="f4323-164">0</span></span>  <br/> <span data-ttu-id="f4323-165">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="f4323-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Escolha tipo na lista suspensa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="f4323-167">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="f4323-167">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="f4323-169">Se existirem outros registros MX na seção **MX (Mail Exchanger)**, exclua cada um deles.</span><span class="sxs-lookup"><span data-stu-id="f4323-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="f4323-170">Para um dos outros registros MX, selecione **excluir.**</span><span class="sxs-lookup"><span data-stu-id="f4323-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Selecione Excluir para cada registro MX adicional](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="f4323-172">Na caixa de diálogo de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4323-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Selecione OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="f4323-174">Use o mesmo processo para excluir todos os outros registros MX que já foram listados.</span><span class="sxs-lookup"><span data-stu-id="f4323-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f4323-175">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f4323-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f4323-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f4323-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f4323-177">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="f4323-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f4323-178">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="f4323-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4323-179">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f4323-180">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="f4323-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f4323-181">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4323-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f4323-182">Na seção registros **a (host)** , localize a linha do registro de **descoberta automática** e, em seguida, selecione **excluir** para essa linha.</span><span class="sxs-lookup"><span data-stu-id="f4323-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4323-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span><span class="sxs-lookup"><span data-stu-id="f4323-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Selecione Excluir](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="f4323-186">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4323-186">Select **OK**.</span></span>
    
    ![Selecione OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="f4323-188">Crie o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="f4323-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="f4323-189">Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4323-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f4323-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f4323-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f4323-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f4323-191">**Host Record**</span></span>|<span data-ttu-id="f4323-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4323-192">**TTL**</span></span>|<span data-ttu-id="f4323-193">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4323-193">**Type**</span></span>|<span data-ttu-id="f4323-194">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="f4323-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f4323-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f4323-195">autodiscover</span></span>  <br/> |<span data-ttu-id="f4323-196">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-196">14400</span></span>  <br/> |<span data-ttu-id="f4323-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4323-197">CNAME</span></span>  <br/> |<span data-ttu-id="f4323-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f4323-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f4323-199">sip</span><span class="sxs-lookup"><span data-stu-id="f4323-199">sip</span></span>  <br/> |<span data-ttu-id="f4323-200">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-200">14400</span></span>  <br/> |<span data-ttu-id="f4323-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4323-201">CNAME</span></span>  <br/> |<span data-ttu-id="f4323-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4323-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f4323-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f4323-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f4323-204">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-204">14400</span></span>  <br/> |<span data-ttu-id="f4323-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4323-205">CNAME</span></span>  <br/> |<span data-ttu-id="f4323-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4323-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f4323-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f4323-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f4323-208">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-208">14400</span></span>  <br/> |<span data-ttu-id="f4323-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4323-209">CNAME</span></span>  <br/> |<span data-ttu-id="f4323-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f4323-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f4323-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f4323-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f4323-212">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-212">14400</span></span>  <br/> |<span data-ttu-id="f4323-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4323-213">CNAME</span></span>  <br/> |<span data-ttu-id="f4323-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f4323-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Criar o primeiro registro CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="f4323-216">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="f4323-216">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="f4323-218">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="f4323-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="f4323-219">Ainda na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="f4323-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="f4323-220">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="f4323-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f4323-221">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="f4323-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f4323-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f4323-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4323-223">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f4323-224">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="f4323-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f4323-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4323-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f4323-226">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="f4323-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="f4323-227">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="f4323-227">Need examples?</span></span> <span data-ttu-id="f4323-228">Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). </span><span class="sxs-lookup"><span data-stu-id="f4323-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="f4323-229">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="f4323-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="f4323-230">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="f4323-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f4323-231">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="f4323-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4323-232">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f4323-233">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="f4323-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f4323-234">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4323-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f4323-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f4323-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f4323-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f4323-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="f4323-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f4323-237">**Host Record**</span></span>|<span data-ttu-id="f4323-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4323-238">**TTL**</span></span>|<span data-ttu-id="f4323-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4323-239">**Type**</span></span>|<span data-ttu-id="f4323-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="f4323-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f4323-241">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-241">14400</span></span>  <br/> |<span data-ttu-id="f4323-242">TXT</span><span class="sxs-lookup"><span data-stu-id="f4323-242">TXT</span></span>  <br/> |<span data-ttu-id="f4323-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f4323-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="f4323-244">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="f4323-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar o valor TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="f4323-246">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="f4323-246">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f4323-248">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="f4323-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f4323-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f4323-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f4323-250">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="f4323-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f4323-251">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="f4323-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4323-252">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="f4323-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f4323-253">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="f4323-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f4323-254">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4323-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f4323-255">Crie o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="f4323-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="f4323-256">Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4323-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f4323-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f4323-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f4323-258">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="f4323-258">**Service**</span></span>|<span data-ttu-id="f4323-259">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="f4323-259">**Protocol**</span></span>|<span data-ttu-id="f4323-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="f4323-260">**Host**</span></span>|<span data-ttu-id="f4323-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4323-261">**TTL**</span></span>|<span data-ttu-id="f4323-262">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4323-262">**Type**</span></span>|<span data-ttu-id="f4323-263">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="f4323-263">**Priority**</span></span>|<span data-ttu-id="f4323-264">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="f4323-264">**Weight**</span></span>|<span data-ttu-id="f4323-265">**Porta**</span><span class="sxs-lookup"><span data-stu-id="f4323-265">**Port**</span></span>|<span data-ttu-id="f4323-266">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="f4323-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f4323-267">_sip</span><span class="sxs-lookup"><span data-stu-id="f4323-267">_sip</span></span>  <br/> |<span data-ttu-id="f4323-268">_tls</span><span class="sxs-lookup"><span data-stu-id="f4323-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="f4323-269">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-269">14400</span></span>  <br/> |<span data-ttu-id="f4323-270">SRV</span><span class="sxs-lookup"><span data-stu-id="f4323-270">SRV</span></span>  <br/> |<span data-ttu-id="f4323-271">100</span><span class="sxs-lookup"><span data-stu-id="f4323-271">100</span></span>  <br/> |<span data-ttu-id="f4323-272">1</span><span class="sxs-lookup"><span data-stu-id="f4323-272">1</span></span>  <br/> |<span data-ttu-id="f4323-273">443</span><span class="sxs-lookup"><span data-stu-id="f4323-273">443</span></span>  <br/> |<span data-ttu-id="f4323-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4323-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f4323-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f4323-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f4323-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="f4323-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="f4323-277">14400</span><span class="sxs-lookup"><span data-stu-id="f4323-277">14400</span></span>  <br/> |<span data-ttu-id="f4323-278">SRV</span><span class="sxs-lookup"><span data-stu-id="f4323-278">SRV</span></span>  <br/> |<span data-ttu-id="f4323-279">100</span><span class="sxs-lookup"><span data-stu-id="f4323-279">100</span></span>  <br/> |<span data-ttu-id="f4323-280">1</span><span class="sxs-lookup"><span data-stu-id="f4323-280">1</span></span>  <br/> |<span data-ttu-id="f4323-281">5061</span><span class="sxs-lookup"><span data-stu-id="f4323-281">5061</span></span>  <br/> |<span data-ttu-id="f4323-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4323-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiar o valor do novo registro](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="f4323-284">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="f4323-284">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="f4323-286">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="f4323-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="f4323-287">Ainda na seção **adicionar registro DNS** , crie um registro usando os valores da outra linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="f4323-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="f4323-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f4323-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f4323-289">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="f4323-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f4323-290">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f4323-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

