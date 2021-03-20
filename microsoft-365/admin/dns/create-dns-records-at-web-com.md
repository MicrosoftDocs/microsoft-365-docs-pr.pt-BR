---
title: Criar registros DNS no web.com para a Microsoft
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
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços web.com para a Microsoft.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909977"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="75d64-103">Criar registros DNS no web.com para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="75d64-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="75d64-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="75d64-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="75d64-105">Se web.com for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="75d64-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="75d64-106">Depois de adicionar esses registros web.com, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75d64-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="75d64-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="75d64-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="75d64-110">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="75d64-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="75d64-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="75d64-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="75d64-112">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="75d64-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="75d64-113">Quando você se inscreveu no web.com, adicionou um domínio usando o processo web.com **instalação.**</span><span class="sxs-lookup"><span data-stu-id="75d64-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="75d64-114">Para verificar e criar registros DNS para seu domínio na Microsoft, primeiro você precisa alterar os nameservers em seu registrador de domínio para que eles usem os nameservers web.com.</span><span class="sxs-lookup"><span data-stu-id="75d64-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="75d64-115">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="75d64-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="75d64-116">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="75d64-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="75d64-117">Crie dois registros nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles corresponderem a esses valores.</span><span class="sxs-lookup"><span data-stu-id="75d64-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="75d64-118">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="75d64-118">First nameserver</span></span>  <br/> |<span data-ttu-id="75d64-119">Use o valor nameserver fornecido por web.com.</span><span class="sxs-lookup"><span data-stu-id="75d64-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="75d64-120">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="75d64-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="75d64-121">Use o valor nameserver fornecido por web.com.</span><span class="sxs-lookup"><span data-stu-id="75d64-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="75d64-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="75d64-122">You should use at least two name server records.</span></span> <span data-ttu-id="75d64-123">Se houver outros servidores de nomes listados, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="75d64-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="75d64-124">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="75d64-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="75d64-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="75d64-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="75d64-126">Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="75d64-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="75d64-127">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="75d64-127">Add a TXT record for verification</span></span>
<span data-ttu-id="75d64-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="75d64-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="75d64-p104">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="75d64-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="75d64-p105">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="75d64-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="75d64-133">Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="75d64-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="75d64-134">Faça logoff primeiro.</span><span class="sxs-lookup"><span data-stu-id="75d64-134">Log in first.</span></span>
  
2. <span data-ttu-id="75d64-135">Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.**</span><span class="sxs-lookup"><span data-stu-id="75d64-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="75d64-136">Em \*\*Gerenciar \*meu domínio\*\*\*, selecione **Editar Registros DNS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="75d64-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="75d64-137">Na página **Nomes de** Domínio, em **Texto (Registros TXT),** clique em **Editar Registros TXT** e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="75d64-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="75d64-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="75d64-138">**Host**</span></span>|<span data-ttu-id="75d64-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75d64-139">**TTL**</span></span>|<span data-ttu-id="75d64-140">**Texto**</span><span class="sxs-lookup"><span data-stu-id="75d64-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="75d64-141">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-141">3600</span></span>  <br/> |<span data-ttu-id="75d64-142">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="75d64-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="75d64-143">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="75d64-143">**Note:** This is an example.</span></span> <span data-ttu-id="75d64-144">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="75d64-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="75d64-145">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="75d64-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="75d64-146">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="75d64-147">Aguarde alguns minutos antes de verificar seu novo registro TXT, para que o registro que você acabou de criar possa atualizar na Internet.</span><span class="sxs-lookup"><span data-stu-id="75d64-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="75d64-148">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="75d64-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="75d64-149">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="75d64-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="75d64-150">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="75d64-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="75d64-151">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="75d64-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="75d64-152">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="75d64-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="75d64-153">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="75d64-p108">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="75d64-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="75d64-157">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75d64-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="75d64-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="75d64-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="75d64-159">Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="75d64-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="75d64-160">Faça logoff primeiro.</span><span class="sxs-lookup"><span data-stu-id="75d64-160">Log in first.</span></span>
  
