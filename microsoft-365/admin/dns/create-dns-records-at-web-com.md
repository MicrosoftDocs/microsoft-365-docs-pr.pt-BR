---
title: Criar registros DNS no web.com para Microsoft
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em web.com para a Microsoft.
ms.openlocfilehash: a7567688ad9935b30c0749cb7aeffdbe128506ef
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048874"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="d02d2-103">Criar registros DNS no web.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="d02d2-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="d02d2-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d02d2-105">Se o web.com for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d02d2-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d02d2-106">Depois que você adicionar esses registros no web.com, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d02d2-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="d02d2-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d02d2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d02d2-110">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="d02d2-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="d02d2-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="d02d2-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d02d2-112">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="d02d2-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="d02d2-113">Quando você se inscreveu no web.com, adicionou um domínio usando o processo de **instalação** do Web.com.</span><span class="sxs-lookup"><span data-stu-id="d02d2-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="d02d2-114">Para verificar e criar registros DNS para o seu domínio na Microsoft, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers da Web.</span><span class="sxs-lookup"><span data-stu-id="d02d2-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="d02d2-115">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="d02d2-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="d02d2-116">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="d02d2-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="d02d2-117">Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.</span><span class="sxs-lookup"><span data-stu-id="d02d2-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="d02d2-118">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="d02d2-118">First nameserver</span></span>  <br/> |<span data-ttu-id="d02d2-119">Use o valor de nameserver fornecido pelo web.com.</span><span class="sxs-lookup"><span data-stu-id="d02d2-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="d02d2-120">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="d02d2-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="d02d2-121">Use o valor de nameserver fornecido pelo web.com.</span><span class="sxs-lookup"><span data-stu-id="d02d2-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="d02d2-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="d02d2-122">You should use at least two name server records.</span></span> <span data-ttu-id="d02d2-123">Se houver outros servidores de nomes listados, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="d02d2-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="d02d2-124">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="d02d2-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d02d2-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d02d2-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="d02d2-126">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="d02d2-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d02d2-127">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="d02d2-127">Add a TXT record for verification</span></span>
<span data-ttu-id="d02d2-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d02d2-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d02d2-p104">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="d02d2-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d02d2-p105">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="d02d2-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d02d2-133">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="d02d2-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="d02d2-134">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d02d2-134">Log in first.</span></span>
  
2. <span data-ttu-id="d02d2-135">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="d02d2-136">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="d02d2-137">Na página **nomes de domínio** , em **texto (registros txt)**, clique em **editar registros txt**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d02d2-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="d02d2-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="d02d2-138">**Host**</span></span>|<span data-ttu-id="d02d2-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d02d2-139">**TTL**</span></span>|<span data-ttu-id="d02d2-140">**Texto**</span><span class="sxs-lookup"><span data-stu-id="d02d2-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="d02d2-141">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-141">3600</span></span>  <br/> |<span data-ttu-id="d02d2-142">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d02d2-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d02d2-143">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d02d2-143">**Note:** This is an example.</span></span> <span data-ttu-id="d02d2-144">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="d02d2-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d02d2-145">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d02d2-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="d02d2-146">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="d02d2-147">Aguarde alguns minutos antes de verificar o novo registro TXT, para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="d02d2-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d02d2-148">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="d02d2-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d02d2-149">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="d02d2-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d02d2-150">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="d02d2-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d02d2-151">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="d02d2-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d02d2-152">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d02d2-153">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d02d2-p108">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d02d2-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d02d2-157">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d02d2-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d02d2-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d02d2-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d02d2-159">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="d02d2-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="d02d2-160">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d02d2-160">Log in first.</span></span>
  
