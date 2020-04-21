---
title: Criar registros DNS para zonas DNS do Azure
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços nas zonas de DNS do Azure para a Microsoft.
ms.openlocfilehash: 7104fb18a6581b7ebc853f938b85171ae1886cfd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629138"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="c6fe2-103">Criar registros DNS para zonas DNS do Azure</span><span class="sxs-lookup"><span data-stu-id="c6fe2-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="c6fe2-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c6fe2-105">Se o Azure for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c6fe2-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="c6fe2-107">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="c6fe2-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="c6fe2-108">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="c6fe2-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="c6fe2-109">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6fe2-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="c6fe2-110">Adicionar os quatro registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6fe2-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="c6fe2-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="c6fe2-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="c6fe2-112">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6fe2-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="c6fe2-113">Depois que você adicionar esses registros no Azure, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6fe2-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c6fe2-117">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="c6fe2-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="c6fe2-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="c6fe2-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6fe2-119">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="c6fe2-120">Ao se inscrever no Azure, você criou um grupo de recursos dentro de uma zona DNS e, em seguida, atribuiu o nome de domínio a esse grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="c6fe2-121">Esse nome de domínio é registrado em um registrador de domínio externo; O Azure não oferece serviços de registro de domínio.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="c6fe2-122">Para verificar e criar registros DNS para o seu domínio na Microsoft, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers do Azure atribuídos ao seu grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="c6fe2-123">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="c6fe2-124">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="c6fe2-125">Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="c6fe2-126">Um exemplo de nameservers atribuídos ao Azure é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="c6fe2-127">**Primeiro nameserver:** Use o valor do servidor de nomes atribuído pelo Azure.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="c6fe2-128">**Segundo nameserver:** Use o valor do servidor de nomes atribuído pelo Azure.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-redelegar-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="c6fe2-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-130">You should use at least two name server records.</span></span> <span data-ttu-id="c6fe2-131">Se houver outros servidores de nomes listados no site do registrador de domínio, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="c6fe2-132">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6fe2-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="c6fe2-134">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c6fe2-135">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="c6fe2-135">Add a TXT record for verification</span></span>
<span data-ttu-id="c6fe2-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c6fe2-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c6fe2-137">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-137">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="c6fe2-138">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-138">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6fe2-p107">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c6fe2-141">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="c6fe2-142">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="c6fe2-144">Usando a **barra de pesquisa** na página do **painel** , digite as **zonas DNS**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="c6fe2-145">Na exibição de resultados, selecione **zonas DNS** na parte de **Serviços** .</span><span class="sxs-lookup"><span data-stu-id="c6fe2-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="c6fe2-146">Depois de Redirecionado, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="c6fe2-148">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="c6fe2-150">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="c6fe2-151">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="c6fe2-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="c6fe2-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-152">**Name**</span></span>|<span data-ttu-id="c6fe2-153">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-153">**Type**</span></span>|<span data-ttu-id="c6fe2-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-154">**TTL**</span></span>|<span data-ttu-id="c6fe2-155">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-155">**TTL unit**</span></span>|<span data-ttu-id="c6fe2-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c6fe2-157">TXT</span><span class="sxs-lookup"><span data-stu-id="c6fe2-157">TXT</span></span>  <br/> |<span data-ttu-id="c6fe2-158">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-158">1</span></span>  <br/> |<span data-ttu-id="c6fe2-159">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-159">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-160">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c6fe2-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c6fe2-161">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-161">**Note:** This is an example.</span></span> <span data-ttu-id="c6fe2-162">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="c6fe2-163">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="c6fe2-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="c6fe2-165">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="c6fe2-166">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c6fe2-167">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c6fe2-168">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c6fe2-169">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c6fe2-170">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c6fe2-171">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c6fe2-172">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="c6fe2-p111">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c6fe2-176">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6fe2-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c6fe2-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c6fe2-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c6fe2-178">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="c6fe2-179">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="c6fe2-181">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="c6fe2-183">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="c6fe2-185">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="c6fe2-186">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="c6fe2-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="c6fe2-187">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-187">**Name**</span></span>|<span data-ttu-id="c6fe2-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-188">**Type**</span></span>|<span data-ttu-id="c6fe2-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-189">**TTL**</span></span>|<span data-ttu-id="c6fe2-190">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-190">**TTL unit**</span></span>|<span data-ttu-id="c6fe2-191">**Preferência**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-191">**Preference**</span></span>|<span data-ttu-id="c6fe2-192">**Troca de emails**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c6fe2-193">MX</span><span class="sxs-lookup"><span data-stu-id="c6fe2-193">MX</span></span>  <br/> |<span data-ttu-id="c6fe2-194">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-194">1</span></span>  <br/> |<span data-ttu-id="c6fe2-195">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-195">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-196">10 </span><span class="sxs-lookup"><span data-stu-id="c6fe2-196">10</span></span>  <br/> <span data-ttu-id="c6fe2-197">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="c6fe2-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="c6fe2-198">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c6fe2-199">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="c6fe2-200">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="c6fe2-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="c6fe2-202">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-202">Select **OK**.</span></span>
    
    ![Azure-BP-configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="c6fe2-204">Se houver outros registros MX listados na seção **registros MX** , você deverá excluí-los.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="c6fe2-205">Primeiro, na área **zona DNS** , selecione o **conjunto de registros MX**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="c6fe2-207">Em seguida, selecione o registro MX que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="c6fe2-209">Selecione o **menu de contexto (...)** e, em seguida, escolha **remover**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="c6fe2-211">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-211">Select **Save**.</span></span>
    
    ![Azure-BP-configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c6fe2-213">Adicionar os quatro registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6fe2-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c6fe2-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c6fe2-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c6fe2-215">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="c6fe2-216">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="c6fe2-218">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="c6fe2-220">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="c6fe2-222">Adicione o primeiro dos quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="c6fe2-223">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, digite ou copie e cole os valores da primeira linha na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c6fe2-224">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="c6fe2-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="c6fe2-225">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-225">**Name**</span></span>|<span data-ttu-id="c6fe2-226">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-226">**Type**</span></span>|<span data-ttu-id="c6fe2-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-227">**TTL**</span></span>|<span data-ttu-id="c6fe2-228">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-228">**TTL unit**</span></span>|<span data-ttu-id="c6fe2-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6fe2-230">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="c6fe2-230">autodiscover</span></span>  <br/> |<span data-ttu-id="c6fe2-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6fe2-231">CNAME</span></span>  <br/> |<span data-ttu-id="c6fe2-232">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-232">1</span></span>  <br/> |<span data-ttu-id="c6fe2-233">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-233">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="c6fe2-235">sip</span><span class="sxs-lookup"><span data-stu-id="c6fe2-235">sip</span></span>  <br/> |<span data-ttu-id="c6fe2-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6fe2-236">CNAME</span></span>  <br/> |<span data-ttu-id="c6fe2-237">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-237">1</span></span>  <br/> |<span data-ttu-id="c6fe2-238">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-238">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c6fe2-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c6fe2-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c6fe2-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6fe2-241">CNAME</span></span>  <br/> |<span data-ttu-id="c6fe2-242">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-242">1</span></span>  <br/> |<span data-ttu-id="c6fe2-243">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-243">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="c6fe2-246">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-246">Select **OK**.</span></span>
    
    ![Azure-BP-configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="c6fe2-248">Adicione cada um dos outros três registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="c6fe2-249">Na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="c6fe2-250">Em seguida, no conjunto de registros vazio, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **OK** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="c6fe2-251">Repita esse processo até ter criado todos os quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="c6fe2-252">Opcion Adicionar dois registros CNAME para MDM.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6fe2-253">Se você tiver o gerenciamento de dispositivo móvel (MDM) para a Microsoft, deverá criar dois registros CNAME adicionais.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="c6fe2-254">Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="c6fe2-255">Se você não tiver o MDM, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="c6fe2-256">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-256">**Name**</span></span>|<span data-ttu-id="c6fe2-257">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-257">**Type**</span></span>|<span data-ttu-id="c6fe2-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-258">**TTL**</span></span>|<span data-ttu-id="c6fe2-259">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-259">**TTL unit**</span></span>|<span data-ttu-id="c6fe2-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c6fe2-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c6fe2-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c6fe2-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6fe2-262">CNAME</span></span>  <br/> |<span data-ttu-id="c6fe2-263">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-263">1</span></span>  <br/> |<span data-ttu-id="c6fe2-264">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-264">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c6fe2-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="c6fe2-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c6fe2-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c6fe2-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6fe2-267">CNAME</span></span>  <br/> |<span data-ttu-id="c6fe2-268">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-268">1</span></span>  <br/> |<span data-ttu-id="c6fe2-269">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-269">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c6fe2-271">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="c6fe2-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c6fe2-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c6fe2-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6fe2-273">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c6fe2-274">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c6fe2-275">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c6fe2-276">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="c6fe2-277">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="c6fe2-278">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="c6fe2-280">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="c6fe2-282">Na área **zona DNS** , selecione o **conjunto de registros txt**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="c6fe2-284">Na área **Propriedades do conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="c6fe2-285">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="c6fe2-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="c6fe2-286">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-286">**Name**</span></span>|<span data-ttu-id="c6fe2-287">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-287">**Type**</span></span>|<span data-ttu-id="c6fe2-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-288">**TTL**</span></span>|<span data-ttu-id="c6fe2-289">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-289">**TTL unit**</span></span>|<span data-ttu-id="c6fe2-290">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c6fe2-291">TXT</span><span class="sxs-lookup"><span data-stu-id="c6fe2-291">TXT</span></span>  <br/> |<span data-ttu-id="c6fe2-292">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-292">1</span></span>  <br/> |<span data-ttu-id="c6fe2-293">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-293">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c6fe2-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c6fe2-295">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="c6fe2-297">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-297">Select **Save**.</span></span>
    
    ![Azure-BP-configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c6fe2-299">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6fe2-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c6fe2-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c6fe2-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c6fe2-301">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="c6fe2-302">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="c6fe2-304">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="c6fe2-306">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="c6fe2-308">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="c6fe2-309">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c6fe2-310">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="c6fe2-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="c6fe2-311">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-311">**Name**</span></span>|<span data-ttu-id="c6fe2-312">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-312">**Type**</span></span>|<span data-ttu-id="c6fe2-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-313">**TTL**</span></span>|<span data-ttu-id="c6fe2-314">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-314">**TTL unit**</span></span>|<span data-ttu-id="c6fe2-315">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-315">**Priority**</span></span>|<span data-ttu-id="c6fe2-316">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-316">**Weight**</span></span>|<span data-ttu-id="c6fe2-317">**Porta**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-317">**Port**</span></span>|<span data-ttu-id="c6fe2-318">**Destino**</span><span class="sxs-lookup"><span data-stu-id="c6fe2-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6fe2-319">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="c6fe2-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="c6fe2-320">SRV</span><span class="sxs-lookup"><span data-stu-id="c6fe2-320">SRV</span></span>  <br/> |<span data-ttu-id="c6fe2-321">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-321">1</span></span>  <br/> |<span data-ttu-id="c6fe2-322">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-322">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-323">100</span><span class="sxs-lookup"><span data-stu-id="c6fe2-323">100</span></span>  <br/> |<span data-ttu-id="c6fe2-324">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-324">1</span></span>  <br/> |<span data-ttu-id="c6fe2-325">443</span><span class="sxs-lookup"><span data-stu-id="c6fe2-325">443</span></span>  <br/> |<span data-ttu-id="c6fe2-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c6fe2-327">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="c6fe2-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="c6fe2-328">SRV</span><span class="sxs-lookup"><span data-stu-id="c6fe2-328">SRV</span></span>  <br/> |<span data-ttu-id="c6fe2-329">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-329">1</span></span>  <br/> |<span data-ttu-id="c6fe2-330">Horas</span><span class="sxs-lookup"><span data-stu-id="c6fe2-330">Hours</span></span>  <br/> |<span data-ttu-id="c6fe2-331">100</span><span class="sxs-lookup"><span data-stu-id="c6fe2-331">100</span></span>  <br/> |<span data-ttu-id="c6fe2-332">1</span><span class="sxs-lookup"><span data-stu-id="c6fe2-332">1</span></span>  <br/> |<span data-ttu-id="c6fe2-333">5061</span><span class="sxs-lookup"><span data-stu-id="c6fe2-333">5061</span></span>  <br/> |<span data-ttu-id="c6fe2-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c6fe2-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="c6fe2-336">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-336">Select **OK**.</span></span>
    
    ![Azure-BP-configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="c6fe2-338">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="c6fe2-339">Nas caixas do novo registro, digite ou copie e cole os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="c6fe2-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6fe2-p120">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c6fe2-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