2. <span data-ttu-id="75d64-161">Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.**</span><span class="sxs-lookup"><span data-stu-id="75d64-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="75d64-162">Em \*\*Gerenciar \*meu domínio\*\*\*, selecione **Editar Registros DNS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="75d64-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="75d64-163">Em **Servidores de Email (Registros MX),** clique em Editar Registros **MX** e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="75d64-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="75d64-164">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="75d64-164">**Priority**</span></span>|<span data-ttu-id="75d64-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75d64-165">**TTL**</span></span>|<span data-ttu-id="75d64-166">**Servidor de email**</span><span class="sxs-lookup"><span data-stu-id="75d64-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="75d64-167">1</span><span class="sxs-lookup"><span data-stu-id="75d64-167">1</span></span>  <br/> <span data-ttu-id="75d64-168">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="75d64-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="75d64-169">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-169">3600</span></span>  <br/> |<span data-ttu-id="75d64-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="75d64-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="75d64-171">**Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75d64-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="75d64-172">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="75d64-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="75d64-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="75d64-174">Se houver outros registros MX listados na seção **Registros MX,** marque a caixa de seleção ao lado do registro em **Excluir** e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="75d64-175">Na tela de confirmação, selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="75d64-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="75d64-176">Adicionar os seis registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="75d64-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="75d64-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="75d64-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="75d64-178">Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="75d64-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="75d64-179">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="75d64-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="75d64-180">Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.**</span><span class="sxs-lookup"><span data-stu-id="75d64-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="75d64-181">Em \*\*Gerenciar \*meu domínio\*\*\*, selecione **Editar Registros DNS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="75d64-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="75d64-182">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="75d64-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="75d64-183">Em **Aliases de Host (Registros CNAME),** clique em Editar Registros **CNAME** e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="75d64-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="75d64-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="75d64-184">**Alias**</span></span>|<span data-ttu-id="75d64-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75d64-185">**TTL**</span></span>|<span data-ttu-id="75d64-186">**Refere-se ao Nome do host**</span><span class="sxs-lookup"><span data-stu-id="75d64-186">**Refers to Host Name**</span></span>|<span data-ttu-id="75d64-187">**Outro Host**</span><span class="sxs-lookup"><span data-stu-id="75d64-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75d64-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="75d64-188">autodiscover</span></span>  <br/> |<span data-ttu-id="75d64-189">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-189">3600</span></span>  <br/> |<span data-ttu-id="75d64-190">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="75d64-190">@ (none)</span></span>  <br/> |<span data-ttu-id="75d64-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="75d64-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="75d64-192">sip</span><span class="sxs-lookup"><span data-stu-id="75d64-192">sip</span></span>  <br/> |<span data-ttu-id="75d64-193">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-193">3600</span></span>  <br/> |<span data-ttu-id="75d64-194">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="75d64-194">@ (none)</span></span>  <br/> |<span data-ttu-id="75d64-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75d64-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="75d64-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="75d64-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="75d64-197">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-197">3600</span></span>  <br/> |<span data-ttu-id="75d64-198">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="75d64-198">@ (none)</span></span>  <br/> | <span data-ttu-id="75d64-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75d64-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="75d64-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="75d64-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="75d64-201">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-201">3600</span></span>  <br/> |<span data-ttu-id="75d64-202">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="75d64-202">@ (none)</span></span>  <br/> |<span data-ttu-id="75d64-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="75d64-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="75d64-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="75d64-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="75d64-205">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-205">3600</span></span>  <br/> |<span data-ttu-id="75d64-206">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="75d64-206">@ (none)</span></span>  <br/> |<span data-ttu-id="75d64-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="75d64-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="75d64-208">msoid</span><span class="sxs-lookup"><span data-stu-id="75d64-208">msoid</span></span>  <br/> |<span data-ttu-id="75d64-209">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-209">3600</span></span>  <br/> |<span data-ttu-id="75d64-210">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="75d64-210">@ (none)</span></span>  <br/> |<span data-ttu-id="75d64-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="75d64-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="75d64-212">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="75d64-213">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="75d64-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="75d64-214">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="75d64-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="75d64-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="75d64-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="75d64-216">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="75d64-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="75d64-217">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="75d64-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="75d64-218">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75d64-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="75d64-219">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="75d64-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="75d64-220">Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="75d64-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="75d64-221">Faça logoff primeiro.</span><span class="sxs-lookup"><span data-stu-id="75d64-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="75d64-222">Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.**</span><span class="sxs-lookup"><span data-stu-id="75d64-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="75d64-223">Em \*\*Gerenciar \*meu domínio\*\*\*, selecione **Editar Registros DNS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="75d64-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="75d64-224">Na página **Nomes de** Domínio, em **Texto (Registros TXT),** clique em **Editar Registros TXT** e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="75d64-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="75d64-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="75d64-225">**Host**</span></span>|<span data-ttu-id="75d64-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75d64-226">**TTL**</span></span>|<span data-ttu-id="75d64-227">**Texto**</span><span class="sxs-lookup"><span data-stu-id="75d64-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="75d64-228">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-228">3600</span></span>  <br/> |<span data-ttu-id="75d64-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="75d64-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="75d64-230">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="75d64-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="75d64-231">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-231">Select **Continue**.</span></span>

