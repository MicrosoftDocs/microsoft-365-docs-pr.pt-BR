---
title: Perguntas frequentes sobre domínios
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Saiba mais sobre domínios no Office 365 encontrando respostas para suas perguntas em perguntas frequentes.
ms.custom: okr_smb
ms.openlocfilehash: f3c72f1ce772e3021d79aa4568dbfdb700400803
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251364"
---
# <a name="domains-faq"></a><span data-ttu-id="ed1db-103">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="ed1db-103">Domains FAQ</span></span>

<span data-ttu-id="ed1db-104">Este artigo contém respostas para perguntas frequentes sobre domínios no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="ed1db-105">Se você não encontrar uma resposta para a sua pergunta, deixe um comentário, e a adicionaremos à lista.</span><span class="sxs-lookup"><span data-stu-id="ed1db-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="ed1db-106">O que é prioridade MX?</span><span class="sxs-lookup"><span data-stu-id="ed1db-106">What is MX priority?</span></span>

<span data-ttu-id="ed1db-107">O email é entregue ao servidor de mensagens com o número de preferência mais baixo (prioridade mais alta), portanto, o registro MX que você usa para o roteamento de emails deve ter o número de preferência mais baixo, normalmente 0 ou *alta* prioridade.</span><span class="sxs-lookup"><span data-stu-id="ed1db-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="ed1db-108">Quando você cria um registro MX, a maioria dos provedores de Hospedagem de DNS exige que você defina o número de preferência.</span><span class="sxs-lookup"><span data-stu-id="ed1db-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="ed1db-109">Um rótulo é a *preferência* de caixa e uma *prioridade* de ti de rótulo.</span><span class="sxs-lookup"><span data-stu-id="ed1db-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="ed1db-110">Alguns exigem um número e alguns pedem que você selecione *baixo* , *médio* ou *alto* .</span><span class="sxs-lookup"><span data-stu-id="ed1db-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="ed1db-111">Se você tiver apenas um registro MX, qualquer valor será adequado para prioridade ou preferência.</span><span class="sxs-lookup"><span data-stu-id="ed1db-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="ed1db-112">Se você tiver mais de um, certifique-se de que o registro MX para roteamento de email seja de prioridade maior do que aquele usado para validar que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="ed1db-113">Como posso validar registros SPF para meu domínio?</span><span class="sxs-lookup"><span data-stu-id="ed1db-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="ed1db-114">É importante que você tenha ou crie **apenas um registro txt para SPF**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-114">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="ed1db-115">Se você já tiver um registro SPF, deverá acrescentar os novos valores do Office 365 a ele, em vez de criar um novo.</span><span class="sxs-lookup"><span data-stu-id="ed1db-115">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="ed1db-116">Após adicionar ou atualizar seu registro SPF para email do Office 365, você deve verificar se a sintaxe está correta com uma destas ferramentas:</span><span class="sxs-lookup"><span data-stu-id="ed1db-116">After you've added or updated your SPF record for Office 365 email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="ed1db-117">Ferramentas de teste de registro SPF</span><span class="sxs-lookup"><span data-stu-id="ed1db-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="ed1db-118">Surveyor SPF</span><span class="sxs-lookup"><span data-stu-id="ed1db-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="ed1db-119">Interface Web de busca</span><span class="sxs-lookup"><span data-stu-id="ed1db-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="ed1db-120">Como o Office 365 gerencia meus registros de DNS?</span><span class="sxs-lookup"><span data-stu-id="ed1db-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="ed1db-121">Há duas opções para o gerenciamento de DNS com o Office 365:</span><span class="sxs-lookup"><span data-stu-id="ed1db-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="ed1db-122">Você alterar os registros de nameserver (NS) e o Office 365 cuida de todos os registros específicos de serviço, como configurar seu registro MX para email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-122">You change your nameserver (NS) records, and then Office 365 takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="ed1db-123">**Recomenda**</span><span class="sxs-lookup"><span data-stu-id="ed1db-123">**(Recommended)**</span></span>
    
