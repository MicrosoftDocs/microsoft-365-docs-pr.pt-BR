---
title: Perguntas frequentes sobre domínios
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Saiba mais sobre domínios encontrando respostas para suas perguntas frequentes.
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049731"
---
# <a name="domains-faq"></a><span data-ttu-id="fd330-103">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="fd330-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fd330-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="fd330-104">The admin center is changing.</span></span> <span data-ttu-id="fd330-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fd330-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="fd330-106">Este artigo contém respostas para perguntas frequentes sobre domínios no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd330-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="fd330-107">Se você não encontrar uma resposta para a sua pergunta, deixe um comentário, e a adicionaremos à lista.</span><span class="sxs-lookup"><span data-stu-id="fd330-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="fd330-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="fd330-108">In this article</span></span>

<span data-ttu-id="fd330-109">[O que é prioridade MX?](#what-is-mx-priority) 
 [Como posso validar registros SPF para meu domínio?](#how-can-i-validate-spf-records-for-my-domain) 
 [O que é um nome de domínio?](#what-is-a-domain-name) 
 [O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [Como definir ou alterar o domínio padrão no Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 [Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [Por que eu tenho um domínio "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [Por que eu tenho um domínio "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [Como verifico meu status de educação ou sem fins lucrativos?](#how-do-i-verify-my-nonprofit-or-education-status)</span><span class="sxs-lookup"><span data-stu-id="fd330-109">[What is MX priority?](#what-is-mx-priority)
[How can I validate SPF records for my domain?](#how-can-i-validate-spf-records-for-my-domain)
[What is a domain name?](#what-is-a-domain-name)
[What happens if my DNS provider doesn't support certain record types?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
[How do I set or change the default domain in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
[Can I add custom subdomains or multiple domains to Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
[Why do I have an "onmicrosoft.com" domain?](#why-do-i-have-an-onmicrosoftcom-domain)
[Why do I have an "onmicrosoft.de" domain?](#why-do-i-have-an-onmicrosoftde-domain)
[How do I verify my nonprofit or education status?](#how-do-i-verify-my-nonprofit-or-education-status)</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="fd330-110">O que é prioridade MX?</span><span class="sxs-lookup"><span data-stu-id="fd330-110">What is MX priority?</span></span>

<span data-ttu-id="fd330-111">O email é entregue ao servidor de mensagens com o número de preferência mais baixo (prioridade mais alta), portanto, o registro MX que você usa para o roteamento de emails deve ter o número de preferência mais baixo, normalmente 0 ou *alta* prioridade.</span><span class="sxs-lookup"><span data-stu-id="fd330-111">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="fd330-112">Quando você cria um registro MX, a maioria dos provedores de Hospedagem de DNS exige que você defina o número de preferência.</span><span class="sxs-lookup"><span data-stu-id="fd330-112">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="fd330-113">Um rótulo é a *preferência* de caixa e uma *prioridade* de ti de rótulo.</span><span class="sxs-lookup"><span data-stu-id="fd330-113">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="fd330-114">Alguns exigem um número e alguns pedem que você selecione *baixo* , *médio* ou *alto* .</span><span class="sxs-lookup"><span data-stu-id="fd330-114">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="fd330-115">Se você tiver apenas um registro MX, qualquer valor será adequado para prioridade ou preferência.</span><span class="sxs-lookup"><span data-stu-id="fd330-115">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="fd330-116">Se você tiver mais de um, certifique-se de que o registro MX para roteamento de email seja de prioridade maior do que aquele usado para validar que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="fd330-116">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="fd330-117">Como posso validar registros SPF para meu domínio?</span><span class="sxs-lookup"><span data-stu-id="fd330-117">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="fd330-118">É importante que você tenha ou crie **apenas um registro txt para SPF**.</span><span class="sxs-lookup"><span data-stu-id="fd330-118">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="fd330-119">Se você já tiver um registro SPF, deverá acrescentar os novos valores do Microsoft 365 a ele, em vez de criar um novo.</span><span class="sxs-lookup"><span data-stu-id="fd330-119">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="fd330-120">Após adicionar ou atualizar seu registro SPF para o email da Microsoft, você deve verificar se a sintaxe está correta com uma destas ferramentas:</span><span class="sxs-lookup"><span data-stu-id="fd330-120">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="fd330-121">Ferramentas de teste de registro SPF</span><span class="sxs-lookup"><span data-stu-id="fd330-121">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="fd330-122">Surveyor SPF</span><span class="sxs-lookup"><span data-stu-id="fd330-122">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="fd330-123">Interface Web de busca</span><span class="sxs-lookup"><span data-stu-id="fd330-123">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="fd330-124">O que é um nome de domínio?</span><span class="sxs-lookup"><span data-stu-id="fd330-124">What is a domain name?</span></span>

<span data-ttu-id="fd330-125">O domínio é um nome exclusivo que é exibido após o sinal de **@** nos endereços de email e após **www.**</span><span class="sxs-lookup"><span data-stu-id="fd330-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="fd330-126">nos endereços de site.</span><span class="sxs-lookup"><span data-stu-id="fd330-126">in web addresses.</span></span> <span data-ttu-id="fd330-127">Normalmente, ela assume a forma do nome da sua organização e um sufixo da Internet padrão, como *yourbusiness.com* ou *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="fd330-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="fd330-128">Usar um domínio personalizado como "**rob \@ contoso.com**" com o Microsoft 365 pode ajudar a criar credibilidade e reconhecimento para a marca.</span><span class="sxs-lookup"><span data-stu-id="fd330-128">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="fd330-129">Você pode [comprar um domínio no Microsoft 365, configurando-o automaticamente](../get-help-with-domains/buy-a-domain-name.md)ou pode comprar ou trazer um que você já possui de um registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="fd330-129">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="fd330-130">O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?</span><span class="sxs-lookup"><span data-stu-id="fd330-130">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="fd330-131">Se você gerenciar seus próprios registros DNS e seu host DNS não oferecer suporte a todos os registros DNS que o Microsoft 365 precisa, alguns recursos do Microsoft 365 não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="fd330-131">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="fd330-132">Recomendamos que você transfira seu domínio para um registrador que dê suporte a todos os registros DNS necessários.</span><span class="sxs-lookup"><span data-stu-id="fd330-132">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="fd330-133">Provedores que oferecem suporte a todos os registros DNS necessários:</span><span class="sxs-lookup"><span data-stu-id="fd330-133">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="fd330-134">Dynadot</span><span class="sxs-lookup"><span data-stu-id="fd330-134">Dynadot</span></span>
    
- <span data-ttu-id="fd330-135">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="fd330-135">eNomCentral</span></span>
    
- <span data-ttu-id="fd330-136">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="fd330-136">Europe Registry</span></span>
    
- <span data-ttu-id="fd330-137">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="fd330-137">GoDaddy</span></span>
    
- <span data-ttu-id="fd330-138">Foco</span><span class="sxs-lookup"><span data-stu-id="fd330-138">Hover</span></span>
    
- <span data-ttu-id="fd330-139">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="fd330-139">MyHosting.com</span></span>
    
- <span data-ttu-id="fd330-140">Name.com</span><span class="sxs-lookup"><span data-stu-id="fd330-140">Name.com</span></span>
    
- <span data-ttu-id="fd330-141">Fala quase livre</span><span class="sxs-lookup"><span data-stu-id="fd330-141">Nearly Free Speech</span></span>
    
- <span data-ttu-id="fd330-142">Nettica</span><span class="sxs-lookup"><span data-stu-id="fd330-142">Nettica</span></span>
    
- <span data-ttu-id="fd330-143">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="fd330-143">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="fd330-144">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="fd330-144">Network Solutions</span></span>
    
- <span data-ttu-id="fd330-145">Register.com</span><span class="sxs-lookup"><span data-stu-id="fd330-145">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="fd330-146">Como definir ou alterar o domínio padrão no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fd330-146">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="fd330-147">Você deve ter pelo menos um domínio personalizado que tenha adicionado ao Microsoft 365 antes de poder escolher um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="fd330-147">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fd330-148">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="fd330-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fd330-149">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="fd330-149">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fd330-150">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="fd330-150">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fd330-151">Na página **domínios** , selecione o domínio que você deseja definir como o padrão para novos endereços de email.</span><span class="sxs-lookup"><span data-stu-id="fd330-151">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="fd330-152">Selecione **Definir como Padrão**.</span><span class="sxs-lookup"><span data-stu-id="fd330-152">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="fd330-153">Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="fd330-153">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="fd330-154">Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="fd330-154">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="fd330-155">Não é possível alterar o nome do seu domínio inicial *. Partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="fd330-155">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="fd330-156">Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fd330-156">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="fd330-157">Sim.</span><span class="sxs-lookup"><span data-stu-id="fd330-157">Yes.</span></span> <span data-ttu-id="fd330-158">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="fd330-158">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="fd330-159">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="fd330-159">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="fd330-160">Sim!</span><span class="sxs-lookup"><span data-stu-id="fd330-160">Yes!</span></span> <span data-ttu-id="fd330-161">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="fd330-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="fd330-162">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="fd330-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="fd330-163">Sim!</span><span class="sxs-lookup"><span data-stu-id="fd330-163">Yes!</span></span> <span data-ttu-id="fd330-164">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="fd330-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="fd330-165">Se você estiver permitindo que a 21Vianet gerencie suas configurações de DNS com registros NS, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="fd330-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="fd330-166">Normalmente, você pode adicionar até 900 domínios à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd330-166">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="fd330-167">Por exemplo, você pode adicionar os domínios contoso.com e contosomarketing.com e, em seguida, adicionar os subdomínios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="fd330-167">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="fd330-168">Quando você adiciona um subdomínio, ele é verificado automaticamente com base no domínio pai que está sendo verificado.</span><span class="sxs-lookup"><span data-stu-id="fd330-168">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="fd330-169">Ao adicionar vários domínios ao Microsoft 365, você pode hospedar qualquer um dos serviços (como email) em qualquer um dos domínios que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="fd330-169">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="fd330-170">*Quando você altera seu email para o Microsoft 365, atualizando o registro MX de um domínio, todos os emails enviados para esse domínio serão iniciados no Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="fd330-170">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="fd330-171">Se você adicionou um domínio do contoso.com a uma assinatura do Microsoft 365, você também pode adicionar o subdomínio xyz.contoso.com a outra organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd330-171">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="fd330-172">Ao adicionar o subdomínio, você será solicitado a adicionar um registro TXT no provedor de Hospedagem de DNS.</span><span class="sxs-lookup"><span data-stu-id="fd330-172">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="fd330-173">Por que eu tenho um domínio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="fd330-173">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="fd330-174">O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.com*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="fd330-174">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="fd330-175">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="fd330-175">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="fd330-176">**Se você deseja que seu email pareça *Alan \@ contoso.com*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha.</span><span class="sxs-lookup"><span data-stu-id="fd330-176">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="fd330-177">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="fd330-177">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="fd330-178">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.com, não será possível alterá-lo para ser fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="fd330-178">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="fd330-179">Para usar um domínio onmicrosoft.com diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd330-179">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="fd330-180">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="fd330-180">**You can't rename your team site URL.**</span></span> <span data-ttu-id="fd330-181">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="fd330-181">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="fd330-182">Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="fd330-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="fd330-183">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="fd330-183">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="fd330-184">O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="fd330-184">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="fd330-185">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="fd330-185">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="fd330-186">Você pode continuar usando o domínio onmicrosoft.com inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fd330-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="fd330-187">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="fd330-187">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="fd330-188">Por que eu tenho um domínio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="fd330-188">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="fd330-189">O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.de*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="fd330-189">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="fd330-190">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="fd330-190">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="fd330-191">**Se você quiser que seu email pareça *Alan@contoso.de*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha.</span><span class="sxs-lookup"><span data-stu-id="fd330-191">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="fd330-192">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="fd330-192">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="fd330-193">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.de, não será possível alterá-lo para ser fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="fd330-193">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="fd330-194">Para usar um domínio onmicrosoft.de diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd330-194">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="fd330-195">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="fd330-195">**You can't rename your team site URL.**</span></span> <span data-ttu-id="fd330-196">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.de. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="fd330-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="fd330-197">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="fd330-197">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="fd330-198">O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="fd330-198">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="fd330-199">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="fd330-199">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="fd330-200">Você pode continuar usando o domínio onmicrosoft.de inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fd330-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="fd330-201">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="fd330-201">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="fd330-202">Como verifico meu status de educação ou sem fins lucrativos?</span><span class="sxs-lookup"><span data-stu-id="fd330-202">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="fd330-203">Selecione **Configurar** no [centro de administração](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="fd330-203">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="fd330-204">(Certifique-se de entrar no Microsoft 365 primeiro).</span><span class="sxs-lookup"><span data-stu-id="fd330-204">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="fd330-205">Para se tornar o administrador da sua escola, selecione a opção **se tornar um administrador** no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd330-205">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="fd330-206">Você será solicitado a adicionar um registro DNS TXT no site de host DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="fd330-206">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="fd330-207">Por quê?</span><span class="sxs-lookup"><span data-stu-id="fd330-207">Why?</span></span> <span data-ttu-id="fd330-208">Como entrar no host DNS e adicionar um registro para o seu domínio, você prova para a Microsoft 365 que é o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="fd330-208">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="fd330-209">Depois de adicionar o registro, você voltará para o portal do Microsoft 365 e confirmará que você o adicionou, de modo que a Microsoft 365 possa verificar.</span><span class="sxs-lookup"><span data-stu-id="fd330-209">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="fd330-210">Tem uma entidade sem fins lucrativos e deseja obter o Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fd330-210">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="fd330-211">[Verifique se a sua organização está qualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) e inscreva-se no serviço.</span><span class="sxs-lookup"><span data-stu-id="fd330-211">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="fd330-212">Quer saber mais sobre tornar-se o administrador da sua escola?</span><span class="sxs-lookup"><span data-stu-id="fd330-212">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="fd330-213">[Saiba tudo sobre ele](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="fd330-213">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>