6. <span data-ttu-id="75d64-232">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="75d64-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="75d64-233">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="75d64-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="75d64-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="75d64-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="75d64-235">Lembre-se de que web.com é responsável por disponibilizar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="75d64-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="75d64-236">Caso você veja discrepâncias entre as etapas abaixo e o gui web.com atual(Interface gráfica do usuário), utilize o [web.com Community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="75d64-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="75d64-237">Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="75d64-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="75d64-238">Faça logoff primeiro.</span><span class="sxs-lookup"><span data-stu-id="75d64-238">Log in first.</span></span>
      
2. <span data-ttu-id="75d64-239">Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.**</span><span class="sxs-lookup"><span data-stu-id="75d64-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="75d64-240">Em \*\*Gerenciar \*meu domínio\*\*\*, selecione **Editar Registros DNS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="75d64-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="75d64-241">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="75d64-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="75d64-242">Em **Serviço (Registros SRV),** clique em **Editar Registros SRV** e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="75d64-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="75d64-243">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="75d64-243">**Service**</span></span>|<span data-ttu-id="75d64-244">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="75d64-244">**Protocol**</span></span>|<span data-ttu-id="75d64-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75d64-245">**TTL**</span></span>|<span data-ttu-id="75d64-246">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="75d64-246">**Priority**</span></span>|<span data-ttu-id="75d64-247">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="75d64-247">**Weight**</span></span>|<span data-ttu-id="75d64-248">**Porta**</span><span class="sxs-lookup"><span data-stu-id="75d64-248">**Port**</span></span>|<span data-ttu-id="75d64-249">**Destino**</span><span class="sxs-lookup"><span data-stu-id="75d64-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75d64-250">_sip</span><span class="sxs-lookup"><span data-stu-id="75d64-250">_sip</span></span> |<span data-ttu-id="75d64-251">_tls</span><span class="sxs-lookup"><span data-stu-id="75d64-251">_tls</span></span> |<span data-ttu-id="75d64-252">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-252">3600</span></span> | <span data-ttu-id="75d64-253">100</span><span class="sxs-lookup"><span data-stu-id="75d64-253">100</span></span>|<span data-ttu-id="75d64-254">1</span><span class="sxs-lookup"><span data-stu-id="75d64-254">1</span></span> |<span data-ttu-id="75d64-255">443</span><span class="sxs-lookup"><span data-stu-id="75d64-255">443</span></span> |<span data-ttu-id="75d64-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75d64-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="75d64-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="75d64-257">_sipfederationtls</span></span> |<span data-ttu-id="75d64-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="75d64-258">_tcp</span></span> |<span data-ttu-id="75d64-259">3600</span><span class="sxs-lookup"><span data-stu-id="75d64-259">3600</span></span> |<span data-ttu-id="75d64-260">100</span><span class="sxs-lookup"><span data-stu-id="75d64-260">100</span></span> |<span data-ttu-id="75d64-261">1</span><span class="sxs-lookup"><span data-stu-id="75d64-261">1</span></span> |<span data-ttu-id="75d64-262">5061</span><span class="sxs-lookup"><span data-stu-id="75d64-262">5061</span></span> | <span data-ttu-id="75d64-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75d64-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="75d64-264">Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="75d64-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="75d64-265">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="75d64-265">Select **Continue**.</span></span>

7. <span data-ttu-id="75d64-266">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="75d64-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="75d64-p116">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="75d64-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
