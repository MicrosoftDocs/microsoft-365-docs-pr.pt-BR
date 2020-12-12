---
title: Criar registros DNS no cloudflare para Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em cloudflare para a Microsoft.
ms.openlocfilehash: 110bd96c0eecf40ae96efe7055d82a8d12dde607
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657955"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="e7117-103">Criar registros DNS no cloudflare para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7117-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="e7117-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="e7117-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e7117-105">Se o Cloudflare for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e7117-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e7117-106">Depois que você adicionar esses registros no Cloudflare, o domínio será configurado para funcionar com os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7117-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="e7117-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7117-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e7117-110">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="e7117-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="e7117-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="e7117-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7117-112">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e7117-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="e7117-113">Quando você se inscreveu no Cloudflare, adicionou um domínio usando o processo de **instalação** do cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e7117-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="e7117-114">O domínio adicionado foi comprado de Cloudflare ou de um registrador de domínio separado.</span><span class="sxs-lookup"><span data-stu-id="e7117-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="e7117-115">Para verificar e criar registros DNS para o seu domínio no Microsoft 365, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers do cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e7117-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="e7117-116">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7117-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="e7117-117">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e7117-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="e7117-118">Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.</span><span class="sxs-lookup"><span data-stu-id="e7117-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="e7117-119">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="e7117-119">First nameserver</span></span>  <br/> |<span data-ttu-id="e7117-120">Use o valor de nameserver fornecido pelo cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e7117-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="e7117-121">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="e7117-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="e7117-122">Use o valor de nameserver fornecido pelo cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e7117-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="e7117-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="e7117-123">You should use at least two name server records.</span></span> <span data-ttu-id="e7117-124">Se houver outros servidores de nomes listados, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="e7117-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="e7117-125">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="e7117-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7117-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="e7117-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e7117-127">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e7117-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e7117-128">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="e7117-128">Add a TXT record for verification</span></span>
<span data-ttu-id="e7117-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e7117-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e7117-p105">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="e7117-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7117-p106">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="e7117-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e7117-134">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e7117-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e7117-135">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e7117-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="e7117-136">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e7117-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e7117-137">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e7117-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e7117-138">Na página **Gerenciamento de DNS** , clique em **adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7117-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="e7117-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7117-139">**Type**</span></span>|<span data-ttu-id="e7117-140">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e7117-140">**Name**</span></span>|<span data-ttu-id="e7117-141">**TTL automático**</span><span class="sxs-lookup"><span data-stu-id="e7117-141">**Automatic TTL**</span></span>|<span data-ttu-id="e7117-142">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="e7117-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="e7117-143">TXT</span><span class="sxs-lookup"><span data-stu-id="e7117-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e7117-144">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-144">30 minutes</span></span>  <br/> |<span data-ttu-id="e7117-145">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e7117-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e7117-146">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e7117-146">**Note:** This is an example.</span></span> <span data-ttu-id="e7117-147">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="e7117-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e7117-148">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="e7117-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="e7117-149">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7117-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="e7117-150">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="e7117-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e7117-151">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e pesquisará o registro.</span><span class="sxs-lookup"><span data-stu-id="e7117-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="e7117-152">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="e7117-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e7117-153">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="e7117-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e7117-154">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="e7117-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e7117-155">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e7117-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e7117-156">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="e7117-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e7117-p109">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7117-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e7117-160">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7117-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e7117-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e7117-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e7117-162">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e7117-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e7117-163">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e7117-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="e7117-164">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e7117-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e7117-165">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e7117-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e7117-166">Na página **Gerenciamento de DNS** , clique em **adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7117-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="e7117-167">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7117-167">**Type**</span></span>|<span data-ttu-id="e7117-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e7117-168">**Name**</span></span>|<span data-ttu-id="e7117-169">**Servidor de email**</span><span class="sxs-lookup"><span data-stu-id="e7117-169">**Mail server**</span></span>|<span data-ttu-id="e7117-170">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="e7117-170">**Priority**</span></span>|<span data-ttu-id="e7117-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7117-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7117-172">MX</span><span class="sxs-lookup"><span data-stu-id="e7117-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="e7117-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e7117-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e7117-174">**Observação:** Acesse sua  *\<domain-key\>*  conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7117-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="e7117-175">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="e7117-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="e7117-176">1 </span><span class="sxs-lookup"><span data-stu-id="e7117-176">1</span></span>  <br/> <span data-ttu-id="e7117-177">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e7117-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="e7117-178">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="e7117-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7117-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="e7117-180">Se houver outros registros MX listados na seção **registros MX** , exclua-os selecionando o ícone **excluir (X)** .</span><span class="sxs-lookup"><span data-stu-id="e7117-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="e7117-181">Na caixa de diálogo de confirmação, selecione **excluir** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="e7117-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7117-182">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7117-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e7117-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e7117-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e7117-184">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e7117-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e7117-185">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e7117-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="e7117-186">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e7117-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e7117-187">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e7117-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e7117-188">Adicione o primeiro dos cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e7117-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="e7117-189">Na página **Gerenciamento de DNS** , clique em **adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7117-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="e7117-190">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7117-190">**Type**</span></span>|<span data-ttu-id="e7117-191">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e7117-191">**Name**</span></span>|<span data-ttu-id="e7117-192">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e7117-192">**Target**</span></span>|<span data-ttu-id="e7117-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7117-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7117-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7117-194">CNAME</span></span>  <br/> |<span data-ttu-id="e7117-195">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="e7117-195">autodiscover</span></span>  <br/> |<span data-ttu-id="e7117-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e7117-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="e7117-197">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e7117-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7117-198">CNAME</span></span>  <br/> |<span data-ttu-id="e7117-199">sip</span><span class="sxs-lookup"><span data-stu-id="e7117-199">sip</span></span>  <br/> |<span data-ttu-id="e7117-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7117-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e7117-201">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e7117-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7117-202">CNAME</span></span>  <br/> |<span data-ttu-id="e7117-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e7117-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e7117-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7117-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e7117-205">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e7117-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7117-206">CNAME</span></span>  <br/> |<span data-ttu-id="e7117-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e7117-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e7117-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e7117-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="e7117-209">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e7117-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7117-210">CNAME</span></span>  <br/> |<span data-ttu-id="e7117-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e7117-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e7117-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e7117-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="e7117-213">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="e7117-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7117-214">CNAME</span></span>  <br/> |<span data-ttu-id="e7117-215">msoid</span><span class="sxs-lookup"><span data-stu-id="e7117-215">msoid</span></span>  <br/> |<span data-ttu-id="e7117-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="e7117-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="e7117-217">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="e7117-218">Selecione o ícone de **tráfego DNS** (nuvem laranja) para ignorar os servidores cloudflare.</span><span class="sxs-lookup"><span data-stu-id="e7117-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="e7117-219">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7117-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="e7117-220">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e7117-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e7117-221">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="e7117-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e7117-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e7117-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7117-223">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="e7117-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e7117-224">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="e7117-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e7117-225">Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7117-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="e7117-226">Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e7117-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e7117-227">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e7117-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e7117-228">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e7117-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="e7117-229">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e7117-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e7117-230">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e7117-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="e7117-231">Na página **Gerenciamento de DNS** , clique em **adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7117-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="e7117-232">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7117-232">**Type**</span></span>|<span data-ttu-id="e7117-233">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e7117-233">**Name**</span></span>|<span data-ttu-id="e7117-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7117-234">**TTL**</span></span>|<span data-ttu-id="e7117-235">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="e7117-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7117-236">TXT</span><span class="sxs-lookup"><span data-stu-id="e7117-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e7117-237">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-237">30 minutes</span></span>  <br/> |<span data-ttu-id="e7117-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e7117-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e7117-239">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="e7117-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="e7117-240">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7117-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e7117-241">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7117-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e7117-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e7117-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7117-243">Tenha em mente que o Cloudflare é responsável por tornar essa funcionalidade disponível.</span><span class="sxs-lookup"><span data-stu-id="e7117-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="e7117-244">Caso você veja discrepâncias entre as etapas abaixo e a GUI atual do Cloudflare (interface gráfica do usuário), aproveite a [comunidade do Cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="e7117-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="e7117-245">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="e7117-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="e7117-246">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="e7117-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="e7117-247">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e7117-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="e7117-248">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e7117-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="e7117-249">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="e7117-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="e7117-250">Na página **Gerenciamento de DNS** , clique em **adicionar registro** e selecione os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7117-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="e7117-251">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7117-251">**Type**</span></span>|<span data-ttu-id="e7117-252">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="e7117-252">**Service**</span></span>|<span data-ttu-id="e7117-253">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="e7117-253">**Protocol**</span></span>|<span data-ttu-id="e7117-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e7117-254">**Name**</span></span>|<span data-ttu-id="e7117-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7117-255">**TTL**</span></span>|<span data-ttu-id="e7117-256">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="e7117-256">**Priority**</span></span>|<span data-ttu-id="e7117-257">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="e7117-257">**Weight**</span></span>|<span data-ttu-id="e7117-258">**Porta**</span><span class="sxs-lookup"><span data-stu-id="e7117-258">**Port**</span></span>|<span data-ttu-id="e7117-259">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e7117-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7117-260">SRV</span><span class="sxs-lookup"><span data-stu-id="e7117-260">SRV</span></span>|<span data-ttu-id="e7117-261">_sip</span><span class="sxs-lookup"><span data-stu-id="e7117-261">_sip</span></span> |<span data-ttu-id="e7117-262">TLS</span><span class="sxs-lookup"><span data-stu-id="e7117-262">TLS</span></span> |<span data-ttu-id="e7117-263">Use seu *domain_name*; por exemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="e7117-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="e7117-264">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-264">30 minutes</span></span> | <span data-ttu-id="e7117-265">100</span><span class="sxs-lookup"><span data-stu-id="e7117-265">100</span></span>|<span data-ttu-id="e7117-266">1 </span><span class="sxs-lookup"><span data-stu-id="e7117-266">1</span></span> |<span data-ttu-id="e7117-267">443</span><span class="sxs-lookup"><span data-stu-id="e7117-267">443</span></span> |<span data-ttu-id="e7117-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7117-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="e7117-269">SRV</span><span class="sxs-lookup"><span data-stu-id="e7117-269">SRV</span></span>|<span data-ttu-id="e7117-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e7117-270">_sipfederationtls</span></span> | <span data-ttu-id="e7117-271">TCP</span><span class="sxs-lookup"><span data-stu-id="e7117-271">TCP</span></span>|<span data-ttu-id="e7117-272">Use seu *domain_name*; por exemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="e7117-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="e7117-273">30 minutos</span><span class="sxs-lookup"><span data-stu-id="e7117-273">30 minutes</span></span> |<span data-ttu-id="e7117-274">100</span><span class="sxs-lookup"><span data-stu-id="e7117-274">100</span></span> |<span data-ttu-id="e7117-275">1 </span><span class="sxs-lookup"><span data-stu-id="e7117-275">1</span></span> |<span data-ttu-id="e7117-276">5061</span><span class="sxs-lookup"><span data-stu-id="e7117-276">5061</span></span> | <span data-ttu-id="e7117-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7117-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="e7117-278">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7117-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="e7117-279">Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="e7117-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="e7117-p117">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e7117-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
