---
title: Criar registros DNS no web.com para o Office 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em web.com para o Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249451"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="8bd83-103">Criar registros DNS no web.com para o Office 365</span><span class="sxs-lookup"><span data-stu-id="8bd83-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="8bd83-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8bd83-105">Se o web.com for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8bd83-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8bd83-106">Depois que você adicionar esses registros no web.com, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bd83-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="8bd83-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="8bd83-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8bd83-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bd83-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8bd83-111">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="8bd83-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="8bd83-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd83-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bd83-113">Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8bd83-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="8bd83-114">Quando você se inscreveu no web.com, adicionou um domínio usando o processo de **instalação** do Web.com.</span><span class="sxs-lookup"><span data-stu-id="8bd83-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="8bd83-115">Para verificar e criar registros DNS para o seu domínio no Office 365, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers da Web.</span><span class="sxs-lookup"><span data-stu-id="8bd83-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="8bd83-116">Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="8bd83-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="8bd83-117">Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8bd83-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="8bd83-118">Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.</span><span class="sxs-lookup"><span data-stu-id="8bd83-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="8bd83-119">Primeiro servidor de nome</span><span class="sxs-lookup"><span data-stu-id="8bd83-119">First nameserver</span></span>  <br/> |<span data-ttu-id="8bd83-120">Use o valor de nameserver fornecido pelo web.com.</span><span class="sxs-lookup"><span data-stu-id="8bd83-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="8bd83-121">Segundo servidor de nome</span><span class="sxs-lookup"><span data-stu-id="8bd83-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="8bd83-122">Use o valor de nameserver fornecido pelo web.com.</span><span class="sxs-lookup"><span data-stu-id="8bd83-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="8bd83-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="8bd83-123">You should use at least two name server records.</span></span> <span data-ttu-id="8bd83-124">Se houver outros servidores de nomes listados, exclua-os.</span><span class="sxs-lookup"><span data-stu-id="8bd83-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="8bd83-125">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="8bd83-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8bd83-p103">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8bd83-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8bd83-128">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="8bd83-128">Add a TXT record for verification</span></span>
<span data-ttu-id="8bd83-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd83-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8bd83-p104">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="8bd83-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bd83-p105">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="8bd83-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8bd83-134">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8bd83-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8bd83-135">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="8bd83-135">Log in first.</span></span>
  
2. <span data-ttu-id="8bd83-136">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8bd83-137">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="8bd83-138">Na página **nomes de domínio** , em **texto (registros txt)**, clique em **editar registros txt**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bd83-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="8bd83-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="8bd83-139">**Host**</span></span>|<span data-ttu-id="8bd83-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd83-140">**TTL**</span></span>|<span data-ttu-id="8bd83-141">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8bd83-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="8bd83-142">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-142">3600</span></span>  <br/> |<span data-ttu-id="8bd83-143">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8bd83-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8bd83-144">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8bd83-144">**Note:** This is an example.</span></span> <span data-ttu-id="8bd83-145">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bd83-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="8bd83-146">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="8bd83-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="8bd83-147">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="8bd83-148">Aguarde alguns minutos antes de verificar o novo registro TXT, para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="8bd83-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8bd83-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="8bd83-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8bd83-150">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="8bd83-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8bd83-151">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="8bd83-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8bd83-152">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="8bd83-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8bd83-153">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8bd83-154">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8bd83-p108">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bd83-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="8bd83-158">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="8bd83-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="8bd83-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd83-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8bd83-160">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8bd83-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8bd83-161">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="8bd83-161">Log in first.</span></span>
  
