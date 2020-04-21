---
title: Criar registros DNS no GoDaddy para Microsoft
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em GoDaddy para a Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: 0e9b75bcd4aa93270efd9b2d94fa2ceeb6e55f75
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629546"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="6d9c1-103">Criar registros DNS no GoDaddy para Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d9c1-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="6d9c1-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="6d9c1-105">Se você usa a GoDaddy como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="6d9c1-106">Depois que você adicionar esses registros no GoDaddy, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

<span data-ttu-id="6d9c1-107">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6d9c1-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="6d9c1-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6d9c1-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="6d9c1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6d9c1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6d9c1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6d9c1-113">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6d9c1-114">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="6d9c1-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="6d9c1-117">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-117">Follow the steps below.</span></span>

1. <span data-ttu-id="6d9c1-p104">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="6d9c1-121">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="6d9c1-123">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-123">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="6d9c1-125">Escolha o **TXT (texto)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="6d9c1-126">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="6d9c1-127">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-127">**Record type**</span></span> |<span data-ttu-id="6d9c1-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-128">**Host**</span></span>|<span data-ttu-id="6d9c1-129">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-129">**TXT Value**</span></span>|<span data-ttu-id="6d9c1-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d9c1-131">TXT (Texto)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-131">TXT (Text)</span></span>|@|<span data-ttu-id="6d9c1-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6d9c1-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="6d9c1-133">**Observação**: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-133">**Note**: This is an example.</span></span> <span data-ttu-id="6d9c1-134">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="6d9c1-135">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="6d9c1-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="6d9c1-136">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-136">1 hour</span></span>  <br><span data-ttu-id="6d9c1-137">(Selecione um valor na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="6d9c1-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-139">Select **Save**.</span></span>

6. <span data-ttu-id="6d9c1-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="6d9c1-141">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="6d9c1-142">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6d9c1-143">No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="6d9c1-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6d9c1-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6d9c1-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="6d9c1-146">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="6d9c1-p107">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6d9c1-150">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d9c1-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6d9c1-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6d9c1-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="6d9c1-152">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-152">Follow the steps below.</span></span>

1. <span data-ttu-id="6d9c1-p108">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="6d9c1-156">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="6d9c1-158">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-158">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="6d9c1-160">Escolha **MX (Mail Exchanger)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="6d9c1-162">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="6d9c1-163">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="6d9c1-164">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-164">**Record type**</span></span>|<span data-ttu-id="6d9c1-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-165">**Host**</span></span>|<span data-ttu-id="6d9c1-166">**Pontos de**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-166">**Points to**</span></span>|<span data-ttu-id="6d9c1-167">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-167">**Priority**</span></span>|<span data-ttu-id="6d9c1-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d9c1-169">Servidor de mensagens (MX)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="6d9c1-170">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6d9c1-171">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="6d9c1-172">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="6d9c1-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6d9c1-173">10 </span><span class="sxs-lookup"><span data-stu-id="6d9c1-173">10</span></span>  <br/> <span data-ttu-id="6d9c1-174">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="6d9c1-175">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="6d9c1-176">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6d9c1-177">Adicionar os registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d9c1-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6d9c1-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6d9c1-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="6d9c1-179">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-179">Follow the steps below.</span></span>

1. <span data-ttu-id="6d9c1-p110">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="6d9c1-183">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="6d9c1-185">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-185">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="6d9c1-187">Escolha **CNAME (alias)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="6d9c1-189">Criar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="6d9c1-190">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="6d9c1-191">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="6d9c1-192">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-192">**Record type**</span></span>|<span data-ttu-id="6d9c1-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-193">**Host**</span></span>|<span data-ttu-id="6d9c1-194">**Pontos de**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-194">**Points to**</span></span>|<span data-ttu-id="6d9c1-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d9c1-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="6d9c1-197">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="6d9c1-197">autodiscover</span></span>  <br/> |<span data-ttu-id="6d9c1-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="6d9c1-199">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="6d9c1-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="6d9c1-201">sip</span><span class="sxs-lookup"><span data-stu-id="6d9c1-201">sip</span></span>  <br/> |<span data-ttu-id="6d9c1-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6d9c1-203">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="6d9c1-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="6d9c1-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6d9c1-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6d9c1-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6d9c1-207">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="6d9c1-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="6d9c1-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6d9c1-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6d9c1-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6d9c1-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="6d9c1-211">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="6d9c1-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="6d9c1-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6d9c1-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6d9c1-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="6d9c1-215">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="6d9c1-216">Repita essas etapas para adicionar o próximo registro CNAME até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6d9c1-217">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="6d9c1-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6d9c1-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6d9c1-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d9c1-219">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6d9c1-220">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6d9c1-221">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6d9c1-222">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="6d9c1-223">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-223">Follow the steps below.</span></span>

1. <span data-ttu-id="6d9c1-p112">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="6d9c1-227">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="6d9c1-229">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-229">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="6d9c1-231">Escolha o **TXT (texto)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="6d9c1-233">Nas caixas do novo registro, digite ou copie e cole os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="6d9c1-234">(Escolha o valor **TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="6d9c1-235">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-235">**Record type**</span></span>|<span data-ttu-id="6d9c1-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-236">**Host**</span></span>|<span data-ttu-id="6d9c1-237">**Valor TXT**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-237">**TXT Value**</span></span>|<span data-ttu-id="6d9c1-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d9c1-239">TXT (Texto)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="6d9c1-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6d9c1-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6d9c1-241">**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="6d9c1-242">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="6d9c1-244">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6d9c1-245">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d9c1-245">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6d9c1-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6d9c1-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="6d9c1-247">Siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-247">Follow the steps below.</span></span>

1. <span data-ttu-id="6d9c1-p113">Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="6d9c1-251">Em **domínios**, selecione DNS no domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="6d9c1-253">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-253">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="6d9c1-255">Escolha o **SRV (Serviço)** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="6d9c1-257">Crie o primeiro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-257">Create the first SRV record.</span></span>

    <span data-ttu-id="6d9c1-258">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="6d9c1-259">(Escolha os valores **tipo de registro** e **TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="6d9c1-260">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-260">**Record type**</span></span>|<span data-ttu-id="6d9c1-261">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-261">**Name**</span></span>|<span data-ttu-id="6d9c1-262">**Destino**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-262">**Target**</span></span>|<span data-ttu-id="6d9c1-263">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-263">**Protocol**</span></span>|<span data-ttu-id="6d9c1-264">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-264">**Service**</span></span>|<span data-ttu-id="6d9c1-265">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-265">**Priority**</span></span>|<span data-ttu-id="6d9c1-266">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-266">**Weight**</span></span>|<span data-ttu-id="6d9c1-267">**Porta**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-267">**Port**</span></span>|<span data-ttu-id="6d9c1-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d9c1-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d9c1-269">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="6d9c1-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6d9c1-271">_tls</span><span class="sxs-lookup"><span data-stu-id="6d9c1-271">_tls</span></span>  <br/> |<span data-ttu-id="6d9c1-272">_sip</span><span class="sxs-lookup"><span data-stu-id="6d9c1-272">_sip</span></span>  <br/> |<span data-ttu-id="6d9c1-273">100</span><span class="sxs-lookup"><span data-stu-id="6d9c1-273">100</span></span>  <br/> |<span data-ttu-id="6d9c1-274">1</span><span class="sxs-lookup"><span data-stu-id="6d9c1-274">1</span></span>  <br/> |<span data-ttu-id="6d9c1-275">443</span><span class="sxs-lookup"><span data-stu-id="6d9c1-275">443</span></span>  <br/> |<span data-ttu-id="6d9c1-276">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="6d9c1-277">SRV (Serviço)</span><span class="sxs-lookup"><span data-stu-id="6d9c1-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="6d9c1-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d9c1-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="6d9c1-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="6d9c1-279">_tcp</span></span>  <br/> |<span data-ttu-id="6d9c1-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="6d9c1-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="6d9c1-281">100</span><span class="sxs-lookup"><span data-stu-id="6d9c1-281">100</span></span>  <br/> |<span data-ttu-id="6d9c1-282">1</span><span class="sxs-lookup"><span data-stu-id="6d9c1-282">1</span></span>  <br/> |<span data-ttu-id="6d9c1-283">5061</span><span class="sxs-lookup"><span data-stu-id="6d9c1-283">5061</span></span>  <br/> |<span data-ttu-id="6d9c1-284">1 hora</span><span class="sxs-lookup"><span data-stu-id="6d9c1-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="6d9c1-286">Repita a **etapa 5** para criar o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="6d9c1-287">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d9c1-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6d9c1-p114">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6d9c1-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
