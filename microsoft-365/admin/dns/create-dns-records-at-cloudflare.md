---
title: Criar registros DNS no Cloudflare para a Microsoft
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
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços na Cloudflare para Microsoft.
ms.openlocfilehash: 8d5dd7779f07fd42dd230ee33c40849da3519d26
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939267"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="068e1-103">Criar registros DNS no Cloudflare para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="068e1-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="068e1-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="068e1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="068e1-105">Se o Cloudflare for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="068e1-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="068e1-106">Depois que você adicionar esses registros na Cloudflare, seu domínio será definido para funcionar com os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="068e1-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="068e1-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="068e1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="068e1-110">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="068e1-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="068e1-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="068e1-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="068e1-112">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="068e1-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="068e1-113">Quando você se inscreveu no Cloudflare, adicionou  um domínio usando o processo de instalação cloudflare.</span><span class="sxs-lookup"><span data-stu-id="068e1-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="068e1-114">O domínio adicionado foi adquirido do Cloudflare ou de um registrador de domínios separado.</span><span class="sxs-lookup"><span data-stu-id="068e1-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="068e1-115">Para verificar e criar registros DNS para seu domínio no Microsoft 365, primeiro você precisa alterar os nameservers no registrador de domínios para que eles usem os nameservers do Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="068e1-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="068e1-116">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="068e1-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="068e1-117">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="068e1-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="068e1-118">Crie dois registros de nameserver usando os valores da tabela a seguir ou edite os registros de nameserver existentes para que eles corresponderem a esses valores.</span><span class="sxs-lookup"><span data-stu-id="068e1-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="068e1-119">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="068e1-119">First nameserver</span></span>  <br/> |<span data-ttu-id="068e1-120">Use o valor de nameserver fornecido pelo Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="068e1-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="068e1-121">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="068e1-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="068e1-122">Use o valor de nameserver fornecido pelo Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="068e1-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="068e1-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="068e1-123">You should use at least two name server records.</span></span> <span data-ttu-id="068e1-124">Se houver outros servidores de nomes listados, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="068e1-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="068e1-125">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="068e1-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="068e1-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="068e1-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="068e1-127">Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="068e1-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="068e1-128">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="068e1-128">Add a TXT record for verification</span></span>
<span data-ttu-id="068e1-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="068e1-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="068e1-p105">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="068e1-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="068e1-p106">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="068e1-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="068e1-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="068e1-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="068e1-135">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="068e1-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="068e1-136">Na **home** page, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="068e1-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="068e1-137">Na página **Visão** geral do seu domínio, selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="068e1-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="068e1-138">Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="068e1-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="068e1-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="068e1-139">Type</span></span> | <span data-ttu-id="068e1-140">Nome</span><span class="sxs-lookup"><span data-stu-id="068e1-140">Name</span></span> | <span data-ttu-id="068e1-141">TTL automática</span><span class="sxs-lookup"><span data-stu-id="068e1-141">Automatic TTL</span></span> | <span data-ttu-id="068e1-142">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="068e1-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="068e1-143">TXT</span><span class="sxs-lookup"><span data-stu-id="068e1-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="068e1-144">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-144">30 minutes</span></span>  <br/> |<span data-ttu-id="068e1-145">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="068e1-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="068e1-146">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="068e1-146">**Note:** This is an example.</span></span> <span data-ttu-id="068e1-147">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="068e1-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="068e1-148">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="068e1-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="068e1-149">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="068e1-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="068e1-150">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="068e1-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="068e1-151">Agora que você adicionou o registro no site do registrador de domínios, volte para a Microsoft e procure o registro.</span><span class="sxs-lookup"><span data-stu-id="068e1-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="068e1-152">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="068e1-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="068e1-153">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="068e1-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="068e1-154">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="068e1-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="068e1-155">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="068e1-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="068e1-156">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="068e1-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="068e1-p109">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="068e1-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="068e1-160">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="068e1-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="068e1-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="068e1-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="068e1-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="068e1-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="068e1-163">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="068e1-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="068e1-164">Na **home** page, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="068e1-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="068e1-165">Na página **Visão** geral do seu domínio, selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="068e1-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="068e1-166">Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="068e1-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="068e1-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="068e1-167">Type</span></span> | <span data-ttu-id="068e1-168">Nome</span><span class="sxs-lookup"><span data-stu-id="068e1-168">Name</span></span> | <span data-ttu-id="068e1-169">Servidor de email</span><span class="sxs-lookup"><span data-stu-id="068e1-169">Mail server</span></span> | <span data-ttu-id="068e1-170">Prioridade</span><span class="sxs-lookup"><span data-stu-id="068e1-170">Priority</span></span> | <span data-ttu-id="068e1-171">TTL</span><span class="sxs-lookup"><span data-stu-id="068e1-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="068e1-172">MX</span><span class="sxs-lookup"><span data-stu-id="068e1-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="068e1-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="068e1-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="068e1-174">**Observação:** Obter o  *\<domain-key\>*  seu na sua conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="068e1-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="068e1-175">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="068e1-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="068e1-176">1 </span><span class="sxs-lookup"><span data-stu-id="068e1-176">1</span></span>  <br/> <span data-ttu-id="068e1-177">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="068e1-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="068e1-178">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="068e1-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="068e1-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="068e1-180">Se houver outros registros MX listados na seção **Registros MX,** exclua-os selecionando o ícone **Excluir (X).**</span><span class="sxs-lookup"><span data-stu-id="068e1-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="068e1-181">Na caixa de diálogo de confirmação, selecione **Excluir** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="068e1-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="068e1-182">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="068e1-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="068e1-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="068e1-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="068e1-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="068e1-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="068e1-185">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="068e1-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="068e1-186">Na **home** page, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="068e1-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="068e1-187">Na página **Visão** geral do seu domínio, selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="068e1-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="068e1-188">Adicione o primeiro dos cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="068e1-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="068e1-189">Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="068e1-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="068e1-190">Tipo</span><span class="sxs-lookup"><span data-stu-id="068e1-190">Type</span></span> | <span data-ttu-id="068e1-191">Nome</span><span class="sxs-lookup"><span data-stu-id="068e1-191">Name</span></span> | <span data-ttu-id="068e1-192">Target</span><span class="sxs-lookup"><span data-stu-id="068e1-192">Target</span></span> | <span data-ttu-id="068e1-193">TTL</span><span class="sxs-lookup"><span data-stu-id="068e1-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="068e1-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="068e1-194">CNAME</span></span>  <br/> |<span data-ttu-id="068e1-195">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="068e1-195">autodiscover</span></span>  <br/> |<span data-ttu-id="068e1-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="068e1-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="068e1-197">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="068e1-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="068e1-198">CNAME</span></span>  <br/> |<span data-ttu-id="068e1-199">sip</span><span class="sxs-lookup"><span data-stu-id="068e1-199">sip</span></span>  <br/> |<span data-ttu-id="068e1-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="068e1-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="068e1-201">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="068e1-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="068e1-202">CNAME</span></span>  <br/> |<span data-ttu-id="068e1-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="068e1-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="068e1-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="068e1-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="068e1-205">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="068e1-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="068e1-206">CNAME</span></span>  <br/> |<span data-ttu-id="068e1-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="068e1-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="068e1-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="068e1-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="068e1-209">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="068e1-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="068e1-210">CNAME</span></span>  <br/> |<span data-ttu-id="068e1-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="068e1-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="068e1-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="068e1-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="068e1-213">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="068e1-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="068e1-214">CNAME</span></span>  <br/> |<span data-ttu-id="068e1-215">msoid</span><span class="sxs-lookup"><span data-stu-id="068e1-215">msoid</span></span>  <br/> |<span data-ttu-id="068e1-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="068e1-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="068e1-217">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="068e1-218">Selecione o **ícone de Tráfego DNS** (alterar a nuvem laranja para cinza) para ignorar os servidores Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="068e1-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="068e1-219">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="068e1-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="068e1-220">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="068e1-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="068e1-221">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="068e1-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="068e1-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="068e1-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="068e1-223">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="068e1-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="068e1-224">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="068e1-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="068e1-225">Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="068e1-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="068e1-226">Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="068e1-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="068e1-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="068e1-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="068e1-228">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="068e1-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="068e1-229">Na **home** page, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="068e1-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="068e1-230">Na página **Visão** geral do seu domínio, selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="068e1-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="068e1-231">Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="068e1-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="068e1-232">Tipo</span><span class="sxs-lookup"><span data-stu-id="068e1-232">Type</span></span> | <span data-ttu-id="068e1-233">Nome</span><span class="sxs-lookup"><span data-stu-id="068e1-233">Name</span></span> | <span data-ttu-id="068e1-234">TTL</span><span class="sxs-lookup"><span data-stu-id="068e1-234">TTL</span></span> | <span data-ttu-id="068e1-235">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="068e1-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="068e1-236">TXT</span><span class="sxs-lookup"><span data-stu-id="068e1-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="068e1-237">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-237">30 minutes</span></span>  <br/> |<span data-ttu-id="068e1-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="068e1-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="068e1-239">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="068e1-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="068e1-240">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="068e1-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="068e1-241">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="068e1-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="068e1-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="068e1-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="068e1-243">Lembre-se de que o Cloudflare é responsável por disponibilizar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="068e1-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="068e1-244">Caso você veja discrepâncias entre as etapas abaixo e a GUI cloudflare atual (Interface gráfica do usuário), aproveite a [comunidade Cloudflare.](https://community.cloudflare.com/)</span><span class="sxs-lookup"><span data-stu-id="068e1-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="068e1-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="068e1-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="068e1-246">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="068e1-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="068e1-247">Na **home** page, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="068e1-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="068e1-248">Na página **Visão** geral do seu domínio, selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="068e1-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="068e1-249">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="068e1-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="068e1-250">Na página **de gerenciamento DNS,** clique em **Adicionar registro** e selecione os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="068e1-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="068e1-251">Tipo</span><span class="sxs-lookup"><span data-stu-id="068e1-251">Type</span></span> | <span data-ttu-id="068e1-252">Serviço</span><span class="sxs-lookup"><span data-stu-id="068e1-252">Service</span></span> | <span data-ttu-id="068e1-253">Protocolo</span><span class="sxs-lookup"><span data-stu-id="068e1-253">Protocol</span></span> | <span data-ttu-id="068e1-254">Nome</span><span class="sxs-lookup"><span data-stu-id="068e1-254">Name</span></span> | <span data-ttu-id="068e1-255">TTL</span><span class="sxs-lookup"><span data-stu-id="068e1-255">TTL</span></span> | <span data-ttu-id="068e1-256">Priority</span><span class="sxs-lookup"><span data-stu-id="068e1-256">Priority</span></span> | <span data-ttu-id="068e1-257">Peso</span><span class="sxs-lookup"><span data-stu-id="068e1-257">Weight</span></span> | <span data-ttu-id="068e1-258">Porta</span><span class="sxs-lookup"><span data-stu-id="068e1-258">Port</span></span> | <span data-ttu-id="068e1-259">Target</span><span class="sxs-lookup"><span data-stu-id="068e1-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="068e1-260">SRV</span><span class="sxs-lookup"><span data-stu-id="068e1-260">SRV</span></span>|<span data-ttu-id="068e1-261">_sip</span><span class="sxs-lookup"><span data-stu-id="068e1-261">_sip</span></span> |<span data-ttu-id="068e1-262">TLS</span><span class="sxs-lookup"><span data-stu-id="068e1-262">TLS</span></span> |<span data-ttu-id="068e1-263">Use seu *domain_name*; por exemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="068e1-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="068e1-264">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-264">30 minutes</span></span> | <span data-ttu-id="068e1-265">100</span><span class="sxs-lookup"><span data-stu-id="068e1-265">100</span></span>|<span data-ttu-id="068e1-266">1 </span><span class="sxs-lookup"><span data-stu-id="068e1-266">1</span></span> |<span data-ttu-id="068e1-267">443</span><span class="sxs-lookup"><span data-stu-id="068e1-267">443</span></span> |<span data-ttu-id="068e1-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="068e1-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="068e1-269">SRV</span><span class="sxs-lookup"><span data-stu-id="068e1-269">SRV</span></span>|<span data-ttu-id="068e1-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="068e1-270">_sipfederationtls</span></span> | <span data-ttu-id="068e1-271">TCP</span><span class="sxs-lookup"><span data-stu-id="068e1-271">TCP</span></span>|<span data-ttu-id="068e1-272">Use seu *domain_name*; por exemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="068e1-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="068e1-273">30 minutos</span><span class="sxs-lookup"><span data-stu-id="068e1-273">30 minutes</span></span> |<span data-ttu-id="068e1-274">100</span><span class="sxs-lookup"><span data-stu-id="068e1-274">100</span></span> |<span data-ttu-id="068e1-275">1 </span><span class="sxs-lookup"><span data-stu-id="068e1-275">1</span></span> |<span data-ttu-id="068e1-276">5061</span><span class="sxs-lookup"><span data-stu-id="068e1-276">5061</span></span> | <span data-ttu-id="068e1-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="068e1-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="068e1-278">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="068e1-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="068e1-279">Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="068e1-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="068e1-p117">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="068e1-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