2. <span data-ttu-id="8bd83-162">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8bd83-163">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="8bd83-164">Em **servidores de email (registros MX)**, clique em **editar registros MX**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bd83-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="8bd83-165">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8bd83-165">**Priority**</span></span>|<span data-ttu-id="8bd83-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd83-166">**TTL**</span></span>|<span data-ttu-id="8bd83-167">**Servidor de email**</span><span class="sxs-lookup"><span data-stu-id="8bd83-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8bd83-168">1</span><span class="sxs-lookup"><span data-stu-id="8bd83-168">1</span></span>  <br/> <span data-ttu-id="8bd83-169">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="8bd83-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="8bd83-170">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-170">3600</span></span>  <br/> |<span data-ttu-id="8bd83-171">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8bd83-172">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bd83-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="8bd83-173">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="8bd83-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="8bd83-174">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="8bd83-175">Se houver outros registros MX listados na seção **registros MX** , marque a caixa de seleção ao lado do registro em **excluir**e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="8bd83-176">Na tela de confirmação, selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="8bd83-177">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="8bd83-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="8bd83-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd83-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8bd83-179">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8bd83-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8bd83-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="8bd83-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="8bd83-181">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8bd83-182">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="8bd83-183">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8bd83-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8bd83-184">Em **aliases de host (registros CNAME)**, clique em **editar registros CNAME**e selecione os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bd83-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="8bd83-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8bd83-185">**Alias**</span></span>|<span data-ttu-id="8bd83-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd83-186">**TTL**</span></span>|<span data-ttu-id="8bd83-187">**Refere-se ao Nome do host**</span><span class="sxs-lookup"><span data-stu-id="8bd83-187">**Refers to Host Name**</span></span>|<span data-ttu-id="8bd83-188">**Outro host**</span><span class="sxs-lookup"><span data-stu-id="8bd83-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8bd83-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8bd83-189">autodiscover</span></span>  <br/> |<span data-ttu-id="8bd83-190">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-190">3600</span></span>  <br/> |<span data-ttu-id="8bd83-191">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="8bd83-191">@ (none)</span></span>  <br/> |<span data-ttu-id="8bd83-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8bd83-193">sip</span><span class="sxs-lookup"><span data-stu-id="8bd83-193">sip</span></span>  <br/> |<span data-ttu-id="8bd83-194">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-194">3600</span></span>  <br/> |<span data-ttu-id="8bd83-195">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="8bd83-195">@ (none)</span></span>  <br/> |<span data-ttu-id="8bd83-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8bd83-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8bd83-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8bd83-198">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-198">3600</span></span>  <br/> |<span data-ttu-id="8bd83-199">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="8bd83-199">@ (none)</span></span>  <br/> | <span data-ttu-id="8bd83-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8bd83-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8bd83-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8bd83-202">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-202">3600</span></span>  <br/> |<span data-ttu-id="8bd83-203">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="8bd83-203">@ (none)</span></span>  <br/> |<span data-ttu-id="8bd83-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8bd83-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8bd83-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8bd83-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8bd83-206">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-206">3600</span></span>  <br/> |<span data-ttu-id="8bd83-207">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="8bd83-207">@ (none)</span></span>  <br/> |<span data-ttu-id="8bd83-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="8bd83-209">msoid</span><span class="sxs-lookup"><span data-stu-id="8bd83-209">msoid</span></span>  <br/> |<span data-ttu-id="8bd83-210">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-210">3600</span></span>  <br/> |<span data-ttu-id="8bd83-211">@ (nenhum)</span><span class="sxs-lookup"><span data-stu-id="8bd83-211">@ (none)</span></span>  <br/> |<span data-ttu-id="8bd83-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="8bd83-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="8bd83-213">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="8bd83-214">Adicione cada um dos outros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="8bd83-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8bd83-215">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="8bd83-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8bd83-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd83-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bd83-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="8bd83-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8bd83-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="8bd83-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8bd83-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bd83-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="8bd83-220">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="8bd83-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="8bd83-221">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8bd83-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8bd83-222">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="8bd83-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="8bd83-223">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8bd83-224">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="8bd83-225">Na página **nomes de domínio** , em **texto (registros txt)**, clique em **editar registros txt**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bd83-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="8bd83-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="8bd83-226">**Host**</span></span>|<span data-ttu-id="8bd83-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd83-227">**TTL**</span></span>|<span data-ttu-id="8bd83-228">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8bd83-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8bd83-229">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-229">3600</span></span>  <br/> |<span data-ttu-id="8bd83-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8bd83-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8bd83-231">**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="8bd83-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="8bd83-232">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-232">Select **Continue**.</span></span>

