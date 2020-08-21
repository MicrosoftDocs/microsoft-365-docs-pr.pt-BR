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
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845839"
---
# <a name="domains-faq"></a><span data-ttu-id="b3728-103">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="b3728-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b3728-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="b3728-104">The admin center is changing.</span></span> <span data-ttu-id="b3728-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b3728-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b3728-106">Este artigo contém respostas para perguntas frequentes sobre domínios no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3728-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="b3728-107">Se você não encontrar uma resposta para a sua pergunta, deixe um comentário, e a adicionaremos à lista.</span><span class="sxs-lookup"><span data-stu-id="b3728-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="b3728-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="b3728-108">In this article</span></span>

- [<span data-ttu-id="b3728-109">O que é prioridade MX?</span><span class="sxs-lookup"><span data-stu-id="b3728-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="b3728-110">Como posso validar registros SPF para meu domínio?</span><span class="sxs-lookup"><span data-stu-id="b3728-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="b3728-111">O que é um nome de domínio?</span><span class="sxs-lookup"><span data-stu-id="b3728-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="b3728-112">O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?</span><span class="sxs-lookup"><span data-stu-id="b3728-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="b3728-113">Como definir ou alterar o domínio padrão no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b3728-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="b3728-114">Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b3728-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="b3728-115">Como transferir um domínio da Microsoft 365 para outro host?</span><span class="sxs-lookup"><span data-stu-id="b3728-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="b3728-116">Por que eu tenho um domínio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="b3728-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="b3728-117">Por que eu tenho um domínio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="b3728-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="b3728-118">Como verifico meu status de educação ou sem fins lucrativos?</span><span class="sxs-lookup"><span data-stu-id="b3728-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="b3728-119">O que é prioridade MX?</span><span class="sxs-lookup"><span data-stu-id="b3728-119">What is MX priority?</span></span>

<span data-ttu-id="b3728-120">O email é entregue ao servidor de mensagens com o número de preferência mais baixo (prioridade mais alta), portanto, o registro MX que você usa para o roteamento de emails deve ter o número de preferência mais baixo, normalmente 0 ou  *alta*  prioridade.</span><span class="sxs-lookup"><span data-stu-id="b3728-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="b3728-121">Quando você cria um registro MX, a maioria dos provedores de Hospedagem de DNS exige que você defina o número de preferência.</span><span class="sxs-lookup"><span data-stu-id="b3728-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="b3728-122">Um rótulo é a  *preferência*  de caixa e uma  *prioridade*  de ti de rótulo.</span><span class="sxs-lookup"><span data-stu-id="b3728-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="b3728-123">Alguns exigem um número e alguns pedem que você selecione  *baixo*  ,  *médio*  ou  *alto*  .</span><span class="sxs-lookup"><span data-stu-id="b3728-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="b3728-124">Se você tiver apenas um registro MX, qualquer valor será adequado para prioridade ou preferência.</span><span class="sxs-lookup"><span data-stu-id="b3728-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="b3728-125">Se você tiver mais de um, certifique-se de que o registro MX para roteamento de email seja de prioridade maior do que aquele usado para validar que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="b3728-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="b3728-126">Como posso validar registros SPF para meu domínio?</span><span class="sxs-lookup"><span data-stu-id="b3728-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="b3728-127">É importante que você tenha ou crie  **apenas um registro txt para SPF**.</span><span class="sxs-lookup"><span data-stu-id="b3728-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="b3728-128">Se você já tiver um registro SPF, deverá acrescentar os novos valores do Microsoft 365 a ele, em vez de criar um novo.</span><span class="sxs-lookup"><span data-stu-id="b3728-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="b3728-129">Após adicionar ou atualizar seu registro SPF para o email da Microsoft, você deve verificar se a sintaxe está correta com uma destas ferramentas:</span><span class="sxs-lookup"><span data-stu-id="b3728-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="b3728-130">Ferramentas de teste de registro SPF</span><span class="sxs-lookup"><span data-stu-id="b3728-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="b3728-131">Surveyor SPF</span><span class="sxs-lookup"><span data-stu-id="b3728-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="b3728-132">Interface Web de busca</span><span class="sxs-lookup"><span data-stu-id="b3728-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="b3728-133">O que é um nome de domínio?</span><span class="sxs-lookup"><span data-stu-id="b3728-133">What is a domain name?</span></span>

<span data-ttu-id="b3728-134">O domínio é um nome exclusivo que é exibido após o sinal de **@** nos endereços de email e após **www.**</span><span class="sxs-lookup"><span data-stu-id="b3728-134">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="b3728-135">nos endereços de site.</span><span class="sxs-lookup"><span data-stu-id="b3728-135">in web addresses.</span></span> <span data-ttu-id="b3728-136">Normalmente, ela assume a forma do nome da sua organização e um sufixo da Internet padrão, como  *yourbusiness.com*  ou  *StateUniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="b3728-136">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="b3728-137">Usar um domínio personalizado como "**rob \@ contoso.com**" com o Microsoft 365 pode ajudar a criar credibilidade e reconhecimento para a marca.</span><span class="sxs-lookup"><span data-stu-id="b3728-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="b3728-138">Você pode [comprar um domínio no Microsoft 365, configurando-o automaticamente](../get-help-with-domains/buy-a-domain-name.md)ou pode comprar ou trazer um que você já possui de um registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="b3728-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="b3728-139">O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?</span><span class="sxs-lookup"><span data-stu-id="b3728-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="b3728-140">Se você gerenciar seus próprios registros DNS e seu host DNS não oferecer suporte a todos os registros DNS que o Microsoft 365 precisa, alguns recursos do Microsoft 365 não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="b3728-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="b3728-141">Recomendamos que você transfira seu domínio para um registrador que dê suporte a todos os registros DNS necessários.</span><span class="sxs-lookup"><span data-stu-id="b3728-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="b3728-142">Provedores que oferecem suporte a todos os registros DNS necessários:</span><span class="sxs-lookup"><span data-stu-id="b3728-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="b3728-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="b3728-143">Dynadot</span></span>
    
- <span data-ttu-id="b3728-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="b3728-144">eNomCentral</span></span>
    
- <span data-ttu-id="b3728-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="b3728-145">Europe Registry</span></span>
    
- <span data-ttu-id="b3728-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="b3728-146">GoDaddy</span></span>
    
- <span data-ttu-id="b3728-147">Foco</span><span class="sxs-lookup"><span data-stu-id="b3728-147">Hover</span></span>
    
- <span data-ttu-id="b3728-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="b3728-148">MyHosting.com</span></span>
    
- <span data-ttu-id="b3728-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="b3728-149">Name.com</span></span>
    
- <span data-ttu-id="b3728-150">Fala quase livre</span><span class="sxs-lookup"><span data-stu-id="b3728-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="b3728-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="b3728-151">Nettica</span></span>
    
- <span data-ttu-id="b3728-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="b3728-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="b3728-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="b3728-153">Network Solutions</span></span>
    
- <span data-ttu-id="b3728-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="b3728-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="b3728-155">Como definir ou alterar o domínio padrão no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b3728-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="b3728-156">Você deve ter pelo menos um domínio personalizado que tenha adicionado ao Microsoft 365 antes de poder escolher um domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="b3728-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b3728-157">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="b3728-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b3728-158">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="b3728-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b3728-159">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="b3728-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="b3728-160">Na página **domínios** , selecione o domínio que você deseja definir como o padrão para novos endereços de email.</span><span class="sxs-lookup"><span data-stu-id="b3728-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="b3728-161">Selecione **Definir como Padrão**.</span><span class="sxs-lookup"><span data-stu-id="b3728-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="b3728-162">Não é possível alterar o nome do seu domínio inicial  *. onmicrosoft.com*  .</span><span class="sxs-lookup"><span data-stu-id="b3728-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="b3728-163">Não é possível alterar o nome do seu domínio inicial  *. onmicrosoft.de*  .</span><span class="sxs-lookup"><span data-stu-id="b3728-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="b3728-164">Não é possível alterar o nome do seu domínio inicial  *. Partner.onmschina.cn*  .</span><span class="sxs-lookup"><span data-stu-id="b3728-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="b3728-165">Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b3728-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="b3728-166">Sim.</span><span class="sxs-lookup"><span data-stu-id="b3728-166">Yes.</span></span> <span data-ttu-id="b3728-167">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="b3728-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="b3728-168">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="b3728-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="b3728-169">Sim!</span><span class="sxs-lookup"><span data-stu-id="b3728-169">Yes!</span></span> <span data-ttu-id="b3728-170">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="b3728-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="b3728-171">Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="b3728-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="b3728-172">Sim!</span><span class="sxs-lookup"><span data-stu-id="b3728-172">Yes!</span></span> <span data-ttu-id="b3728-173">Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="b3728-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="b3728-174">Se você estiver permitindo que a 21Vianet gerencie suas configurações de DNS com registros NS, não será possível adicionar subdomínios.</span><span class="sxs-lookup"><span data-stu-id="b3728-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="b3728-175">Normalmente, você pode adicionar até 900 domínios à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3728-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="b3728-176">Por exemplo, você pode adicionar os domínios contoso.com e contosomarketing.com e, em seguida, adicionar os subdomínios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="b3728-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="b3728-177">Quando você adiciona um subdomínio, ele é verificado automaticamente com base no domínio pai que está sendo verificado.</span><span class="sxs-lookup"><span data-stu-id="b3728-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="b3728-178">Ao adicionar vários domínios ao Microsoft 365, você pode hospedar qualquer um dos serviços (como email) em qualquer um dos domínios que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="b3728-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="b3728-179">*Quando você altera seu email para o Microsoft 365, atualizando o registro MX de um domínio, todos os emails enviados para esse domínio serão iniciados no Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="b3728-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b3728-180">Se você adicionou um domínio do contoso.com a uma assinatura do Microsoft 365, você também pode adicionar o subdomínio xyz.contoso.com a outra organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3728-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="b3728-181">Ao adicionar o subdomínio, você será solicitado a adicionar um registro TXT no provedor de Hospedagem de DNS.</span><span class="sxs-lookup"><span data-stu-id="b3728-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="b3728-182">Como transferir um domínio da Microsoft 365 para outro host?</span><span class="sxs-lookup"><span data-stu-id="b3728-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="b3728-183">Para obter o procedimento para transferir um domínio, consulte [transferir um domínio da Microsoft para outro host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span><span class="sxs-lookup"><span data-stu-id="b3728-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="b3728-184">Piloto do Microsoft 365 do meu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="b3728-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="b3728-185">Para obter o procedimento para testar a funcionalidade de email do Microsoft 365 de um domínio personalizado para uma caixa de correio do Microsoft 365, consulte [piloto da microsoft 365 em meu domínio personalizado](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="b3728-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="b3728-186">Por que eu tenho um domínio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="b3728-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="b3728-187">O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.com*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="b3728-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="b3728-188">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="b3728-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="b3728-189">**Se você deseja que seu email pareça *Alan \@ contoso.com*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha.</span><span class="sxs-lookup"><span data-stu-id="b3728-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="b3728-190">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="b3728-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="b3728-191">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.com, não será possível alterá-lo para ser fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b3728-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="b3728-192">Para usar um domínio onmicrosoft.com diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3728-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="b3728-193">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="b3728-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="b3728-194">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b3728-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="b3728-195">Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="b3728-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="b3728-196">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="b3728-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="b3728-197">O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="b3728-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="b3728-198">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3728-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="b3728-199">Você pode continuar usando o domínio onmicrosoft.com inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b3728-199">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="b3728-200">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="b3728-200">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="b3728-201">Por que eu tenho um domínio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="b3728-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="b3728-202">O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.de*, quando você se inscreve com o serviço.</span><span class="sxs-lookup"><span data-stu-id="b3728-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="b3728-203">A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="b3728-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="b3728-204">**Se você quiser que seu email pareça *Alan@contoso.de*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha.</span><span class="sxs-lookup"><span data-stu-id="b3728-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="b3728-205">**Não é possível renomear o domínio onmicrosoft após a inscrição.**</span><span class="sxs-lookup"><span data-stu-id="b3728-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="b3728-206">Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.de, não será possível alterá-lo para ser fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="b3728-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="b3728-207">Para usar um domínio onmicrosoft.de diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3728-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="b3728-208">**Não é possível renomear a URL do site de equipe.**</span><span class="sxs-lookup"><span data-stu-id="b3728-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="b3728-209">A URL do site de equipe se baseia no nome de domínio do onmicrosoft.de. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="b3728-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="b3728-210">**Não é possível remover seu domínio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="b3728-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="b3728-211">O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="b3728-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="b3728-212">Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3728-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="b3728-213">Você pode continuar usando o domínio onmicrosoft.de inicial, mesmo depois de adicionar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b3728-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="b3728-214">Ele ainda funciona para email e outros serviços, portanto, é sua escolha.</span><span class="sxs-lookup"><span data-stu-id="b3728-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="b3728-215">Como verifico meu status de educação ou sem fins lucrativos?</span><span class="sxs-lookup"><span data-stu-id="b3728-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="b3728-216">Selecione **Configurar** no [centro de administração](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="b3728-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="b3728-217">(Certifique-se de entrar no Microsoft 365 primeiro).</span><span class="sxs-lookup"><span data-stu-id="b3728-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="b3728-218">Para se tornar o administrador da sua escola, selecione a opção  **se tornar um administrador** no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3728-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="b3728-219">Você será solicitado a adicionar um registro DNS TXT no site de host DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b3728-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="b3728-220">Por quê?</span><span class="sxs-lookup"><span data-stu-id="b3728-220">Why?</span></span> <span data-ttu-id="b3728-221">Como entrar no host DNS e adicionar um registro para o seu domínio, você prova para a Microsoft 365 que é o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="b3728-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="b3728-222">Depois de adicionar o registro, você voltará para o portal do Microsoft 365 e confirmará que você o adicionou, de modo que a Microsoft 365 possa verificar.</span><span class="sxs-lookup"><span data-stu-id="b3728-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="b3728-223">Tem uma entidade sem fins lucrativos e deseja obter o Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b3728-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="b3728-224">[Verifique se a sua organização está qualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) e inscreva-se no serviço.</span><span class="sxs-lookup"><span data-stu-id="b3728-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="b3728-225">Quer saber mais sobre tornar-se o administrador da sua escola?</span><span class="sxs-lookup"><span data-stu-id="b3728-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="b3728-226">[Saiba tudo sobre ele](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="b3728-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>