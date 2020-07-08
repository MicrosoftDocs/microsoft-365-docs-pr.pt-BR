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
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068098"
---
# <a name="domains-faq"></a><span data-ttu-id="c4237-103">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="c4237-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c4237-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="c4237-104">The admin center is changing.</span></span> <span data-ttu-id="c4237-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c4237-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c4237-106">Este artigo contém respostas para perguntas frequentes sobre domínios no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4237-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="c4237-107">Se você não encontrar uma resposta para a sua pergunta, deixe um comentário, e a adicionaremos à lista.</span><span class="sxs-lookup"><span data-stu-id="c4237-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="c4237-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="c4237-108">In this article</span></span>

- [<span data-ttu-id="c4237-109">O que é prioridade MX?</span><span class="sxs-lookup"><span data-stu-id="c4237-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="c4237-110">Como posso validar registros SPF para meu domínio?</span><span class="sxs-lookup"><span data-stu-id="c4237-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="c4237-111">O que é um nome de domínio?</span><span class="sxs-lookup"><span data-stu-id="c4237-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="c4237-112">O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?</span><span class="sxs-lookup"><span data-stu-id="c4237-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="c4237-113">Como definir ou alterar o domínio padrão no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c4237-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="c4237-114">Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c4237-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="c4237-115">Por que eu tenho um domínio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="c4237-115">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="c4237-116">Por que eu tenho um domínio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="c4237-116">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="c4237-117">Como verifico meu status de educação ou sem fins lucrativos?</span><span class="sxs-lookup"><span data-stu-id="c4237-117">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="c4237-118">O que é prioridade MX?</span><span class="sxs-lookup"><span data-stu-id="c4237-118">What is MX priority?</span></span>

<span data-ttu-id="c4237-119">O email é entregue ao servidor de mensagens com o número de preferência mais baixo (prioridade mais alta), portanto, o registro MX que você usa para o roteamento de emails deve ter o número de preferência mais baixo, normalmente 0 ou *alta* prioridade.</span><span class="sxs-lookup"><span data-stu-id="c4237-119">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="c4237-120">Quando você cria um registro MX, a maioria dos provedores de Hospedagem de DNS exige que você defina o número de preferência.</span><span class="sxs-lookup"><span data-stu-id="c4237-120">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="c4237-121">Um rótulo é a *preferência* de caixa e uma *prioridade* de ti de rótulo.</span><span class="sxs-lookup"><span data-stu-id="c4237-121">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="c4237-122">Alguns exigem um número e alguns pedem que você selecione *baixo* , *médio* ou *alto* .</span><span class="sxs-lookup"><span data-stu-id="c4237-122">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="c4237-123">Se você tiver apenas um registro MX, qualquer valor será adequado para prioridade ou preferência.</span><span class="sxs-lookup"><span data-stu-id="c4237-123">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="c4237-124">Se você tiver mais de um, certifique-se de que o registro MX para roteamento de email seja de prioridade maior do que aquele usado para validar que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="c4237-124">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="c4237-125">Como posso validar registros SPF para meu domínio?</span><span class="sxs-lookup"><span data-stu-id="c4237-125">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="c4237-126">É importante que você tenha ou crie **apenas um registro txt para SPF**.</span><span class="sxs-lookup"><span data-stu-id="c4237-126">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="c4237-127">Se você já tiver um registro SPF, deverá acrescentar os novos valores do Microsoft 365 a ele, em vez de criar um novo.</span><span class="sxs-lookup"><span data-stu-id="c4237-127">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="c4237-128">Após adicionar ou atualizar seu registro SPF para o email da Microsoft, você deve verificar se a sintaxe está correta com uma destas ferramentas:</span><span class="sxs-lookup"><span data-stu-id="c4237-128">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="c4237-129">Ferramentas de teste de registro SPF</span><span class="sxs-lookup"><span data-stu-id="c4237-129">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="c4237-130">Surveyor SPF</span><span class="sxs-lookup"><span data-stu-id="c4237-130">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="c4237-131">Interface Web de busca</span><span class="sxs-lookup"><span data-stu-id="c4237-131">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="c4237-132">O que é um nome de domínio?</span><span class="sxs-lookup"><span data-stu-id="c4237-132">What is a domain name?</span></span>

<span data-ttu-id="c4237-133">O domínio é um nome exclusivo que é exibido após o sinal de **@** nos endereços de email e após **www.**</span><span class="sxs-lookup"><span data-stu-id="c4237-133">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="c4237-134">nos endereços de site.</span><span class="sxs-lookup"><span data-stu-id="c4237-134">in web addresses.</span></span> <span data-ttu-id="c4237-135">Normalmente, ela assume a forma do nome da sua organização e um sufixo da Internet padrão, como *yourbusiness.com* ou *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="c4237-135">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="c4237-136">Usar um domínio personalizado como "**rob \@ contoso.com**" com o Microsoft 365 pode ajudar a criar credibilidade e reconhecimento para a marca.</span><span class="sxs-lookup"><span data-stu-id="c4237-136">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="c4237-137">Você pode [comprar um domínio no Microsoft 365, configurando-o automaticamente](../get-help-with-domains/buy-a-domain-name.md)ou pode comprar ou trazer um que você já possui de um registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="c4237-137">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="c4237-138">O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?</span><span class="sxs-lookup"><span data-stu-id="c4237-138">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="c4237-139">Se você gerenciar seus próprios registros DNS e seu host DNS não oferecer suporte a todos os registros DNS que o Microsoft 365 precisa, alguns recursos do Microsoft 365 não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="c4237-139">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="c4237-140">Recomendamos que você transfira seu domínio para um registrador que dê suporte a todos os registros DNS necessários.</span><span class="sxs-lookup"><span data-stu-id="c4237-140">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="c4237-141">Provedores que oferecem suporte a todos os registros DNS necessários:</span><span class="sxs-lookup"><span data-stu-id="c4237-141">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="c4237-142">Dynadot</span><span class="sxs-lookup"><span data-stu-id="c4237-142">Dynadot</span></span>
    
- <span data-ttu-id="c4237-143">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="c4237-143">eNomCentral</span></span>
    
- <span data-ttu-id="c4237-144">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="c4237-144">Europe Registry</span></span>
    
- <span data-ttu-id="c4237-145">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="c4237-145">GoDaddy</span></span>
    
- <span data-ttu-id="c4237-146">Foco</span><span class="sxs-lookup"><span data-stu-id="c4237-146">Hover</span></span>
    
- <span data-ttu-id="c4237-147">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="c4237-147">MyHosting.com</span></span>
    
- <span data-ttu-id="c4237-148">Name.com</span><span class="sxs-lookup"><span data-stu-id="c4237-148">Name.com</span></span>
    
- <span data-ttu-id="c4237-149">Fala quase livre</span><span class="sxs-lookup"><span data-stu-id="c4237-149">Nearly Free Speech</span></span>
    
- <span data-ttu-id="c4237-150">Nettica</span><span class="sxs-lookup"><span data-stu-id="c4237-150">Nettica</span></span>
    
- <span data-ttu-id="c4237-151">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="c4237-151">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="c4237-152">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="c4237-152">Network Solutions</span></span>
    
- <span data-ttu-id="c4237-153">Register.com</span><span class="sxs-lookup"><span data-stu-id="c4237-153">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="c4237-154">Como definir ou alterar o domínio padrão no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c4237-154">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="c4237-155">Você deve ter pelo menos um domínio personalizado que tenha adicionado ao Microsoft 365 antes de poder escolher um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="c4237-155">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c4237-156">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="c4237-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c4237-157">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="c4237-157">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c4237-158">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="c4237-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c4237-159">Na página **domínios** , selecione o domínio que você deseja definir como o padrão para novos endereços de email.</span><span class="sxs-lookup"><span data-stu-id="c4237-159">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="c4237-160">Selecione **Definir como Padrão**.</span><span class="sxs-lookup"><span data-stu-id="c4237-160">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="c4237-161">Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="c4237-161">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="c4237-162">Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="c4237-162">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="c4237-163">Não é possível alterar o nome do seu domínio inicial *. Partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="c4237-163">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="c4237-164">Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c4237-164">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="c4237-165">Sim.</span><span class="sxs-lookup"><span data-stu-id="c4237-165">Yes.</span></span> <span data-ttu-id="c4237-166">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="c4237-166">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="c4237-167">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="c4237-167">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="c4237-168">Sim!</span><span class="sxs-lookup"><span data-stu-id="c4237-168">Yes!</span></span> <span data-ttu-id="c4237-169">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="c4237-169">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="c4237-170">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="c4237-170">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="c4237-171">Sim!</span><span class="sxs-lookup"><span data-stu-id="c4237-171">Yes!</span></span> <span data-ttu-id="c4237-172">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="c4237-172">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="c4237-173">Se você estiver permitindo que a 21Vianet gerencie suas configurações de DNS com registros NS, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="c4237-173">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="c4237-174">Normalmente, você pode adicionar até 900 domínios à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4237-174">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="c4237-175">Por exemplo, você pode adicionar os domínios contoso.com e contosomarketing.com e, em seguida, adicionar os subdomínios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c4237-175">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="c4237-176">Quando você adiciona um subdomínio, ele é verificado automaticamente com base no domínio pai que está sendo verificado.</span><span class="sxs-lookup"><span data-stu-id="c4237-176">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="c4237-177">Ao adicionar vários domínios ao Microsoft 365, você pode hospedar qualquer um dos serviços (como email) em qualquer um dos domínios que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="c4237-177">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="c4237-178">*Quando você altera seu email para o Microsoft 365, atualizando o registro MX de um domínio, todos os emails enviados para esse domínio serão iniciados no Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="c4237-178">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c4237-179">Se você adicionou um domínio do contoso.com a uma assinatura do Microsoft 365, você também pode adicionar o subdomínio xyz.contoso.com a outra organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4237-179">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="c4237-180">Ao adicionar o subdomínio, você será solicitado a adicionar um registro TXT no provedor de Hospedagem de DNS.</span><span class="sxs-lookup"><span data-stu-id="c4237-180">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="c4237-181">Por que eu tenho um domínio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="c4237-181">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="c4237-182">O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.com*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="c4237-182">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="c4237-183">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="c4237-183">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="c4237-184">**Se você deseja que seu email pareça *Alan \@ contoso.com*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha.</span><span class="sxs-lookup"><span data-stu-id="c4237-184">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="c4237-185">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="c4237-185">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="c4237-186">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.com, não será possível alterá-lo para ser fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="c4237-186">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="c4237-187">Para usar um domínio onmicrosoft.com diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4237-187">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="c4237-188">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="c4237-188">**You can't rename your team site URL.**</span></span> <span data-ttu-id="c4237-189">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="c4237-189">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="c4237-190">Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="c4237-190">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="c4237-191">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="c4237-191">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="c4237-192">O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="c4237-192">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="c4237-193">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="c4237-193">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="c4237-194">Você pode continuar usando o domínio onmicrosoft.com inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c4237-194">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="c4237-195">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="c4237-195">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="c4237-196">Por que eu tenho um domínio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="c4237-196">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="c4237-197">O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.de*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="c4237-197">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="c4237-198">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="c4237-198">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="c4237-199">**Se você quiser que seu email pareça *Alan@contoso.de*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha.</span><span class="sxs-lookup"><span data-stu-id="c4237-199">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="c4237-200">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="c4237-200">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="c4237-201">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.de, não será possível alterá-lo para ser fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="c4237-201">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="c4237-202">Para usar um domínio onmicrosoft.de diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4237-202">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="c4237-203">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="c4237-203">**You can't rename your team site URL.**</span></span> <span data-ttu-id="c4237-204">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.de. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="c4237-204">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="c4237-205">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="c4237-205">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="c4237-206">O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="c4237-206">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="c4237-207">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="c4237-207">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="c4237-208">Você pode continuar usando o domínio onmicrosoft.de inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c4237-208">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="c4237-209">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="c4237-209">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="c4237-210">Como verifico meu status de educação ou sem fins lucrativos?</span><span class="sxs-lookup"><span data-stu-id="c4237-210">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="c4237-211">Selecione **Configurar** no [centro de administração](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="c4237-211">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="c4237-212">(Certifique-se de entrar no Microsoft 365 primeiro).</span><span class="sxs-lookup"><span data-stu-id="c4237-212">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="c4237-213">Para se tornar o administrador da sua escola, selecione a opção **se tornar um administrador** no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4237-213">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="c4237-214">Você será solicitado a adicionar um registro DNS TXT no site de host DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c4237-214">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="c4237-215">Por quê?</span><span class="sxs-lookup"><span data-stu-id="c4237-215">Why?</span></span> <span data-ttu-id="c4237-216">Como entrar no host DNS e adicionar um registro para o seu domínio, você prova para a Microsoft 365 que é o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="c4237-216">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="c4237-217">Depois de adicionar o registro, você voltará para o portal do Microsoft 365 e confirmará que você o adicionou, de modo que a Microsoft 365 possa verificar.</span><span class="sxs-lookup"><span data-stu-id="c4237-217">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="c4237-218">Tem uma entidade sem fins lucrativos e deseja obter o Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c4237-218">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="c4237-219">[Verifique se a sua organização está qualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) e inscreva-se no serviço.</span><span class="sxs-lookup"><span data-stu-id="c4237-219">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="c4237-220">Quer saber mais sobre tornar-se o administrador da sua escola?</span><span class="sxs-lookup"><span data-stu-id="c4237-220">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="c4237-221">[Saiba tudo sobre ele](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="c4237-221">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>