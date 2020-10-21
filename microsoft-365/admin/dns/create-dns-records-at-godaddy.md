---
title: Criar registros DNS no GoDaddy para Microsoft
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em GoDaddy para a Microsoft.
ms.openlocfilehash: 995e579e21a185084d9ee64a7ee462930d845844
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646122"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="18c3f-103">Criar registros DNS no GoDaddy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c3f-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="18c3f-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="18c3f-105">Se você usa a GoDaddy como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="18c3f-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="18c3f-106">Depois que você adicionar esses registros no GoDaddy, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18c3f-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="18c3f-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18c3f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="18c3f-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="18c3f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="18c3f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="18c3f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="18c3f-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="18c3f-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="18c3f-116">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="18c3f-116">Follow the steps below.</span></span>

1. <span data-ttu-id="18c3f-p104">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="18c3f-120">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="18c3f-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="18c3f-122">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-122">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="18c3f-124">Escolha o **TXT (texto)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="18c3f-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="18c3f-125">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="18c3f-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="18c3f-126">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="18c3f-126">**Record type**</span></span> |<span data-ttu-id="18c3f-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="18c3f-127">**Host**</span></span>|<span data-ttu-id="18c3f-128">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="18c3f-128">**TXT Value**</span></span>|<span data-ttu-id="18c3f-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="18c3f-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18c3f-130">TXT (Texto)</span><span class="sxs-lookup"><span data-stu-id="18c3f-130">TXT (Text)</span></span>|@|<span data-ttu-id="18c3f-131">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="18c3f-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="18c3f-132">**Observação**: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="18c3f-132">**Note**: This is an example.</span></span> <span data-ttu-id="18c3f-133">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="18c3f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="18c3f-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="18c3f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="18c3f-135">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-135">1 hour</span></span>  <br><span data-ttu-id="18c3f-136">(Selecione um valor na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="18c3f-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="18c3f-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-138">Select **Save**.</span></span>

6. <span data-ttu-id="18c3f-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="18c3f-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="18c3f-140">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="18c3f-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="18c3f-141">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="18c3f-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="18c3f-142">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="18c3f-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="18c3f-143">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="18c3f-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="18c3f-144">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="18c3f-145">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="18c3f-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18c3f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="18c3f-149">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18c3f-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="18c3f-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="18c3f-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="18c3f-151">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="18c3f-151">Follow the steps below.</span></span>

1. <span data-ttu-id="18c3f-p108">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="18c3f-155">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="18c3f-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="18c3f-157">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-157">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="18c3f-159">Escolha **MX (Mail Exchanger)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="18c3f-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="18c3f-161">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="18c3f-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="18c3f-162">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="18c3f-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="18c3f-163">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="18c3f-163">**Record type**</span></span>|<span data-ttu-id="18c3f-164">**Host**</span><span class="sxs-lookup"><span data-stu-id="18c3f-164">**Host**</span></span>|<span data-ttu-id="18c3f-165">**Pontos de**</span><span class="sxs-lookup"><span data-stu-id="18c3f-165">**Points to**</span></span>|<span data-ttu-id="18c3f-166">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="18c3f-166">**Priority**</span></span>|<span data-ttu-id="18c3f-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="18c3f-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18c3f-168">Servidor de mensagens (MX)</span><span class="sxs-lookup"><span data-stu-id="18c3f-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="18c3f-169">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="18c3f-170">**Observação:** Acesse sua  *\<domain-key\>*  conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18c3f-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="18c3f-171">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="18c3f-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="18c3f-172">10 </span><span class="sxs-lookup"><span data-stu-id="18c3f-172">10</span></span>  <br/> <span data-ttu-id="18c3f-173">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="18c3f-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="18c3f-174">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="18c3f-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="18c3f-176">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c3f-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="18c3f-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="18c3f-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="18c3f-178">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="18c3f-178">Follow the steps below.</span></span>

1. <span data-ttu-id="18c3f-p110">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="18c3f-182">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="18c3f-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="18c3f-184">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-184">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="18c3f-186">Escolha **CNAME (alias)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="18c3f-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="18c3f-188">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="18c3f-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="18c3f-189">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="18c3f-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="18c3f-190">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="18c3f-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="18c3f-191">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="18c3f-191">**Record type**</span></span>|<span data-ttu-id="18c3f-192">**Host**</span><span class="sxs-lookup"><span data-stu-id="18c3f-192">**Host**</span></span>|<span data-ttu-id="18c3f-193">**Pontos de**</span><span class="sxs-lookup"><span data-stu-id="18c3f-193">**Points to**</span></span>|<span data-ttu-id="18c3f-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="18c3f-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18c3f-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="18c3f-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="18c3f-196">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="18c3f-196">autodiscover</span></span>  <br/> |<span data-ttu-id="18c3f-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="18c3f-198">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="18c3f-199">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="18c3f-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="18c3f-200">sip</span><span class="sxs-lookup"><span data-stu-id="18c3f-200">sip</span></span>  <br/> |<span data-ttu-id="18c3f-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="18c3f-202">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="18c3f-203">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="18c3f-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="18c3f-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="18c3f-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="18c3f-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="18c3f-206">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="18c3f-207">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="18c3f-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="18c3f-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="18c3f-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="18c3f-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="18c3f-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="18c3f-210">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="18c3f-211">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="18c3f-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="18c3f-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="18c3f-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="18c3f-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="18c3f-214">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="18c3f-215">Repita essas etapas para adicionar o próximo registro CNAME até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="18c3f-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="18c3f-216">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="18c3f-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="18c3f-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="18c3f-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="18c3f-218">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="18c3f-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="18c3f-219">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="18c3f-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="18c3f-220">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18c3f-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="18c3f-221">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="18c3f-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="18c3f-222">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="18c3f-222">Follow the steps below.</span></span>

