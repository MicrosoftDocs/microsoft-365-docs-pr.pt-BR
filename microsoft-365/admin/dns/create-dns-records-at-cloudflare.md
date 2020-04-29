---
title: Criar registros DNS no cloudflare para Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em cloudflare para a Microsoft.
ms.openlocfilehash: ccd629dfdec24e509144c205b748a883cb65d554
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919622"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="9cee9-103">Criar registros DNS no cloudflare para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cee9-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="9cee9-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9cee9-105">Se o Cloudflare for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="9cee9-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9cee9-106">Depois que você adicionar esses registros no Cloudflare, o domínio será configurado para funcionar com os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9cee9-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="9cee9-107">Para saber mais sobre hospedagem na web e DNS para sites com a Microsoft, confira [Usar um site público com o a Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="9cee9-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9cee9-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9cee9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9cee9-111">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="9cee9-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9cee9-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9cee9-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cee9-113">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="9cee9-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9cee9-114">Quando você se inscreveu no Cloudflare, adicionou um domínio usando o processo de **instalação** do cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9cee9-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="9cee9-115">O domínio adicionado foi comprado de Cloudflare ou de um registrador de domínio separado.</span><span class="sxs-lookup"><span data-stu-id="9cee9-115">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="9cee9-116">Para verificar e criar registros DNS para o seu domínio no Microsoft 365, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers do cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9cee9-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="9cee9-117">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="9cee9-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9cee9-118">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="9cee9-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9cee9-119">Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.</span><span class="sxs-lookup"><span data-stu-id="9cee9-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9cee9-120">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="9cee9-120">First nameserver</span></span>  <br/> |<span data-ttu-id="9cee9-121">Use o valor de nameserver fornecido pelo cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9cee9-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="9cee9-122">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="9cee9-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="9cee9-123">Use o valor de nameserver fornecido pelo cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9cee9-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="9cee9-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="9cee9-124">You should use at least two name server records.</span></span> <span data-ttu-id="9cee9-125">Se houver outros servidores de nomes listados, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="9cee9-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="9cee9-126">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="9cee9-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9cee9-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9cee9-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9cee9-128">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="9cee9-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9cee9-129">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="9cee9-129">Add a TXT record for verification</span></span>
<span data-ttu-id="9cee9-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9cee9-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9cee9-p105">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="9cee9-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cee9-p106">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="9cee9-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9cee9-135">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9cee9-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9cee9-136">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="9cee9-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9cee9-137">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="9cee9-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9cee9-138">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9cee9-139">Na página **Gerenciamento de DNS** , clique em **adicionar registro**e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9cee9-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9cee9-140">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-140">**Type**</span></span>|<span data-ttu-id="9cee9-141">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9cee9-141">**Name**</span></span>|<span data-ttu-id="9cee9-142">**TTL automático**</span><span class="sxs-lookup"><span data-stu-id="9cee9-142">**Automatic TTL**</span></span>|<span data-ttu-id="9cee9-143">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="9cee9-144">TXT</span><span class="sxs-lookup"><span data-stu-id="9cee9-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9cee9-145">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-145">30 minutes</span></span>  <br/> |<span data-ttu-id="9cee9-146">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9cee9-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9cee9-147">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="9cee9-147">**Note:** This is an example.</span></span> <span data-ttu-id="9cee9-148">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="9cee9-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9cee9-149">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="9cee9-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="9cee9-150">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="9cee9-151">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="9cee9-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9cee9-152">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e pesquisará o registro.</span><span class="sxs-lookup"><span data-stu-id="9cee9-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="9cee9-153">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="9cee9-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9cee9-154">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="9cee9-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9cee9-155">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="9cee9-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9cee9-156">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9cee9-157">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9cee9-p109">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9cee9-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9cee9-161">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9cee9-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9cee9-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9cee9-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9cee9-163">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9cee9-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9cee9-164">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="9cee9-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9cee9-165">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="9cee9-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9cee9-166">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9cee9-167">Na página **Gerenciamento de DNS** , clique em **adicionar registro**e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9cee9-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9cee9-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-168">**Type**</span></span>|<span data-ttu-id="9cee9-169">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9cee9-169">**Name**</span></span>|<span data-ttu-id="9cee9-170">**Servidor de email**</span><span class="sxs-lookup"><span data-stu-id="9cee9-170">**Mail server**</span></span>|<span data-ttu-id="9cee9-171">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="9cee9-171">**Priority**</span></span>|<span data-ttu-id="9cee9-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cee9-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cee9-173">MX</span><span class="sxs-lookup"><span data-stu-id="9cee9-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="9cee9-174">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9cee9-175">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9cee9-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="9cee9-176">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="9cee9-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="9cee9-177">1</span><span class="sxs-lookup"><span data-stu-id="9cee9-177">1</span></span>  <br/> <span data-ttu-id="9cee9-178">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cee9-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="9cee9-179">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="9cee9-180">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="9cee9-181">Se houver outros registros MX listados na seção **registros MX** , exclua-os selecionando o ícone **excluir (X)** .</span><span class="sxs-lookup"><span data-stu-id="9cee9-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="9cee9-182">Na caixa de diálogo de confirmação, selecione **excluir** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="9cee9-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9cee9-183">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cee9-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9cee9-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9cee9-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9cee9-185">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9cee9-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9cee9-186">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="9cee9-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9cee9-187">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="9cee9-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9cee9-188">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9cee9-189">Adicione o primeiro dos cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9cee9-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="9cee9-190">Na página **Gerenciamento de DNS** , clique em **adicionar registro**e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9cee9-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="9cee9-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-191">**Type**</span></span>|<span data-ttu-id="9cee9-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9cee9-192">**Name**</span></span>|<span data-ttu-id="9cee9-193">**Destino**</span><span class="sxs-lookup"><span data-stu-id="9cee9-193">**Target**</span></span>|<span data-ttu-id="9cee9-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cee9-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cee9-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cee9-195">CNAME</span></span>  <br/> |<span data-ttu-id="9cee9-196">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="9cee9-196">autodiscover</span></span>  <br/> |<span data-ttu-id="9cee9-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="9cee9-198">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9cee9-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cee9-199">CNAME</span></span>  <br/> |<span data-ttu-id="9cee9-200">sip</span><span class="sxs-lookup"><span data-stu-id="9cee9-200">sip</span></span>  <br/> |<span data-ttu-id="9cee9-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9cee9-202">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9cee9-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cee9-203">CNAME</span></span>  <br/> |<span data-ttu-id="9cee9-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9cee9-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9cee9-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9cee9-206">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9cee9-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cee9-207">CNAME</span></span>  <br/> |<span data-ttu-id="9cee9-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9cee9-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9cee9-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9cee9-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="9cee9-210">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9cee9-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cee9-211">CNAME</span></span>  <br/> |<span data-ttu-id="9cee9-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9cee9-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9cee9-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="9cee9-214">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9cee9-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cee9-215">CNAME</span></span>  <br/> |<span data-ttu-id="9cee9-216">msoid</span><span class="sxs-lookup"><span data-stu-id="9cee9-216">msoid</span></span>  <br/> |<span data-ttu-id="9cee9-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="9cee9-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="9cee9-218">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="9cee9-219">Selecione o ícone de **tráfego DNS** (nuvem laranja) para ignorar os servidores cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9cee9-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="9cee9-220">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="9cee9-221">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9cee9-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9cee9-222">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="9cee9-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9cee9-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9cee9-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cee9-224">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="9cee9-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9cee9-225">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="9cee9-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9cee9-226">Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9cee9-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="9cee9-227">Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="9cee9-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9cee9-228">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9cee9-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9cee9-229">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="9cee9-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9cee9-230">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="9cee9-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9cee9-231">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9cee9-232">Na página **Gerenciamento de DNS** , clique em **adicionar registro**e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9cee9-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="9cee9-233">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-233">**Type**</span></span>|<span data-ttu-id="9cee9-234">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9cee9-234">**Name**</span></span>|<span data-ttu-id="9cee9-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cee9-235">**TTL**</span></span>|<span data-ttu-id="9cee9-236">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cee9-237">TXT</span><span class="sxs-lookup"><span data-stu-id="9cee9-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9cee9-238">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-238">30 minutes</span></span>  <br/> |<span data-ttu-id="9cee9-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9cee9-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9cee9-240">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="9cee9-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="9cee9-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9cee9-242">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cee9-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9cee9-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9cee9-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cee9-244">Tenha em mente que o Cloudflare é responsável por tornar essa funcionalidade disponível.</span><span class="sxs-lookup"><span data-stu-id="9cee9-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="9cee9-245">Caso você veja discrepâncias entre as etapas abaixo e a GUI atual do Cloudflare (interface gráfica do usuário), aproveite a [comunidade do Cloudflare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="9cee9-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="9cee9-246">Para começar, vá até a sua página de domínios no Cloudflare usando [este link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9cee9-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9cee9-247">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="9cee9-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="9cee9-248">Na página **inicial** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="9cee9-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9cee9-249">Na página **visão geral** do seu domínio, selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="9cee9-250">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="9cee9-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="9cee9-251">Na página **Gerenciamento de DNS** , clique em **adicionar registro**e selecione os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9cee9-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="9cee9-252">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-252">**Type**</span></span>|<span data-ttu-id="9cee9-253">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="9cee9-253">**Service**</span></span>|<span data-ttu-id="9cee9-254">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="9cee9-254">**Protocol**</span></span>|<span data-ttu-id="9cee9-255">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9cee9-255">**Name**</span></span>|<span data-ttu-id="9cee9-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cee9-256">**TTL**</span></span>|<span data-ttu-id="9cee9-257">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="9cee9-257">**Priority**</span></span>|<span data-ttu-id="9cee9-258">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="9cee9-258">**Weight**</span></span>|<span data-ttu-id="9cee9-259">**Porta**</span><span class="sxs-lookup"><span data-stu-id="9cee9-259">**Port**</span></span>|<span data-ttu-id="9cee9-260">**Destino**</span><span class="sxs-lookup"><span data-stu-id="9cee9-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cee9-261">SRV</span><span class="sxs-lookup"><span data-stu-id="9cee9-261">SRV</span></span>|<span data-ttu-id="9cee9-262">_sip</span><span class="sxs-lookup"><span data-stu-id="9cee9-262">_sip</span></span> |<span data-ttu-id="9cee9-263">TLS</span><span class="sxs-lookup"><span data-stu-id="9cee9-263">TLS</span></span> |<span data-ttu-id="9cee9-264">Use seu *domain_name*; por exemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="9cee9-265">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-265">30 minutes</span></span> | <span data-ttu-id="9cee9-266">100</span><span class="sxs-lookup"><span data-stu-id="9cee9-266">100</span></span>|<span data-ttu-id="9cee9-267">1</span><span class="sxs-lookup"><span data-stu-id="9cee9-267">1</span></span> |<span data-ttu-id="9cee9-268">443</span><span class="sxs-lookup"><span data-stu-id="9cee9-268">443</span></span> |<span data-ttu-id="9cee9-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="9cee9-270">SRV</span><span class="sxs-lookup"><span data-stu-id="9cee9-270">SRV</span></span>|<span data-ttu-id="9cee9-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9cee9-271">_sipfederationtls</span></span> | <span data-ttu-id="9cee9-272">TCP</span><span class="sxs-lookup"><span data-stu-id="9cee9-272">TCP</span></span>|<span data-ttu-id="9cee9-273">Use seu *domain_name*; por exemplo, contoso.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="9cee9-274">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9cee9-274">30 minutes</span></span> |<span data-ttu-id="9cee9-275">100</span><span class="sxs-lookup"><span data-stu-id="9cee9-275">100</span></span> |<span data-ttu-id="9cee9-276">1</span><span class="sxs-lookup"><span data-stu-id="9cee9-276">1</span></span> |<span data-ttu-id="9cee9-277">5061</span><span class="sxs-lookup"><span data-stu-id="9cee9-277">5061</span></span> | <span data-ttu-id="9cee9-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cee9-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="9cee9-279">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9cee9-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="9cee9-280">Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="9cee9-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="9cee9-p117">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9cee9-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
