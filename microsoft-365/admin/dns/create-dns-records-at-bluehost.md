---
title: Criar registros DNS no Bluehost para Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços na Bluehost para Microsoft.
ms.openlocfilehash: a9de709b0981c3e74eec1a3ea0e0452d068c5ad4
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658142"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="53b59-103">Criar registros DNS no Bluehost para Microsoft</span><span class="sxs-lookup"><span data-stu-id="53b59-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="53b59-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="53b59-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="53b59-105">Se você usa a Bluehost como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="53b59-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="53b59-106">Depois que você adicionar esses registros no Bluehost, o domínio será definido para funcionar com os serviços Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53b59-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="53b59-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="53b59-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="53b59-108">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="53b59-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="53b59-109">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="53b59-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="53b59-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="53b59-110">Add a TXT record for verification</span></span>
<span data-ttu-id="53b59-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="53b59-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="53b59-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53b59-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="53b59-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="53b59-116">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="53b59-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="53b59-117">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="53b59-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="53b59-118">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="53b59-119">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="53b59-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="53b59-120">Na área **_domain_name_*_ , na linha _\* Editor de Zona DNS,*\* selecione Gerenciar registros **DNS.**</span><span class="sxs-lookup"><span data-stu-id="53b59-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="53b59-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="53b59-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="53b59-122">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="53b59-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="53b59-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="53b59-123">**Host Record**</span></span> <br/> |<span data-ttu-id="53b59-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53b59-124">**TTL**</span></span> <br/> |<span data-ttu-id="53b59-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53b59-125">**Type**</span></span> <br/> |<span data-ttu-id="53b59-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="53b59-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="53b59-127">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-127">14400</span></span>  <br/> |<span data-ttu-id="53b59-128">TXT</span><span class="sxs-lookup"><span data-stu-id="53b59-128">TXT</span></span>  <br/> |<span data-ttu-id="53b59-129">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="53b59-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="53b59-130">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="53b59-130">**Note:** This is an example.</span></span> <span data-ttu-id="53b59-131">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="53b59-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="53b59-132">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="53b59-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="53b59-133">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="53b59-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="53b59-134">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="53b59-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="53b59-135">Agora que você adicionou o registro no site do registrador de domínios, volte para a Microsoft e solicite uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="53b59-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="53b59-136">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="53b59-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="53b59-137">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="53b59-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="53b59-138">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="53b59-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="53b59-139">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="53b59-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="53b59-140">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="53b59-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="53b59-141">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="53b59-141">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="53b59-142">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="53b59-142">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="53b59-143">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="53b59-143">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="53b59-144">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53b59-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="53b59-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="53b59-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="53b59-146">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="53b59-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="53b59-147">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="53b59-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="53b59-148">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="53b59-149">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="53b59-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="53b59-150">Na área **_domain_name_*_ , na linha _\* Editor de Zona DNS,*\* selecione Gerenciar registros **DNS.**</span><span class="sxs-lookup"><span data-stu-id="53b59-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="53b59-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="53b59-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="53b59-152">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="53b59-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="53b59-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="53b59-153">**Host Record**</span></span>|<span data-ttu-id="53b59-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53b59-154">**TTL**</span></span>|<span data-ttu-id="53b59-155">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53b59-155">**Type**</span></span>|<span data-ttu-id="53b59-156">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="53b59-156">**Points To**</span></span>|<span data-ttu-id="53b59-157">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="53b59-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="53b59-158">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-158">14400</span></span>  <br/> |<span data-ttu-id="53b59-159">MX</span><span class="sxs-lookup"><span data-stu-id="53b59-159">MX</span></span>  <br/> | <span data-ttu-id="53b59-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="53b59-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="53b59-161">**Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53b59-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="53b59-162">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="53b59-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="53b59-163">0</span><span class="sxs-lookup"><span data-stu-id="53b59-163">0</span></span>  <br/> <span data-ttu-id="53b59-164">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="53b59-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Choose Type from the drop-down list](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="53b59-166">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="53b59-166">Select **add record**.</span></span>
    
    ![Selecionar Adicionar Registro](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="53b59-168">Se existirem outros registros MX na seção **MX (Mail Exchanger)**, exclua cada um deles.</span><span class="sxs-lookup"><span data-stu-id="53b59-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="53b59-169">Para um dos outros registros MX, selecione **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="53b59-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Selecione Excluir para cada registro MX adicional](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="53b59-171">Na caixa de diálogo de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="53b59-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Selecione OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="53b59-173">Use o mesmo processo para excluir todos os outros registros MX que já foram listados.</span><span class="sxs-lookup"><span data-stu-id="53b59-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="53b59-174">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="53b59-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="53b59-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="53b59-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="53b59-176">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="53b59-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="53b59-177">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="53b59-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="53b59-178">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="53b59-179">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="53b59-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="53b59-180">Na área **_domain_name_*_ , na linha _\* Editor de Zona DNS,*\* selecione Gerenciar registros **DNS.**</span><span class="sxs-lookup"><span data-stu-id="53b59-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="53b59-181">Na seção **registros A (Host),** encontre a linha do registro **de descoberta** automática e selecione **excluir** para essa linha.</span><span class="sxs-lookup"><span data-stu-id="53b59-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="53b59-182">Você deve excluir o registro de descoberta  **automática** existente *antes* de adicionar o registro de descoberta automática exigido pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53b59-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="53b59-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span><span class="sxs-lookup"><span data-stu-id="53b59-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Selecionar Excluir](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="53b59-185">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="53b59-185">Select **OK**.</span></span>
    
    ![Selecione OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="53b59-187">Crie o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="53b59-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="53b59-188">Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="53b59-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="53b59-189">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="53b59-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="53b59-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="53b59-190">**Host Record**</span></span>|<span data-ttu-id="53b59-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53b59-191">**TTL**</span></span>|<span data-ttu-id="53b59-192">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53b59-192">**Type**</span></span>|<span data-ttu-id="53b59-193">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="53b59-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="53b59-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="53b59-194">autodiscover</span></span>  <br/> |<span data-ttu-id="53b59-195">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-195">14400</span></span>  <br/> |<span data-ttu-id="53b59-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="53b59-196">CNAME</span></span>  <br/> |<span data-ttu-id="53b59-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="53b59-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="53b59-198">sip</span><span class="sxs-lookup"><span data-stu-id="53b59-198">sip</span></span>  <br/> |<span data-ttu-id="53b59-199">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-199">14400</span></span>  <br/> |<span data-ttu-id="53b59-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="53b59-200">CNAME</span></span>  <br/> |<span data-ttu-id="53b59-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53b59-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="53b59-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="53b59-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="53b59-203">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-203">14400</span></span>  <br/> |<span data-ttu-id="53b59-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="53b59-204">CNAME</span></span>  <br/> |<span data-ttu-id="53b59-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53b59-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="53b59-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="53b59-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="53b59-207">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-207">14400</span></span>  <br/> |<span data-ttu-id="53b59-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="53b59-208">CNAME</span></span>  <br/> |<span data-ttu-id="53b59-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="53b59-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="53b59-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="53b59-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="53b59-211">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-211">14400</span></span>  <br/> |<span data-ttu-id="53b59-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="53b59-212">CNAME</span></span>  <br/> |<span data-ttu-id="53b59-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="53b59-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Criar o primeiro registro CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="53b59-215">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="53b59-215">Select **add record**.</span></span>
    
    ![Selecionar Adicionar Registro](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="53b59-217">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="53b59-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="53b59-218">Ainda na seção **Adicionar Registro DNS,** crie um registro usando os valores da  próxima linha na tabela e selecione novamente adicionar registro para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="53b59-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="53b59-219">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="53b59-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="53b59-220">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="53b59-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="53b59-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="53b59-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="53b59-222">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="53b59-223">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="53b59-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="53b59-224">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53b59-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="53b59-225">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="53b59-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="53b59-226">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="53b59-226">Need examples?</span></span> <span data-ttu-id="53b59-227">Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="53b59-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="53b59-228">Para validar seu registro SPF, você pode usar uma destas ferramentas de[validação de SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="53b59-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="53b59-229">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="53b59-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="53b59-230">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="53b59-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="53b59-231">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="53b59-232">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="53b59-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="53b59-233">Na área **_domain_name_*_ , na linha _\* Editor de Zona DNS,*\* selecione Gerenciar registros **DNS.**</span><span class="sxs-lookup"><span data-stu-id="53b59-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="53b59-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="53b59-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="53b59-235">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="53b59-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="53b59-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="53b59-236">**Host Record**</span></span>|<span data-ttu-id="53b59-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53b59-237">**TTL**</span></span>|<span data-ttu-id="53b59-238">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53b59-238">**Type**</span></span>|<span data-ttu-id="53b59-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="53b59-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="53b59-240">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-240">14400</span></span>  <br/> |<span data-ttu-id="53b59-241">TXT</span><span class="sxs-lookup"><span data-stu-id="53b59-241">TXT</span></span>  <br/> |<span data-ttu-id="53b59-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="53b59-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="53b59-243">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="53b59-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiar o valor TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="53b59-245">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="53b59-245">Select **add record**.</span></span>
    
    ![Selecionar Adicionar Registro](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="53b59-247">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="53b59-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="53b59-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="53b59-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="53b59-249">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="53b59-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="53b59-250">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="53b59-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="53b59-251">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="53b59-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="53b59-252">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="53b59-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="53b59-253">Na área **_domain_name_*_ , na linha _\* Editor de Zona DNS,*\* selecione Gerenciar registros **DNS.**</span><span class="sxs-lookup"><span data-stu-id="53b59-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="53b59-254">Crie o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="53b59-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="53b59-255">Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="53b59-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="53b59-256">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="53b59-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="53b59-257">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="53b59-257">**Service**</span></span>|<span data-ttu-id="53b59-258">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="53b59-258">**Protocol**</span></span>|<span data-ttu-id="53b59-259">**Host**</span><span class="sxs-lookup"><span data-stu-id="53b59-259">**Host**</span></span>|<span data-ttu-id="53b59-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53b59-260">**TTL**</span></span>|<span data-ttu-id="53b59-261">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53b59-261">**Type**</span></span>|<span data-ttu-id="53b59-262">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="53b59-262">**Priority**</span></span>|<span data-ttu-id="53b59-263">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="53b59-263">**Weight**</span></span>|<span data-ttu-id="53b59-264">**Porta**</span><span class="sxs-lookup"><span data-stu-id="53b59-264">**Port**</span></span>|<span data-ttu-id="53b59-265">**Aponta para**</span><span class="sxs-lookup"><span data-stu-id="53b59-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="53b59-266">_sip</span><span class="sxs-lookup"><span data-stu-id="53b59-266">_sip</span></span>  <br/> |<span data-ttu-id="53b59-267">_tls</span><span class="sxs-lookup"><span data-stu-id="53b59-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="53b59-268">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-268">14400</span></span>  <br/> |<span data-ttu-id="53b59-269">SRV</span><span class="sxs-lookup"><span data-stu-id="53b59-269">SRV</span></span>  <br/> |<span data-ttu-id="53b59-270">100</span><span class="sxs-lookup"><span data-stu-id="53b59-270">100</span></span>  <br/> |<span data-ttu-id="53b59-271">1 </span><span class="sxs-lookup"><span data-stu-id="53b59-271">1</span></span>  <br/> |<span data-ttu-id="53b59-272">443</span><span class="sxs-lookup"><span data-stu-id="53b59-272">443</span></span>  <br/> |<span data-ttu-id="53b59-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53b59-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="53b59-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="53b59-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="53b59-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="53b59-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="53b59-276">14400</span><span class="sxs-lookup"><span data-stu-id="53b59-276">14400</span></span>  <br/> |<span data-ttu-id="53b59-277">SRV</span><span class="sxs-lookup"><span data-stu-id="53b59-277">SRV</span></span>  <br/> |<span data-ttu-id="53b59-278">100</span><span class="sxs-lookup"><span data-stu-id="53b59-278">100</span></span>  <br/> |<span data-ttu-id="53b59-279">1 </span><span class="sxs-lookup"><span data-stu-id="53b59-279">1</span></span>  <br/> |<span data-ttu-id="53b59-280">5061</span><span class="sxs-lookup"><span data-stu-id="53b59-280">5061</span></span>  <br/> |<span data-ttu-id="53b59-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53b59-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Copiar o valor do novo registro](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="53b59-283">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="53b59-283">Select **add record**.</span></span>
    
    ![Selecionar Adicionar Registro](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="53b59-285">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="53b59-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="53b59-286">Ainda na seção **Adicionar Registro DNS,** crie um registro usando os valores da  outra linha na tabela e selecione novamente adicionar registro para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="53b59-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="53b59-287">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="53b59-287">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="53b59-288">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="53b59-288">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="53b59-289">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="53b59-289">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