2. <span data-ttu-id="ed1db-124">Você mesmo adiciona registros DNS para email e outros serviços do Office 365 no seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-124">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="ed1db-125">**(Apenas especialistas)**</span><span class="sxs-lookup"><span data-stu-id="ed1db-125">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="ed1db-126">O Office 365 cria e hospeda os registros DNS</span><span class="sxs-lookup"><span data-stu-id="ed1db-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="ed1db-127">**Vantagens**</span><span class="sxs-lookup"><span data-stu-id="ed1db-127">**Advantages**</span></span> 
- <span data-ttu-id="ed1db-128">Você não precisa se preocupar em cometer erros nos valores inseridos para os registros DNS dos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="ed1db-129">Você tem mais flexibilidade em sua escolha de registradores de domínio e host DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="ed1db-130">Qualquer provedor que permita alterar os registros de nameserver funcionará, mesmo se o provedor não oferecer suporte a todos os tipos de registros necessários.</span><span class="sxs-lookup"><span data-stu-id="ed1db-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="ed1db-131">Quando o Office 365 adiciona novos registros DNS, não é necessário fazer atualizações.</span><span class="sxs-lookup"><span data-stu-id="ed1db-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="ed1db-132">Desvantagens</span><span class="sxs-lookup"><span data-stu-id="ed1db-132">Disadvantages</span></span> 
- <span data-ttu-id="ed1db-133">Não é possível alterar seus registros DNS para hospedar email fora do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="ed1db-134">Se você já usa um site público com seu domínio para seu endereço, como o www.fourthcoffee.com, você deve redirecionar as pessoas para esse endereço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="ed1db-135">Configurar o redirecionamento requer um endereço IP estático, que nem sempre é facilmente disponível para sites públicos.</span><span class="sxs-lookup"><span data-stu-id="ed1db-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="ed1db-136">– Se seu registrador de domínio atual não permitir que você altere os registros de nameserver do seu domínio, você terá que alternar para um registrador diferente para usar essa opção de gerenciamento de DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="ed1db-137">Você mesmo gerencia os registros DNS</span><span class="sxs-lookup"><span data-stu-id="ed1db-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="ed1db-138">Vantagens</span><span class="sxs-lookup"><span data-stu-id="ed1db-138">Advantages</span></span>
- <span data-ttu-id="ed1db-139">Você controla os registros DNS dos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="ed1db-140">Se você tiver um site público com seu domínio para seu endereço, como o www.fourthcoffee.com, não precisará se preocupar em usar o redirecionamento para garantir que as pessoas ainda possam acessar seu site depois de configurar seu domínio no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="ed1db-141">Você tem a flexibilidade de hospedar emails em outro lugar, como com um servidor Exchange local.</span><span class="sxs-lookup"><span data-stu-id="ed1db-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="ed1db-142">Desvantagens</span><span class="sxs-lookup"><span data-stu-id="ed1db-142">Disadvantages</span></span>
<span data-ttu-id="ed1db-143">Você precisa configurar os registros DNS para os serviços do Office 365 por conta própria (a menos que tenha um domínio GoDaddy).</span><span class="sxs-lookup"><span data-stu-id="ed1db-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="ed1db-144">Se o seu host DNS atual não oferecer suporte a todos os tipos de registros necessários para o Office 365, alguns recursos do Office 365 não estarão disponíveis e talvez seja necessário alternar para um host DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="ed1db-144">If your current DNS host doesn't support all of the required record types for Office 365, some Office 365 features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="ed1db-145">Quando o Office 365 altera os requisitos para registros DNS ou adiciona novos serviços, você precisa fazer as atualizações em seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="ed1db-146">O que é um nome de domínio?</span><span class="sxs-lookup"><span data-stu-id="ed1db-146">What is a domain name?</span></span>


<span data-ttu-id="ed1db-147">O domínio é um nome exclusivo que é exibido após o sinal de **@** nos endereços de email e após **www.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-147">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="ed1db-148">nos endereços de site.</span><span class="sxs-lookup"><span data-stu-id="ed1db-148">in web addresses.</span></span> <span data-ttu-id="ed1db-149">Normalmente, ela assume a forma do nome da sua organização e um sufixo da Internet padrão, como *yourbusiness.com* ou *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="ed1db-149">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="ed1db-150">Usar um domínio personalizado como "**rob\@contoso.com**" com o Office 365 pode ajudar a criar credibilidade e reconhecimento para a marca.</span><span class="sxs-lookup"><span data-stu-id="ed1db-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="ed1db-151">Você pode [comprar um domínio no Office 365 e o configuraremos automaticamente](../get-help-with-domains/buy-a-domain-name.md), ou você pode comprar ou trazer um que você já possui de um registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="ed1db-152">É possível transferir um domínio que comprei da Microsoft para outro provedor?</span><span class="sxs-lookup"><span data-stu-id="ed1db-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="ed1db-153">Sim, mas não é possível transferir um domínio do Office 365 para outro registrador até 60 dias após você comprá-lo com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="ed1db-154">Observe que uma consulta *whois* mostrará um registrador de domínios comprados do Office 365 como domínios com o selvagem LLC.</span><span class="sxs-lookup"><span data-stu-id="ed1db-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="ed1db-155">No entanto, somente o Office 365 deve ser contatado em relação ao seu domínio do Office 365 comprado.</span><span class="sxs-lookup"><span data-stu-id="ed1db-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="ed1db-156">Siga as etapas abaixo para obter o código no Office 365 e, em seguida, vá para o site do outro registrador de domínio para configurar a transferência do seu nome de domínio para esse registrador.</span><span class="sxs-lookup"><span data-stu-id="ed1db-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>
  
