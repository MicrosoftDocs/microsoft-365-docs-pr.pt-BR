---
title: Criar registros DNS para zonas DNS do Azure
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços nas zonas de DNS do Azure para o Office 365.
ms.openlocfilehash: 3758b525bd98c724165f2671023ba416c338786d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236960"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="f8cff-103">Criar registros DNS para zonas DNS do Azure</span><span class="sxs-lookup"><span data-stu-id="f8cff-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="f8cff-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f8cff-105">Se o Azure for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f8cff-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f8cff-106">Esses são os principais registros a adicionar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="f8cff-107">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="f8cff-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="f8cff-108">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="f8cff-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="f8cff-109">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cff-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="f8cff-110">Adicionar os quatro registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cff-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="f8cff-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="f8cff-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="f8cff-112">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cff-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="f8cff-113">Depois que você adicionar esses registros no Azure, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8cff-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8cff-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f8cff-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f8cff-117">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="f8cff-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f8cff-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cff-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8cff-119">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f8cff-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f8cff-120">Ao se inscrever no Azure, você criou um grupo de recursos dentro de uma zona DNS e, em seguida, atribuiu o nome de domínio a esse grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="f8cff-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="f8cff-121">Esse nome de domínio é registrado em um registrador de domínio externo; O Azure não oferece serviços de registro de domínio.</span><span class="sxs-lookup"><span data-stu-id="f8cff-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="f8cff-122">Para verificar e criar registros DNS para o seu domínio no Office 365, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers do Azure atribuídos ao grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="f8cff-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="f8cff-123">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="f8cff-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f8cff-124">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f8cff-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f8cff-125">Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.</span><span class="sxs-lookup"><span data-stu-id="f8cff-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="f8cff-126">Um exemplo de nameservers atribuídos ao Azure é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="f8cff-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="f8cff-127">**Primeiro nameserver:** Use o valor do servidor de nomes atribuído pelo Azure.</span><span class="sxs-lookup"><span data-stu-id="f8cff-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="f8cff-128">**Segundo nameserver:** Use o valor do servidor de nomes atribuído pelo Azure.</span><span class="sxs-lookup"><span data-stu-id="f8cff-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-redelegar-1-1](../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="f8cff-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="f8cff-130">You should use at least two name server records.</span></span> <span data-ttu-id="f8cff-131">Se houver outros servidores de nomes listados no site do registrador de domínio, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="f8cff-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="f8cff-132">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="f8cff-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f8cff-p105">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f8cff-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f8cff-135">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="f8cff-135">Add a TXT record for verification</span></span>
<span data-ttu-id="f8cff-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cff-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f8cff-p106">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="f8cff-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8cff-p107">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f8cff-141">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="f8cff-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f8cff-142">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f8cff-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f8cff-144">Usando a **barra de pesquisa** na página do **painel** , digite as **zonas DNS**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="f8cff-145">Na exibição de resultados, selecione **zonas DNS** na parte de **Serviços** .</span><span class="sxs-lookup"><span data-stu-id="f8cff-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="f8cff-146">Depois de Redirecionado, selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-configure-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f8cff-148">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f8cff-150">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f8cff-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="f8cff-151">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="f8cff-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f8cff-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f8cff-152">**Name**</span></span>|<span data-ttu-id="f8cff-153">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8cff-153">**Type**</span></span>|<span data-ttu-id="f8cff-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-154">**TTL**</span></span>|<span data-ttu-id="f8cff-155">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-155">**TTL unit**</span></span>|<span data-ttu-id="f8cff-156">**Valor**</span><span class="sxs-lookup"><span data-stu-id="f8cff-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f8cff-157">TXT</span><span class="sxs-lookup"><span data-stu-id="f8cff-157">TXT</span></span>  <br/> |<span data-ttu-id="f8cff-158">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-158">1</span></span>  <br/> |<span data-ttu-id="f8cff-159">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-159">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-160">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f8cff-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f8cff-161">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="f8cff-161">**Note:** This is an example.</span></span> <span data-ttu-id="f8cff-162">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8cff-162">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="f8cff-163">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="f8cff-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="f8cff-165">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="f8cff-166">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="f8cff-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f8cff-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="f8cff-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f8cff-168">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="f8cff-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f8cff-169">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="f8cff-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f8cff-170">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="f8cff-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f8cff-171">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f8cff-172">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f8cff-p111">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f8cff-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f8cff-176">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cff-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f8cff-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cff-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f8cff-178">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="f8cff-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f8cff-179">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f8cff-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f8cff-181">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f8cff-183">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f8cff-185">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f8cff-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="f8cff-186">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="f8cff-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f8cff-187">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f8cff-187">**Name**</span></span>|<span data-ttu-id="f8cff-188">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8cff-188">**Type**</span></span>|<span data-ttu-id="f8cff-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-189">**TTL**</span></span>|<span data-ttu-id="f8cff-190">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-190">**TTL unit**</span></span>|<span data-ttu-id="f8cff-191">**Preferência**</span><span class="sxs-lookup"><span data-stu-id="f8cff-191">**Preference**</span></span>|<span data-ttu-id="f8cff-192">**Troca de emails**</span><span class="sxs-lookup"><span data-stu-id="f8cff-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f8cff-193">MX</span><span class="sxs-lookup"><span data-stu-id="f8cff-193">MX</span></span>  <br/> |<span data-ttu-id="f8cff-194">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-194">1</span></span>  <br/> |<span data-ttu-id="f8cff-195">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-195">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-196">10 </span><span class="sxs-lookup"><span data-stu-id="f8cff-196">10</span></span>  <br/> <span data-ttu-id="f8cff-197">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="f8cff-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="f8cff-198">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f8cff-199">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8cff-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="f8cff-200">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="f8cff-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="f8cff-202">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-202">Select **OK**.</span></span>
    
    ![Azure-BP-configure-2-2](../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="f8cff-204">Se houver outros registros MX listados na seção **registros MX** , você deverá excluí-los.</span><span class="sxs-lookup"><span data-stu-id="f8cff-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="f8cff-205">Primeiro, na área **zona DNS** , selecione o **conjunto de registros MX**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-configure-2-3](../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="f8cff-207">Em seguida, selecione o registro MX que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="f8cff-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-configure-2-4](../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="f8cff-209">Selecione o **menu de contexto (...)** e, em seguida, escolha **remover**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-configure-2-5](../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="f8cff-211">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-211">Select **Save**.</span></span>
    
    ![Azure-BP-configure-2-6](../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f8cff-213">Adicionar os quatro registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cff-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f8cff-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cff-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f8cff-215">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="f8cff-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f8cff-216">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f8cff-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f8cff-218">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f8cff-220">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f8cff-222">Adicione o primeiro dos quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="f8cff-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="f8cff-223">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, digite ou copie e cole os valores da primeira linha na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f8cff-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f8cff-224">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="f8cff-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f8cff-225">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f8cff-225">**Name**</span></span>|<span data-ttu-id="f8cff-226">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8cff-226">**Type**</span></span>|<span data-ttu-id="f8cff-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-227">**TTL**</span></span>|<span data-ttu-id="f8cff-228">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-228">**TTL unit**</span></span>|<span data-ttu-id="f8cff-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f8cff-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f8cff-230">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="f8cff-230">autodiscover</span></span>  <br/> |<span data-ttu-id="f8cff-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="f8cff-231">CNAME</span></span>  <br/> |<span data-ttu-id="f8cff-232">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-232">1</span></span>  <br/> |<span data-ttu-id="f8cff-233">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-233">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f8cff-235">sip</span><span class="sxs-lookup"><span data-stu-id="f8cff-235">sip</span></span>  <br/> |<span data-ttu-id="f8cff-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="f8cff-236">CNAME</span></span>  <br/> |<span data-ttu-id="f8cff-237">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-237">1</span></span>  <br/> |<span data-ttu-id="f8cff-238">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-238">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f8cff-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f8cff-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f8cff-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="f8cff-241">CNAME</span></span>  <br/> |<span data-ttu-id="f8cff-242">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-242">1</span></span>  <br/> |<span data-ttu-id="f8cff-243">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-243">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-configure-3-1](../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="f8cff-246">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-246">Select **OK**.</span></span>
    
    ![Azure-BP-configure-3-2](../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="f8cff-248">Adicione cada um dos outros três registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="f8cff-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="f8cff-249">Na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="f8cff-250">Em seguida, no conjunto de registros vazio, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **OK** para concluir esse registro.</span><span class="sxs-lookup"><span data-stu-id="f8cff-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="f8cff-251">Repita esse processo até ter criado todos os quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="f8cff-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="f8cff-252">Opcion Adicionar dois registros CNAME para MDM.</span><span class="sxs-lookup"><span data-stu-id="f8cff-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8cff-253">Se você tiver o gerenciamento de dispositivo móvel (MDM) para o Office 365, deverá criar dois registros CNAME adicionais.</span><span class="sxs-lookup"><span data-stu-id="f8cff-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="f8cff-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f8cff-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="f8cff-255">Se você não tiver o MDM, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f8cff-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="f8cff-256">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f8cff-256">**Name**</span></span>|<span data-ttu-id="f8cff-257">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8cff-257">**Type**</span></span>|<span data-ttu-id="f8cff-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-258">**TTL**</span></span>|<span data-ttu-id="f8cff-259">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-259">**TTL unit**</span></span>|<span data-ttu-id="f8cff-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f8cff-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8cff-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f8cff-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f8cff-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="f8cff-262">CNAME</span></span>  <br/> |<span data-ttu-id="f8cff-263">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-263">1</span></span>  <br/> |<span data-ttu-id="f8cff-264">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-264">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f8cff-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="f8cff-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f8cff-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f8cff-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="f8cff-267">CNAME</span></span>  <br/> |<span data-ttu-id="f8cff-268">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-268">1</span></span>  <br/> |<span data-ttu-id="f8cff-269">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-269">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f8cff-271">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="f8cff-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f8cff-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cff-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8cff-273">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="f8cff-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f8cff-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="f8cff-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f8cff-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8cff-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f8cff-276">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="f8cff-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f8cff-277">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="f8cff-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f8cff-278">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f8cff-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f8cff-280">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f8cff-282">Na área **zona DNS** , selecione o **conjunto de registros txt**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-configure-4-1](../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="f8cff-284">Na área **Propriedades do conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f8cff-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="f8cff-285">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="f8cff-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f8cff-286">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f8cff-286">**Name**</span></span>|<span data-ttu-id="f8cff-287">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8cff-287">**Type**</span></span>|<span data-ttu-id="f8cff-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-288">**TTL**</span></span>|<span data-ttu-id="f8cff-289">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-289">**TTL unit**</span></span>|<span data-ttu-id="f8cff-290">**Valor**</span><span class="sxs-lookup"><span data-stu-id="f8cff-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f8cff-291">TXT</span><span class="sxs-lookup"><span data-stu-id="f8cff-291">TXT</span></span>  <br/> |<span data-ttu-id="f8cff-292">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-292">1</span></span>  <br/> |<span data-ttu-id="f8cff-293">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-293">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f8cff-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f8cff-295">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="f8cff-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-configure-4-2](../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="f8cff-297">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-297">Select **Save**.</span></span>
    
    ![Azure-BP-configure-4-3](../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f8cff-299">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f8cff-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f8cff-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f8cff-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f8cff-301">Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="f8cff-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f8cff-302">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f8cff-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f8cff-304">Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="f8cff-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f8cff-306">Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f8cff-308">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="f8cff-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="f8cff-309">Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f8cff-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f8cff-310">(Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.)</span><span class="sxs-lookup"><span data-stu-id="f8cff-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f8cff-311">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f8cff-311">**Name**</span></span>|<span data-ttu-id="f8cff-312">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8cff-312">**Type**</span></span>|<span data-ttu-id="f8cff-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-313">**TTL**</span></span>|<span data-ttu-id="f8cff-314">**Unidade TTL**</span><span class="sxs-lookup"><span data-stu-id="f8cff-314">**TTL unit**</span></span>|<span data-ttu-id="f8cff-315">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="f8cff-315">**Priority**</span></span>|<span data-ttu-id="f8cff-316">**Peso**</span><span class="sxs-lookup"><span data-stu-id="f8cff-316">**Weight**</span></span>|<span data-ttu-id="f8cff-317">**Porta**</span><span class="sxs-lookup"><span data-stu-id="f8cff-317">**Port**</span></span>|<span data-ttu-id="f8cff-318">**Destino**</span><span class="sxs-lookup"><span data-stu-id="f8cff-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f8cff-319">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="f8cff-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="f8cff-320">SRV</span><span class="sxs-lookup"><span data-stu-id="f8cff-320">SRV</span></span>  <br/> |<span data-ttu-id="f8cff-321">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-321">1</span></span>  <br/> |<span data-ttu-id="f8cff-322">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-322">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-323">100</span><span class="sxs-lookup"><span data-stu-id="f8cff-323">100</span></span>  <br/> |<span data-ttu-id="f8cff-324">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-324">1</span></span>  <br/> |<span data-ttu-id="f8cff-325">443</span><span class="sxs-lookup"><span data-stu-id="f8cff-325">443</span></span>  <br/> |<span data-ttu-id="f8cff-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f8cff-327">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="f8cff-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="f8cff-328">SRV</span><span class="sxs-lookup"><span data-stu-id="f8cff-328">SRV</span></span>  <br/> |<span data-ttu-id="f8cff-329">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-329">1</span></span>  <br/> |<span data-ttu-id="f8cff-330">Horas</span><span class="sxs-lookup"><span data-stu-id="f8cff-330">Hours</span></span>  <br/> |<span data-ttu-id="f8cff-331">100</span><span class="sxs-lookup"><span data-stu-id="f8cff-331">100</span></span>  <br/> |<span data-ttu-id="f8cff-332">1</span><span class="sxs-lookup"><span data-stu-id="f8cff-332">1</span></span>  <br/> |<span data-ttu-id="f8cff-333">5061</span><span class="sxs-lookup"><span data-stu-id="f8cff-333">5061</span></span>  <br/> |<span data-ttu-id="f8cff-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8cff-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-configure-5-1](../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="f8cff-336">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8cff-336">Select **OK**.</span></span>
    
    ![Azure-BP-configure-5-2](../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="f8cff-338">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="f8cff-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="f8cff-339">Nas caixas do novo registro, digite ou copie e cole os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="f8cff-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f8cff-p120">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f8cff-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