2. <span data-ttu-id="d02d2-161">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="d02d2-162">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="d02d2-163">Em **servidores de email (registros MX)**, clique em **editar registros MX**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d02d2-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="d02d2-164">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d02d2-164">**Priority**</span></span>|<span data-ttu-id="d02d2-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d02d2-165">**TTL**</span></span>|<span data-ttu-id="d02d2-166">**Servidor de email**</span><span class="sxs-lookup"><span data-stu-id="d02d2-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d02d2-167">1</span><span class="sxs-lookup"><span data-stu-id="d02d2-167">1</span></span>  <br/> <span data-ttu-id="d02d2-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="d02d2-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="d02d2-169">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-169">3600</span></span>  <br/> |<span data-ttu-id="d02d2-170">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d02d2-171">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d02d2-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="d02d2-172">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="d02d2-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="d02d2-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="d02d2-174">Se houver outros registros MX listados na seção **registros MX** , marque a caixa de seleção ao lado do registro em **excluir**e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="d02d2-175">Na tela de confirmação, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d02d2-176">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="d02d2-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d02d2-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d02d2-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d02d2-178">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="d02d2-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="d02d2-179">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d02d2-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="d02d2-180">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="d02d2-181">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="d02d2-182">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d02d2-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="d02d2-183">Em **aliases de host (registros CNAME)**, clique em **editar registros CNAME**e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d02d2-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="d02d2-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d02d2-184">**Alias**</span></span>|<span data-ttu-id="d02d2-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d02d2-185">**TTL**</span></span>|<span data-ttu-id="d02d2-186">**Refere-se ao Nome do host**</span><span class="sxs-lookup"><span data-stu-id="d02d2-186">**Refers to Host Name**</span></span>|<span data-ttu-id="d02d2-187">**Outro host**</span><span class="sxs-lookup"><span data-stu-id="d02d2-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d02d2-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d02d2-188">autodiscover</span></span>  <br/> |<span data-ttu-id="d02d2-189">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-189">3600</span></span>  <br/> |<span data-ttu-id="d02d2-190">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="d02d2-190">@ (none)</span></span>  <br/> |<span data-ttu-id="d02d2-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d02d2-192">sip</span><span class="sxs-lookup"><span data-stu-id="d02d2-192">sip</span></span>  <br/> |<span data-ttu-id="d02d2-193">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-193">3600</span></span>  <br/> |<span data-ttu-id="d02d2-194">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="d02d2-194">@ (none)</span></span>  <br/> |<span data-ttu-id="d02d2-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d02d2-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d02d2-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d02d2-197">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-197">3600</span></span>  <br/> |<span data-ttu-id="d02d2-198">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="d02d2-198">@ (none)</span></span>  <br/> | <span data-ttu-id="d02d2-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d02d2-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d02d2-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d02d2-201">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-201">3600</span></span>  <br/> |<span data-ttu-id="d02d2-202">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="d02d2-202">@ (none)</span></span>  <br/> |<span data-ttu-id="d02d2-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d02d2-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d02d2-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d02d2-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d02d2-205">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-205">3600</span></span>  <br/> |<span data-ttu-id="d02d2-206">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="d02d2-206">@ (none)</span></span>  <br/> |<span data-ttu-id="d02d2-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="d02d2-208">msoid</span><span class="sxs-lookup"><span data-stu-id="d02d2-208">msoid</span></span>  <br/> |<span data-ttu-id="d02d2-209">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-209">3600</span></span>  <br/> |<span data-ttu-id="d02d2-210">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="d02d2-210">@ (none)</span></span>  <br/> |<span data-ttu-id="d02d2-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="d02d2-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="d02d2-212">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="d02d2-213">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="d02d2-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d02d2-214">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="d02d2-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d02d2-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d02d2-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d02d2-216">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="d02d2-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d02d2-217">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="d02d2-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d02d2-218">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d02d2-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d02d2-219">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="d02d2-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="d02d2-220">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="d02d2-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="d02d2-221">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d02d2-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="d02d2-222">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="d02d2-223">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="d02d2-224">Na página **nomes de domínio** , em **texto (registros txt)**, clique em **editar registros txt**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d02d2-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="d02d2-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="d02d2-225">**Host**</span></span>|<span data-ttu-id="d02d2-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d02d2-226">**TTL**</span></span>|<span data-ttu-id="d02d2-227">**Texto**</span><span class="sxs-lookup"><span data-stu-id="d02d2-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d02d2-228">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-228">3600</span></span>  <br/> |<span data-ttu-id="d02d2-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d02d2-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d02d2-230">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="d02d2-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="d02d2-231">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-231">Select **Continue**.</span></span>