1. <span data-ttu-id="ed1db-157">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="ed1db-158">Se você estiver usando o Office 365 Alemanha, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-158">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="ed1db-159">Se você estiver usando o Office 365 operado pela 21Vianet, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-159">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ed1db-160">Na página **domínios** , selecione o domínio do Office 365 que você deseja transferir para outro registrador de domínio e, em seguida, selecione **transferência** > de domínio**habilitar transferência**de domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="ed1db-161">Siga as etapas para se preparar para transferir seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="ed1db-162">Depois de obter o código, vá para o site do registrador de domínio no qual você deseja gerenciar o nome de domínio em frente e siga as instruções para transferir um domínio (pesquise ajuda no site).</span><span class="sxs-lookup"><span data-stu-id="ed1db-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="ed1db-163">Se você precisar ver o código novamente, na página **configurações de domínio** no Office 365, selecione **Exibir código de autorização para transferência de domínio**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="ed1db-164">Após a conclusão da transferência, você renovará seu domínio no novo registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="ed1db-165">Para concluir o processo, volte para a página **domínios** do centro de administração e selecione **completa transferência de domínio**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="ed1db-166">*Observação: Observe que os domínios comprados do Office 365 não estão qualificados para alterações no servidor de nomes ou transferência do domínio entre os locatários do Office 365.  Se uma dessas opções for obrigatória, o registro de domínio precisará ser transferido para outro registrador.*</span><span class="sxs-lookup"><span data-stu-id="ed1db-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="ed1db-167">Como alterar a forma como os registros DNS são gerenciados no Office 365?</span><span class="sxs-lookup"><span data-stu-id="ed1db-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="ed1db-168">Alterar o gerenciamento de DNS para um host DNS fora do Office 365</span><span class="sxs-lookup"><span data-stu-id="ed1db-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="ed1db-169">Entre no registrador de domínio do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="ed1db-170">Encontre a área no site do registrador onde você atualiza os registros Nameservers e atualize os nameservers para apontar para o host DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-170">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="ed1db-171">(Geralmente, o host DNS é o registrador de domínio).</span><span class="sxs-lookup"><span data-stu-id="ed1db-171">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="ed1db-172">Siga um link para acessar o assistente de configuração de domínios:</span><span class="sxs-lookup"><span data-stu-id="ed1db-172">Follow a link to go to the domains setup wizard:</span></span>
    
4. <span data-ttu-id="ed1db-173">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="ed1db-174">Se você estiver usando o Office 365 Alemanha, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-174">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="ed1db-175">Se você estiver usando o Office 365 operado pela 21Vianet, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-175">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
5. <span data-ttu-id="ed1db-176">Na página **domínios** , selecione o domínio que você está alternando e selecione **Gerenciamento de DNS**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="ed1db-177">No assistente de configuração de domínios, na página **configurar seus serviços online** , selecione **gerenciar meus próprios registros DNS**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="ed1db-178">Adicionar os registros DNS sugeridos pelo assistente na página **Atualizar configurações de DNS** para o site do registrador.</span><span class="sxs-lookup"><span data-stu-id="ed1db-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="ed1db-179">Depois de adicionar os registros, volte para o Office 365 e selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="ed1db-180">Alterar o gerenciamento de DNS para o Office 365</span><span class="sxs-lookup"><span data-stu-id="ed1db-180">Change DNS management to Office 365</span></span>
  
