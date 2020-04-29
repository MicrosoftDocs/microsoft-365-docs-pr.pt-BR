---
title: Criar registros DNS no Bluehost para Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Bluehost para a Microsoft.
ms.openlocfilehash: 1608aebdf984e22e45d7a2469acb0a8002fca2a1
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919546"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="90f37-103">Criar registros DNS no Bluehost para Microsoft</span><span class="sxs-lookup"><span data-stu-id="90f37-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="90f37-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="90f37-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="90f37-105">Se você usa a Bluehost como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="90f37-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="90f37-106">Depois que você adicionar esses registros no Bluehost, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90f37-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="90f37-107">Para saber mais sobre hospedagem na web e DNS para sites com a Microsoft, confira [Usar um site público com o a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="90f37-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="90f37-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="90f37-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="90f37-109">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="90f37-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="90f37-110">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90f37-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="90f37-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="90f37-111">Add a TXT record for verification</span></span>
<span data-ttu-id="90f37-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="90f37-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="90f37-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90f37-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="90f37-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="90f37-117">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="90f37-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="90f37-118">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="90f37-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="90f37-119">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="90f37-120">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="90f37-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="90f37-121">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="90f37-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="90f37-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="90f37-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="90f37-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="90f37-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90f37-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="90f37-124">**Host Record**</span></span> <br/> |<span data-ttu-id="90f37-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90f37-125">**TTL**</span></span> <br/> |<span data-ttu-id="90f37-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90f37-126">**Type**</span></span> <br/> |<span data-ttu-id="90f37-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="90f37-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="90f37-128">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-128">14400</span></span>  <br/> |<span data-ttu-id="90f37-129">TXT</span><span class="sxs-lookup"><span data-stu-id="90f37-129">TXT</span></span>  <br/> |<span data-ttu-id="90f37-130">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="90f37-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="90f37-131">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="90f37-131">**Note:** This is an example.</span></span> <span data-ttu-id="90f37-132">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="90f37-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="90f37-133">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="90f37-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="90f37-134">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="90f37-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="90f37-135">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="90f37-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="90f37-136">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="90f37-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="90f37-137">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="90f37-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="90f37-138">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="90f37-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="90f37-139">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="90f37-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="90f37-140">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="90f37-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="90f37-141">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="90f37-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="90f37-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="90f37-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="90f37-143">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="90f37-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="90f37-144">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90f37-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="90f37-145">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90f37-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="90f37-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="90f37-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="90f37-147">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="90f37-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="90f37-148">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="90f37-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="90f37-149">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="90f37-150">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="90f37-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="90f37-151">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="90f37-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="90f37-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="90f37-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="90f37-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="90f37-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90f37-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="90f37-154">**Host Record**</span></span>|<span data-ttu-id="90f37-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90f37-155">**TTL**</span></span>|<span data-ttu-id="90f37-156">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90f37-156">**Type**</span></span>|<span data-ttu-id="90f37-157">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="90f37-157">**Points To**</span></span>|<span data-ttu-id="90f37-158">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="90f37-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="90f37-159">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-159">14400</span></span>  <br/> |<span data-ttu-id="90f37-160">MX</span><span class="sxs-lookup"><span data-stu-id="90f37-160">MX</span></span>  <br/> | <span data-ttu-id="90f37-161">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="90f37-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="90f37-162">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90f37-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="90f37-163">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="90f37-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="90f37-164">,0</span><span class="sxs-lookup"><span data-stu-id="90f37-164">0</span></span>  <br/> <span data-ttu-id="90f37-165">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="90f37-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Escolha tipo na lista suspensa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="90f37-167">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="90f37-167">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="90f37-169">Se existirem outros registros MX na seção **MX (Mail Exchanger)**, exclua cada um deles.</span><span class="sxs-lookup"><span data-stu-id="90f37-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="90f37-170">Para um dos outros registros MX, selecione **excluir.**</span><span class="sxs-lookup"><span data-stu-id="90f37-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Selecione Excluir para cada registro MX adicional](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="90f37-172">Na caixa de diálogo de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90f37-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Selecione OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="90f37-174">Use o mesmo processo para excluir todos os outros registros MX que já foram listados.</span><span class="sxs-lookup"><span data-stu-id="90f37-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="90f37-175">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="90f37-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="90f37-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="90f37-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="90f37-177">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="90f37-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="90f37-178">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="90f37-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="90f37-179">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="90f37-180">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="90f37-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="90f37-181">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="90f37-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="90f37-182">Na seção registros **a (host)** , localize a linha do registro de **descoberta automática** e, em seguida, selecione **excluir** para essa linha.</span><span class="sxs-lookup"><span data-stu-id="90f37-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="90f37-183">Você deve excluir o registro de **descoberta automática** existente *antes* de adicionar o registro de **descoberta automática** necessário para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90f37-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="90f37-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span><span class="sxs-lookup"><span data-stu-id="90f37-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Selecione Excluir](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="90f37-186">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90f37-186">Select **OK**.</span></span>
    
    ![Selecione OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="90f37-188">Crie o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="90f37-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="90f37-189">Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="90f37-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="90f37-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="90f37-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90f37-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="90f37-191">**Host Record**</span></span>|<span data-ttu-id="90f37-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90f37-192">**TTL**</span></span>|<span data-ttu-id="90f37-193">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90f37-193">**Type**</span></span>|<span data-ttu-id="90f37-194">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="90f37-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90f37-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="90f37-195">autodiscover</span></span>  <br/> |<span data-ttu-id="90f37-196">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-196">14400</span></span>  <br/> |<span data-ttu-id="90f37-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="90f37-197">CNAME</span></span>  <br/> |<span data-ttu-id="90f37-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="90f37-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="90f37-199">sip</span><span class="sxs-lookup"><span data-stu-id="90f37-199">sip</span></span>  <br/> |<span data-ttu-id="90f37-200">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-200">14400</span></span>  <br/> |<span data-ttu-id="90f37-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="90f37-201">CNAME</span></span>  <br/> |<span data-ttu-id="90f37-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90f37-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="90f37-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="90f37-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="90f37-204">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-204">14400</span></span>  <br/> |<span data-ttu-id="90f37-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="90f37-205">CNAME</span></span>  <br/> |<span data-ttu-id="90f37-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90f37-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="90f37-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="90f37-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="90f37-208">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-208">14400</span></span>  <br/> |<span data-ttu-id="90f37-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="90f37-209">CNAME</span></span>  <br/> |<span data-ttu-id="90f37-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="90f37-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="90f37-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="90f37-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="90f37-212">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-212">14400</span></span>  <br/> |<span data-ttu-id="90f37-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="90f37-213">CNAME</span></span>  <br/> |<span data-ttu-id="90f37-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="90f37-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Criar o primeiro registro CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="90f37-216">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="90f37-216">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="90f37-218">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="90f37-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="90f37-219">Ainda na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="90f37-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="90f37-220">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="90f37-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="90f37-221">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="90f37-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="90f37-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="90f37-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="90f37-223">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="90f37-224">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="90f37-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="90f37-225">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90f37-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="90f37-226">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="90f37-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="90f37-227">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="90f37-227">Need examples?</span></span> <span data-ttu-id="90f37-228">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="90f37-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="90f37-229">Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="90f37-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="90f37-230">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="90f37-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="90f37-231">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="90f37-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="90f37-232">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="90f37-233">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="90f37-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="90f37-234">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="90f37-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="90f37-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="90f37-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="90f37-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="90f37-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="90f37-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="90f37-237">**Host Record**</span></span>|<span data-ttu-id="90f37-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90f37-238">**TTL**</span></span>|<span data-ttu-id="90f37-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90f37-239">**Type**</span></span>|<span data-ttu-id="90f37-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="90f37-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="90f37-241">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-241">14400</span></span>  <br/> |<span data-ttu-id="90f37-242">TXT</span><span class="sxs-lookup"><span data-stu-id="90f37-242">TXT</span></span>  <br/> |<span data-ttu-id="90f37-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="90f37-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="90f37-244">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="90f37-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar o valor TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="90f37-246">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="90f37-246">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="90f37-248">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="90f37-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="90f37-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="90f37-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="90f37-250">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="90f37-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="90f37-251">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="90f37-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="90f37-252">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="90f37-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="90f37-253">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="90f37-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="90f37-254">Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="90f37-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="90f37-255">Crie o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="90f37-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="90f37-256">Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="90f37-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="90f37-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="90f37-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="90f37-258">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="90f37-258">**Service**</span></span>|<span data-ttu-id="90f37-259">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="90f37-259">**Protocol**</span></span>|<span data-ttu-id="90f37-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="90f37-260">**Host**</span></span>|<span data-ttu-id="90f37-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="90f37-261">**TTL**</span></span>|<span data-ttu-id="90f37-262">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90f37-262">**Type**</span></span>|<span data-ttu-id="90f37-263">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="90f37-263">**Priority**</span></span>|<span data-ttu-id="90f37-264">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="90f37-264">**Weight**</span></span>|<span data-ttu-id="90f37-265">**Porta**</span><span class="sxs-lookup"><span data-stu-id="90f37-265">**Port**</span></span>|<span data-ttu-id="90f37-266">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="90f37-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="90f37-267">_sip</span><span class="sxs-lookup"><span data-stu-id="90f37-267">_sip</span></span>  <br/> |<span data-ttu-id="90f37-268">_tls</span><span class="sxs-lookup"><span data-stu-id="90f37-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="90f37-269">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-269">14400</span></span>  <br/> |<span data-ttu-id="90f37-270">SRV</span><span class="sxs-lookup"><span data-stu-id="90f37-270">SRV</span></span>  <br/> |<span data-ttu-id="90f37-271">100</span><span class="sxs-lookup"><span data-stu-id="90f37-271">100</span></span>  <br/> |<span data-ttu-id="90f37-272">1</span><span class="sxs-lookup"><span data-stu-id="90f37-272">1</span></span>  <br/> |<span data-ttu-id="90f37-273">443</span><span class="sxs-lookup"><span data-stu-id="90f37-273">443</span></span>  <br/> |<span data-ttu-id="90f37-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90f37-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="90f37-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="90f37-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="90f37-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="90f37-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="90f37-277">14400</span><span class="sxs-lookup"><span data-stu-id="90f37-277">14400</span></span>  <br/> |<span data-ttu-id="90f37-278">SRV</span><span class="sxs-lookup"><span data-stu-id="90f37-278">SRV</span></span>  <br/> |<span data-ttu-id="90f37-279">100</span><span class="sxs-lookup"><span data-stu-id="90f37-279">100</span></span>  <br/> |<span data-ttu-id="90f37-280">1</span><span class="sxs-lookup"><span data-stu-id="90f37-280">1</span></span>  <br/> |<span data-ttu-id="90f37-281">5061</span><span class="sxs-lookup"><span data-stu-id="90f37-281">5061</span></span>  <br/> |<span data-ttu-id="90f37-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="90f37-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiar o valor do novo registro](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="90f37-284">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="90f37-284">Select **add record**.</span></span>
    
    ![Selecionar Adicionar registro](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="90f37-286">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="90f37-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="90f37-287">Ainda na seção **adicionar registro DNS** , crie um registro usando os valores da outra linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="90f37-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="90f37-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="90f37-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="90f37-289">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="90f37-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="90f37-290">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="90f37-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