6. <span data-ttu-id="d02d2-232">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d02d2-233">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d02d2-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d02d2-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d02d2-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d02d2-235">Tenha em mente que o web.com é responsável por tornar essa funcionalidade disponível.</span><span class="sxs-lookup"><span data-stu-id="d02d2-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="d02d2-236">Caso você veja discrepâncias entre as etapas abaixo e a GUI atual do web.com (interface gráfica do usuário), aproveite a [comunidade do Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="d02d2-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="d02d2-237">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="d02d2-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="d02d2-238">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="d02d2-238">Log in first.</span></span>
      
2. <span data-ttu-id="d02d2-239">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="d02d2-240">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="d02d2-241">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="d02d2-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="d02d2-242">Em **serviço (Registros SRV)**, clique em **Editar Registros SRV**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d02d2-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="d02d2-243">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="d02d2-243">**Service**</span></span>|<span data-ttu-id="d02d2-244">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="d02d2-244">**Protocol**</span></span>|<span data-ttu-id="d02d2-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d02d2-245">**TTL**</span></span>|<span data-ttu-id="d02d2-246">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="d02d2-246">**Priority**</span></span>|<span data-ttu-id="d02d2-247">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="d02d2-247">**Weight**</span></span>|<span data-ttu-id="d02d2-248">**Porta**</span><span class="sxs-lookup"><span data-stu-id="d02d2-248">**Port**</span></span>|<span data-ttu-id="d02d2-249">**Destino**</span><span class="sxs-lookup"><span data-stu-id="d02d2-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d02d2-250">_sip</span><span class="sxs-lookup"><span data-stu-id="d02d2-250">_sip</span></span> |<span data-ttu-id="d02d2-251">_tls</span><span class="sxs-lookup"><span data-stu-id="d02d2-251">_tls</span></span> |<span data-ttu-id="d02d2-252">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-252">3600</span></span> | <span data-ttu-id="d02d2-253">100</span><span class="sxs-lookup"><span data-stu-id="d02d2-253">100</span></span>|<span data-ttu-id="d02d2-254">1</span><span class="sxs-lookup"><span data-stu-id="d02d2-254">1</span></span> |<span data-ttu-id="d02d2-255">443</span><span class="sxs-lookup"><span data-stu-id="d02d2-255">443</span></span> |<span data-ttu-id="d02d2-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="d02d2-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d02d2-257">_sipfederationtls</span></span> |<span data-ttu-id="d02d2-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="d02d2-258">_tcp</span></span> |<span data-ttu-id="d02d2-259">3600</span><span class="sxs-lookup"><span data-stu-id="d02d2-259">3600</span></span> |<span data-ttu-id="d02d2-260">100</span><span class="sxs-lookup"><span data-stu-id="d02d2-260">100</span></span> |<span data-ttu-id="d02d2-261">1</span><span class="sxs-lookup"><span data-stu-id="d02d2-261">1</span></span> |<span data-ttu-id="d02d2-262">5061</span><span class="sxs-lookup"><span data-stu-id="d02d2-262">5061</span></span> | <span data-ttu-id="d02d2-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d02d2-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="d02d2-264">Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="d02d2-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="d02d2-265">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-265">Select **Continue**.</span></span>

7. <span data-ttu-id="d02d2-266">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="d02d2-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="d02d2-p116">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d02d2-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