1. <span data-ttu-id="18c3f-p112">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="18c3f-226">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="18c3f-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="18c3f-228">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-228">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="18c3f-230">Escolha o **TXT (texto)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="18c3f-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="18c3f-232">Nas caixas do novo registro, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="18c3f-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="18c3f-233">(Escolha o valor **TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="18c3f-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="18c3f-234">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="18c3f-234">**Record type**</span></span>|<span data-ttu-id="18c3f-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="18c3f-235">**Host**</span></span>|<span data-ttu-id="18c3f-236">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="18c3f-236">**TXT Value**</span></span>|<span data-ttu-id="18c3f-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="18c3f-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18c3f-238">TXT (Texto)</span><span class="sxs-lookup"><span data-stu-id="18c3f-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="18c3f-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="18c3f-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="18c3f-240">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="18c3f-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="18c3f-241">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="18c3f-243">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="18c3f-244">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c3f-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="18c3f-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="18c3f-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="18c3f-246">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="18c3f-246">Follow the steps below.</span></span>

1. <span data-ttu-id="18c3f-p113">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="18c3f-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="18c3f-250">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="18c3f-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="18c3f-252">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-252">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="18c3f-254">Escolha o **SRV (Serviço)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="18c3f-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="18c3f-256">Crie o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="18c3f-256">Create the first SRV record.</span></span>

    <span data-ttu-id="18c3f-257">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="18c3f-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="18c3f-258">(Escolha os valores **tipo de registro** e **TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="18c3f-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="18c3f-259">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="18c3f-259">**Record type**</span></span>|<span data-ttu-id="18c3f-260">**Nome**</span><span class="sxs-lookup"><span data-stu-id="18c3f-260">**Name**</span></span>|<span data-ttu-id="18c3f-261">**Destino**</span><span class="sxs-lookup"><span data-stu-id="18c3f-261">**Target**</span></span>|<span data-ttu-id="18c3f-262">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="18c3f-262">**Protocol**</span></span>|<span data-ttu-id="18c3f-263">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="18c3f-263">**Service**</span></span>|<span data-ttu-id="18c3f-264">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="18c3f-264">**Priority**</span></span>|<span data-ttu-id="18c3f-265">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="18c3f-265">**Weight**</span></span>|<span data-ttu-id="18c3f-266">**Porta**</span><span class="sxs-lookup"><span data-stu-id="18c3f-266">**Port**</span></span>|<span data-ttu-id="18c3f-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="18c3f-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="18c3f-268">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="18c3f-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="18c3f-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="18c3f-270">_tls</span><span class="sxs-lookup"><span data-stu-id="18c3f-270">_tls</span></span>  <br/> |<span data-ttu-id="18c3f-271">_sip</span><span class="sxs-lookup"><span data-stu-id="18c3f-271">_sip</span></span>  <br/> |<span data-ttu-id="18c3f-272">100</span><span class="sxs-lookup"><span data-stu-id="18c3f-272">100</span></span>  <br/> |<span data-ttu-id="18c3f-273">1</span><span class="sxs-lookup"><span data-stu-id="18c3f-273">1</span></span>  <br/> |<span data-ttu-id="18c3f-274">443</span><span class="sxs-lookup"><span data-stu-id="18c3f-274">443</span></span>  <br/> |<span data-ttu-id="18c3f-275">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="18c3f-276">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="18c3f-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="18c3f-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="18c3f-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="18c3f-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="18c3f-278">_tcp</span></span>  <br/> |<span data-ttu-id="18c3f-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="18c3f-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="18c3f-280">100</span><span class="sxs-lookup"><span data-stu-id="18c3f-280">100</span></span>  <br/> |<span data-ttu-id="18c3f-281">1</span><span class="sxs-lookup"><span data-stu-id="18c3f-281">1</span></span>  <br/> |<span data-ttu-id="18c3f-282">5061</span><span class="sxs-lookup"><span data-stu-id="18c3f-282">5061</span></span>  <br/> |<span data-ttu-id="18c3f-283">1 hora</span><span class="sxs-lookup"><span data-stu-id="18c3f-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="18c3f-285">Repita a **etapa 5** para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="18c3f-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="18c3f-286">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18c3f-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="18c3f-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18c3f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