1. <span data-ttu-id="ed1db-181">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="ed1db-182">Se você estiver usando o Office 365 Alemanha, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-182">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="ed1db-183">Se você estiver usando o Office 365 operado pela 21Vianet, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-183">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ed1db-184">Na página **domínios** , selecione o domínio que você está alternando e selecione **Gerenciamento de DNS**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="ed1db-185">No assistente de configuração de domínios, na página **configurar seus serviços online** , selecione **Configurar meus serviços online para mim. (Recomendado)** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="ed1db-186">Se você ainda não verificou o domínio, siga as etapas para fazer isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="ed1db-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="ed1db-187">Na página **Atualizar configurações de DNS** , listamos os nameservers para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-187">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="ed1db-188">Vá para o registrador de domínio do seu domínio e atualize os nameservers para os nameservers do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-188">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="ed1db-189">Depois de atualizar os nameservers, **aguarde pelo menos uma hora**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="ed1db-190">Em seguida, novamente no assistente do Office 365, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="ed1db-191">O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?</span><span class="sxs-lookup"><span data-stu-id="ed1db-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="ed1db-192">Se você gerenciar seus próprios registros DNS e seu host DNS não oferecer suporte a todos os registros DNS que o Office 365 precisa, alguns recursos do Office 365 não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="ed1db-192">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="ed1db-193">Recomendamos que você transfira seu domínio para um registrador que dê suporte a todos os registros DNS necessários.</span><span class="sxs-lookup"><span data-stu-id="ed1db-193">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="ed1db-194">Provedores que oferecem suporte a todos os registros DNS necessários:</span><span class="sxs-lookup"><span data-stu-id="ed1db-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="ed1db-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="ed1db-195">Dynadot</span></span>
    
- <span data-ttu-id="ed1db-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="ed1db-196">eNomCentral</span></span>
    
- <span data-ttu-id="ed1db-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="ed1db-197">Europe Registry</span></span>
    
- <span data-ttu-id="ed1db-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="ed1db-198">GoDaddy</span></span>
    
- <span data-ttu-id="ed1db-199">Foco</span><span class="sxs-lookup"><span data-stu-id="ed1db-199">Hover</span></span>
    
- <span data-ttu-id="ed1db-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="ed1db-200">MyHosting.com</span></span>
    
- <span data-ttu-id="ed1db-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="ed1db-201">Name.com</span></span>
    
- <span data-ttu-id="ed1db-202">Fala quase livre</span><span class="sxs-lookup"><span data-stu-id="ed1db-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="ed1db-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="ed1db-203">Nettica</span></span>
    
- <span data-ttu-id="ed1db-204">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="ed1db-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="ed1db-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="ed1db-205">Network Solutions</span></span>
    