6. <span data-ttu-id="8bd83-233">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="8bd83-234">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="8bd83-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="8bd83-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd83-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bd83-236">Tenha em mente que o web.com é responsável por tornar essa funcionalidade disponível.</span><span class="sxs-lookup"><span data-stu-id="8bd83-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="8bd83-237">Caso você veja discrepâncias entre as etapas abaixo e a GUI atual do web.com (interface gráfica do usuário), aproveite a [comunidade do Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="8bd83-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="8bd83-238">Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8bd83-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8bd83-239">Faça o logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="8bd83-239">Log in first.</span></span>
      
2. <span data-ttu-id="8bd83-240">Na página **Gerenciador de contas** , selecione **meus nomes de domínio**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8bd83-241">Em \* \* gerenciar \* meu domínio \* \* \*, selecione **editar registros DNS avançados**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="8bd83-242">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="8bd83-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="8bd83-243">Em **serviço (Registros SRV)**, clique em **Editar Registros SRV**e selecione os valores na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bd83-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="8bd83-244">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="8bd83-244">**Service**</span></span>|<span data-ttu-id="8bd83-245">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="8bd83-245">**Protocol**</span></span>|<span data-ttu-id="8bd83-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd83-246">**TTL**</span></span>|<span data-ttu-id="8bd83-247">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8bd83-247">**Priority**</span></span>|<span data-ttu-id="8bd83-248">**Peso**</span><span class="sxs-lookup"><span data-stu-id="8bd83-248">**Weight**</span></span>|<span data-ttu-id="8bd83-249">**Porta**</span><span class="sxs-lookup"><span data-stu-id="8bd83-249">**Port**</span></span>|<span data-ttu-id="8bd83-250">**Destino**</span><span class="sxs-lookup"><span data-stu-id="8bd83-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8bd83-251">_sip</span><span class="sxs-lookup"><span data-stu-id="8bd83-251">_sip</span></span> |<span data-ttu-id="8bd83-252">_tls</span><span class="sxs-lookup"><span data-stu-id="8bd83-252">_tls</span></span> |<span data-ttu-id="8bd83-253">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-253">3600</span></span> | <span data-ttu-id="8bd83-254">100</span><span class="sxs-lookup"><span data-stu-id="8bd83-254">100</span></span>|<span data-ttu-id="8bd83-255">1</span><span class="sxs-lookup"><span data-stu-id="8bd83-255">1</span></span> |<span data-ttu-id="8bd83-256">443</span><span class="sxs-lookup"><span data-stu-id="8bd83-256">443</span></span> |<span data-ttu-id="8bd83-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="8bd83-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8bd83-258">_sipfederationtls</span></span> |<span data-ttu-id="8bd83-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="8bd83-259">_tcp</span></span> |<span data-ttu-id="8bd83-260">3600</span><span class="sxs-lookup"><span data-stu-id="8bd83-260">3600</span></span> |<span data-ttu-id="8bd83-261">100</span><span class="sxs-lookup"><span data-stu-id="8bd83-261">100</span></span> |<span data-ttu-id="8bd83-262">1</span><span class="sxs-lookup"><span data-stu-id="8bd83-262">1</span></span> |<span data-ttu-id="8bd83-263">5061</span><span class="sxs-lookup"><span data-stu-id="8bd83-263">5061</span></span> | <span data-ttu-id="8bd83-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd83-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="8bd83-265">Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="8bd83-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="8bd83-266">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-266">Select **Continue**.</span></span>

7. <span data-ttu-id="8bd83-267">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8bd83-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="8bd83-p116">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bd83-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