- <span data-ttu-id="ed1db-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="ed1db-206">Register.com</span></span>
    
 <span data-ttu-id="ed1db-207">**Se não houver suporte para registros SRV**, os seguintes recursos do Office 365 não estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ed1db-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="ed1db-208">Integração de IM e presença do Skype for Business online com o Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="ed1db-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="ed1db-209">Comunicação externa (Federação) com usuários do Skype for Business online em outras organizações.</span><span class="sxs-lookup"><span data-stu-id="ed1db-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="ed1db-210">Public Internet Connectivity (PIC) com usuários do Skype for Business online conectados com uma conta da Microsoft (conhecida anteriormente como Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="ed1db-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="ed1db-211">**Se não houver suporte para vários registros CNAME,** você terá que escolher entre os seguintes recursos para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="ed1db-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="ed1db-212">Os clientes de área de trabalho de email e clientes móveis podem usar a descoberta automática para localizar automaticamente o serviço do Exchange Online, de modo que os usuários possam entrar sem precisar inserir um nome de servidor.</span><span class="sxs-lookup"><span data-stu-id="ed1db-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="ed1db-213">Os clientes de área de trabalho do Skype for Business Online podem usar a descoberta automática para localizar automaticamente o serviço Skype for Business Online, de modo que os usuários possam entrar sem precisar inserir um nome de servidor.</span><span class="sxs-lookup"><span data-stu-id="ed1db-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="ed1db-214">Os clientes móveis do Skype for Business Online podem usar a descoberta automática para localizar automaticamente o serviço Skype for Business Online, de modo que os usuários possam entrar sem precisar inserir um nome de servidor.</span><span class="sxs-lookup"><span data-stu-id="ed1db-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="ed1db-215">**Se não houver suporte para registros SPF/txt**, outras pessoas poderão usar seu domínio para enviar spam ou outros emails mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="ed1db-215">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="ed1db-216">Os registros SPF funcionam identificando os servidores que estão autorizados a enviar emails do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-216">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="ed1db-217">Como faço para definir ou alterar o domínio padrão no Office 365?</span><span class="sxs-lookup"><span data-stu-id="ed1db-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="ed1db-218">Você deve ter pelo menos um domínio personalizado que tenha adicionado ao Office 365 antes de poder escolher um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="ed1db-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>
  
1. <span data-ttu-id="ed1db-219">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="ed1db-220">Se você estiver usando o Office 365 Alemanha, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-220">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="ed1db-221">Se você estiver usando o Office 365 operado pela 21Vianet, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-221">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ed1db-222">Na página **domínios** , selecione o domínio que você deseja definir como o padrão para novos endereços de email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="ed1db-223">Selecione **definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="ed1db-224">Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="ed1db-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="ed1db-225">Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="ed1db-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="ed1db-226">Não é possível alterar o nome do seu domínio inicial *. Partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="ed1db-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="ed1db-227">Posso adicionar subdomínios personalizados ou vários domínios ao Office 365?</span><span class="sxs-lookup"><span data-stu-id="ed1db-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="ed1db-228">Sim!</span><span class="sxs-lookup"><span data-stu-id="ed1db-228">Yes!</span></span> <span data-ttu-id="ed1db-229">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="ed1db-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="ed1db-230">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="ed1db-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="ed1db-231">Sim!</span><span class="sxs-lookup"><span data-stu-id="ed1db-231">Yes!</span></span> <span data-ttu-id="ed1db-232">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="ed1db-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="ed1db-233">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="ed1db-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="ed1db-234">Sim!</span><span class="sxs-lookup"><span data-stu-id="ed1db-234">Yes!</span></span> <span data-ttu-id="ed1db-235">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="ed1db-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="ed1db-236">Se você estiver permitindo que a 21Vianet gerencie suas configurações de DNS com registros NS, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="ed1db-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="ed1db-237">Normalmente, você pode adicionar até 900 domínios à sua assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="ed1db-238">Por exemplo, você pode adicionar os domínios contoso.com e contosomarketing.com e, em seguida, adicionar os subdomínios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ed1db-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="ed1db-239">Quando você adiciona um subdomínio, ele é verificado automaticamente com base no domínio pai que está sendo verificado.</span><span class="sxs-lookup"><span data-stu-id="ed1db-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="ed1db-240">Ao adicionar vários domínios ao Office 365, você pode hospedar qualquer um dos serviços (como email) em qualquer um dos domínios que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="ed1db-240">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="ed1db-241">*Quando você altera seu email para o Office 365, atualizando o registro MX de um domínio, todos os emails enviados para esse domínio serão iniciados no Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ed1db-241">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ed1db-242">Se você já tiver adicionado um domínio do contoso.com a um locatário do Office 365, você também pode adicionar o subdomínio xyz.contoso.com a outro locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="ed1db-243">Ao adicionar o subdomínio, você será solicitado a adicionar um registro TXT no provedor de Hospedagem de DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="ed1db-244">Por que eu tenho um domínio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="ed1db-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="ed1db-245">O Office 365 cria um domínio para você, como o *contoso.onmicrosoft.com*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="ed1db-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="ed1db-246">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="ed1db-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="ed1db-247">**Se você deseja que seu email pareça *\@Alan contoso.com*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Office 365,](add-domain.md) se você já o possui.</span><span class="sxs-lookup"><span data-stu-id="ed1db-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="ed1db-248">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-248">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="ed1db-249">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.com, não será possível alterá-lo para ser fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ed1db-249">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="ed1db-250">Para usar um domínio onmicrosoft.com diferente, você terá que iniciar uma nova assinatura com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-250">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="ed1db-251">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="ed1db-252">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ed1db-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="ed1db-253">Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="ed1db-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="ed1db-254">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-254">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="ed1db-255">O Office 365 precisa mantê-lo por conta própria, pois é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="ed1db-255">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="ed1db-256">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed1db-256">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="ed1db-257">Você pode continuar usando o domínio onmicrosoft.com inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-257">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="ed1db-258">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="ed1db-258">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="ed1db-259">Por que eu tenho um domínio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="ed1db-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="ed1db-260">O Office 365 cria um domínio para você, como o *contoso.onmicrosoft.de*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="ed1db-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="ed1db-261">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="ed1db-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="ed1db-262">**Se você deseja que seu email pareça *Alan@contoso.de*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Office 365](add-domain.md) , se você já o possui.</span><span class="sxs-lookup"><span data-stu-id="ed1db-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="ed1db-263">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="ed1db-264">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.de, não será possível alterá-lo para ser fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="ed1db-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="ed1db-265">Para usar um domínio onmicrosoft.de diferente, você terá que iniciar uma nova assinatura com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="ed1db-266">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="ed1db-267">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.de. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="ed1db-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="ed1db-268">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="ed1db-268">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="ed1db-269">O Office 365 precisa mantê-lo por conta própria, pois é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="ed1db-269">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="ed1db-270">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed1db-270">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="ed1db-271">Você pode continuar usando o domínio onmicrosoft.de inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="ed1db-272">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="ed1db-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="ed1db-273">Como verifico meu status de educação ou sem fins lucrativos?</span><span class="sxs-lookup"><span data-stu-id="ed1db-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="ed1db-274">Selecione **Configurar** no [centro de administração](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="ed1db-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="ed1db-275">(Certifique-se de entrar no Office 365 primeiro.)</span><span class="sxs-lookup"><span data-stu-id="ed1db-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="ed1db-276">Para se tornar o administrador da sua escola, selecione a opção **se tornar um administrador** no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="ed1db-277">Você será solicitado a adicionar um registro DNS TXT no site de host DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="ed1db-278">Por quê?</span><span class="sxs-lookup"><span data-stu-id="ed1db-278">Why?</span></span> <span data-ttu-id="ed1db-279">Como entrar no host DNS e adicionar um registro para seu domínio, você prova ao Office 365 que é o proprietário do nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="ed1db-280">Depois de adicionar o registro, você voltará para o portal do Office 365 e confirmará que você o adicionou, para que o Office 365 possa verificar.</span><span class="sxs-lookup"><span data-stu-id="ed1db-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="ed1db-281">Tem uma entidade sem fins lucrativos e deseja obter o Office 365?</span><span class="sxs-lookup"><span data-stu-id="ed1db-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="ed1db-282">[Verifique se a sua organização está qualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) e inscreva-se no serviço.</span><span class="sxs-lookup"><span data-stu-id="ed1db-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="ed1db-283">Quer saber mais sobre tornar-se o administrador da sua escola?</span><span class="sxs-lookup"><span data-stu-id="ed1db-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="ed1db-284">[Saiba tudo sobre ele](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="ed1db-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="ed1db-285">Posso fazer um piloto do Office 365 com apenas alguns endereços de email do meu domínio personalizado?</span><span class="sxs-lookup"><span data-stu-id="ed1db-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="ed1db-286">Você pode, mas há limitações:</span><span class="sxs-lookup"><span data-stu-id="ed1db-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="ed1db-287">Seu provedor de email atual deve fornecer encaminhamento de email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="ed1db-288">Você precisa gerenciar seus registros DNS relacionados ao Office 365 em seu provedor de hospedagem DNS, em vez de ter o Office 365 gerenciá-los para você.</span><span class="sxs-lookup"><span data-stu-id="ed1db-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="ed1db-289">Para saber o que isso envolve, confira adicionar seu domínio ao Office 365 quando quiser gerenciar seus próprios registros DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="ed1db-290">Alguns recursos do Office 365 não estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ed1db-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="ed1db-291">Os usuários não conseguirão ver as informações de disponibilidade dos usuários que estão no outro provedor de email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="ed1db-292">Os administradores não conseguirão administrar as contas de todos os usuários de um só lugar.</span><span class="sxs-lookup"><span data-stu-id="ed1db-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="ed1db-293">Os usuários podem não conseguir usar o filtro de spam do Office 365</span><span class="sxs-lookup"><span data-stu-id="ed1db-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="ed1db-294">Como configurar um piloto do Office 365</span><span class="sxs-lookup"><span data-stu-id="ed1db-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="ed1db-295">Entre no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed1db-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="ed1db-296">Entre no Office 365 com uma conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="ed1db-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="ed1db-297">Vá para \*\*\*\* \> **domínios**de configurações.</span><span class="sxs-lookup"><span data-stu-id="ed1db-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="ed1db-298">Verifique se você é o proprietário do domínio que deseja usar</span><span class="sxs-lookup"><span data-stu-id="ed1db-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="ed1db-299">Na página **domínios** , selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="ed1db-300">No painel, digite o domínio, neste exemplo, cohowinery.com, e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="ed1db-301">Na página **verificar** domínio, siga as instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="ed1db-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="ed1db-302">Na lista suspensa, selecione seu provedor de Hospedagem de DNS e siga as instruções para mostrar que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ed1db-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="ed1db-303">Selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-303">Select **Verify**.</span></span> <span data-ttu-id="ed1db-304">Leva alguns minutos e 72 horas para que as alterações de DNS entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="ed1db-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="ed1db-305">Quando a verificação for bem-sucedida, você será solicitado a modificar seus registros DNS.</span><span class="sxs-lookup"><span data-stu-id="ed1db-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="ed1db-306">Marcar o domínio como compartilhado no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ed1db-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="ed1db-307">Vá para o **centro de administração do Exchange** (Eat).</span><span class="sxs-lookup"><span data-stu-id="ed1db-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="ed1db-308">Na seção **fluxo de emails** , selecione **domínios aceitos**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="ed1db-309">Clique duas vezes no domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="ed1db-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="ed1db-310">Na janela que é aberta, selecione **retransmissão interna**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="ed1db-311">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-311">Select **Save**.</span></span> <span data-ttu-id="ed1db-312">Essa configuração pode exigir alguns minutos para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="ed1db-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="ed1db-313">Opcionalmente, desbloqueie o servidor de email existente</span><span class="sxs-lookup"><span data-stu-id="ed1db-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="ed1db-314">O Office 365 usa o proteção do Exchange Online (EOP) para proteção contra spam.</span><span class="sxs-lookup"><span data-stu-id="ed1db-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="ed1db-315">Se o EOP detectar um alto volume de spam sendo encaminhado pelo servidor de email atual, ele poderá bloqueá-lo, o que impediria o encaminhamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed1db-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="ed1db-316">Se você estiver confiante com a proteção contra spam que seu outro provedor de email usa, poderá listar seus servidores no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="ed1db-317">No entanto, isso também permitirá que qualquer spam que chega ao servidor original seja enviado às caixas de correio do Office 365, e você não poderá avaliar como o Office 365 impede spam.</span><span class="sxs-lookup"><span data-stu-id="ed1db-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="ed1db-318">Vá para o centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="ed1db-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="ed1db-319">No Eat, selecione **proteção**e selecione filtro de **conexão**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="ed1db-320">Na **lista de permissões de IP**, **+** selecione e adicione o endereço IP do servidor de email que você pode obter de seu provedor de email atual.</span><span class="sxs-lookup"><span data-stu-id="ed1db-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="ed1db-321">Criar contas de usuário e definir o endereço principal (responder a)</span><span class="sxs-lookup"><span data-stu-id="ed1db-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="ed1db-322">Vá para o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="ed1db-323">Na barra de navegação esquerda, selecione usuários **ativos**do **usuário** \> .</span><span class="sxs-lookup"><span data-stu-id="ed1db-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="ed1db-324">Crie as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="ed1db-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="ed1db-325">Para cada conta, selecione **+ (novo)** e preencha as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="ed1db-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="ed1db-326">Para manter o mesmo email do usuário, o campo **nome de usuário** deve ser exatamente o mesmo que o endereço de email existente do usuário.</span><span class="sxs-lookup"><span data-stu-id="ed1db-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="ed1db-327">Ao lado de nome de usuário, selecione seu nome de domínio personalizado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ed1db-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="ed1db-328">Selecione **criar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ed1db-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="ed1db-329">Atualizar registros DNS no seu provedor de Hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="ed1db-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="ed1db-330">Entre no site do provedor de Hospedagem de DNS e siga as [etapas de criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ed1db-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="ed1db-331">**Faça as seguintes exceções:**</span><span class="sxs-lookup"><span data-stu-id="ed1db-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="ed1db-332">Não crie um novo registro MX ou altere seu registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="ed1db-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="ed1db-333">Se você já tiver um registro SPF (Sender Policy Framework) para seu provedor de emails anterior, em vez de criar um novo registro SPF (TXT) para o Exchange Online, basta adicionar "include include. Protection. Outlook. com" ao registro TXT atual.</span><span class="sxs-lookup"><span data-stu-id="ed1db-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="ed1db-334">Por exemplo, "v = spf1 mx inclui:adatum. com include include. Protection. Outlook. com ~ All".</span><span class="sxs-lookup"><span data-stu-id="ed1db-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="ed1db-335">Se você ainda não tem um registro SPF, modifique o que é recomendado pelo Office 365 para incluir o domínio para seu provedor de email atual, mais spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ed1db-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="ed1db-336">Isso autoriza mensagens de saída de ambos os sistemas de email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="ed1db-337">Configurar o encaminhamento de emails no provedor atual</span><span class="sxs-lookup"><span data-stu-id="ed1db-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="ed1db-338">No seu provedor de email atual, configure o encaminhamento de contas de email dos usuários para seu domínio do onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="ed1db-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="ed1db-339">A caixa de correio do usuário A deve encaminhar para usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed1db-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="ed1db-340">A caixa de correio do usuário B deve encaminhar para userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed1db-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="ed1db-341">Ao concluir esta etapa:</span><span class="sxs-lookup"><span data-stu-id="ed1db-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="ed1db-342">Todos os emails enviados para usera@yourcompany.com e userb@yourcompany.com estarão disponíveis no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="ed1db-343">Observações:</span><span class="sxs-lookup"><span data-stu-id="ed1db-343">Notes:</span></span>
        
        - <span data-ttu-id="ed1db-344">Entre em contato com seu provedor de email atual para obter as etapas exatas para configurar o encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="ed1db-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="ed1db-345">Você não precisa manter uma cópia das mensagens no provedor de emails atual.</span><span class="sxs-lookup"><span data-stu-id="ed1db-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="ed1db-346">A maioria dos provedores encaminham o endereço para resposta do remetente intacto, para que as respostas vá para o remetente original.</span><span class="sxs-lookup"><span data-stu-id="ed1db-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="ed1db-347">Testar o fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="ed1db-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="ed1db-348">Entre no Outlook Web App usando as credenciais do usuário A.</span><span class="sxs-lookup"><span data-stu-id="ed1db-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="ed1db-349">Execute os seguintes testes:</span><span class="sxs-lookup"><span data-stu-id="ed1db-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="ed1db-350">Teste email local do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed1db-350">Test local Office 365 email.</span></span> <span data-ttu-id="ed1db-351">Por exemplo, envie um email para o usuário B. Esse email deve ser entregue imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ed1db-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="ed1db-352">Neste cenário, a mensagem não será encaminhada para a caixa de correio do usuário B no seu servidor original porque o Office 365 vê a caixa de correio como local.</span><span class="sxs-lookup"><span data-stu-id="ed1db-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="ed1db-353">Teste o email para alguém que está no outro sistema de email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="ed1db-354">Por exemplo, envie um email para o usuário C. Este email deve ser entregue na caixa de correio do usuário C no seu servidor de email original.</span><span class="sxs-lookup"><span data-stu-id="ed1db-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="ed1db-355">A partir de uma conta externa ou da conta de email de um funcionário no outro sistema de email, verifique se o encaminhamento foi configurado corretamente no outro sistema de email.</span><span class="sxs-lookup"><span data-stu-id="ed1db-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="ed1db-356">Por exemplo, da conta de servidor origninal do usuário C ou de uma conta do hotmail, envie um email para o usuário e verifique se ele chega à caixa de correio do Office 365 do usuário A.</span><span class="sxs-lookup"><span data-stu-id="ed1db-356">For example, from User C's origninal server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="ed1db-357">Mover conteúdo da caixa de correio</span><span class="sxs-lookup"><span data-stu-id="ed1db-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="ed1db-358">Como há apenas dois usuários a serem movidos, e como o usuário A e o usuário B já estão usando o Outlook, o email pode ser movido abrindo o antigo. PST no novo perfil do Outlook e copiar as mensagens, itens de calendário, contatos, etc., conforme mostrado em importar itens do Outlook de um arquivo de dados do Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="ed1db-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="ed1db-359">Depois de organizado nos locais apropriados da caixa de correio do Office 365, todos os itens podem ser acessados de qualquer dispositivo, em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="ed1db-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="ed1db-360">Quando mais caixas de correio estiverem envolvidas ou se os funcionários ainda não estiverem usando o Outlook, você poderá usar as ferramentas de migração disponíveis no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ed1db-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="ed1db-361">Para começar, vá para o centro de administração do Exchange e siga as instruções em migrar email de um servidor IMAP para caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ed1db-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
