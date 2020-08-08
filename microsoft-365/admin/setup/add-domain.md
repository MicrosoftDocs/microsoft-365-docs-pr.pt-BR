---
title: Adicionar um domínio ao Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Adicione seu domínio ao Microsoft 365 no centro de administração do Microsoft 365 adicionando um registro DNS no seu host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: 8b70466e5cf82d9cf5be67162263f28ab5bd0d5d
ms.sourcegitcommit: 20c219332270f1013d48b39773dd0e48dabad9e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2020
ms.locfileid: "46592293"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="5f2e8-104">Adicionar um domínio ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f2e8-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5f2e8-105">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-105">The admin center is changing.</span></span> <span data-ttu-id="5f2e8-106">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="5f2e8-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="5f2e8-107">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="5f2e8-108">*Para adicionar, modificar ou remover domínios, você **deve** ser um **administrador global** de um [plano comercial ou empresarial](https://products.office.com/business/office). Essas alterações afetam todo o locatário, *os administradores personalizados* ou *os usuários regulares* não poderão fazer essas alterações.*</span><span class="sxs-lookup"><span data-stu-id="5f2e8-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="5f2e8-109">Siga estas etapas para adicionar, configurar ou continuar a configurar um domínio.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5f2e8-110">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="5f2e8-111">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5f2e8-112">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5f2e8-113">Vá para a página de domínios de **configurações**  >  **Domains** .</span><span class="sxs-lookup"><span data-stu-id="5f2e8-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="5f2e8-114">Selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="5f2e8-115">Insira o nome do domínio que você deseja adicionar e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="5f2e8-116">Escolha como deseja verificar se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="5f2e8-117">Se seu domínio estiver registrado em GoDaddy ou 1 &amp; 1, selecione **entrar em**  >  **seguida** e [a Microsoft configurará seus registros automaticamente](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="5f2e8-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="5f2e8-118">É possível enviar um email para o contato registrado do domínio com um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="5f2e8-119">Se você não reconhece ou tem acesso ao email no registro, você pode usar a terceira opção.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="5f2e8-120">Use um registro TXT para verificar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="5f2e8-121">Selecione-o e selecione **Avançar** para ver instruções sobre como adicionar esse registro DNS ao site do registrador.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="5f2e8-122">Isso pode levar até 30 minutos para verificar após você ter adicionado o registro.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="5f2e8-123">Escolha como você deseja fazer as alterações de DNS necessárias para o Office usar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="5f2e8-124">Escolha **adicionar os registros DNS para mim** se quiser que o Office configure o DNS automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="5f2e8-125">Escolha **eu mesmo adicionarei os registros DNS** se você quiser anexar apenas serviços específicos da Microsoft 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso mais tarde.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="5f2e8-126">**Escolha essa opção se você souber exatamente o que está fazendo:**</span><span class="sxs-lookup"><span data-stu-id="5f2e8-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="5f2e8-127">Se você optar por *adicionar registros DNS por conta própria* , selecione **Avançar** e verá uma página com todos os registros que você precisa adicionar ao site de registradores para configurar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="5f2e8-128">Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="5f2e8-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="5f2e8-129">Confira a nossa lista de [instruções específicas de host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para encontrar seu host e siga as etapas para adicionar todos os registros necessários.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="5f2e8-130">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="5f2e8-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="5f2e8-131">Se você quiser aguardar mais tarde, role até o final e selecione **ignorar esta etapa**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="5f2e8-132">Selecione **concluir** -você terminou!</span><span class="sxs-lookup"><span data-stu-id="5f2e8-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="5f2e8-133">Adicionar ou editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="5f2e8-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="5f2e8-134">Siga as etapas abaixo para adicionar um registro personalizado para um site ou serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="5f2e8-135">Entre no centro de administração da Microsoft em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="5f2e8-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="5f2e8-136">Vá para a página de domínios de **configurações**   >  **Domains** .</span><span class="sxs-lookup"><span data-stu-id="5f2e8-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="5f2e8-137">Selecione um domínio na página **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="5f2e8-138">Em **configurações de DNS**, selecione **registros personalizados**; em seguida, selecione **novo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="5f2e8-139">Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="5f2e8-140">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="5f2e8-141">Registradores com conexão de domínio</span><span class="sxs-lookup"><span data-stu-id="5f2e8-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="5f2e8-142">Os registradores habilitados para [conexão de domínio](https://www.domainconnect.org/) permitem que você adicione seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="5f2e8-143">No assistente, apenas confirmará que você é o proprietário do domínio e, em seguida, configurar automaticamente os registros do seu domínio, para que os emails sejam da Microsoft 365 e de outros serviços da Microsoft 365, como o Teams, trabalhem com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f2e8-144">Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="5f2e8-145">Registradores de conexão de domínio que se integram ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f2e8-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="5f2e8-146">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="5f2e8-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="5f2e8-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="5f2e8-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="5f2e8-148">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="5f2e8-148">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="5f2e8-149">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="5f2e8-149">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="5f2e8-150">WordPress</span><span class="sxs-lookup"><span data-stu-id="5f2e8-150">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="5f2e8-151">Plesk</span><span class="sxs-lookup"><span data-stu-id="5f2e8-151">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="5f2e8-152">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="5f2e8-152">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="5f2e8-153">SecureServer ou WildWestDomains (GoDaddy revendedores usando o SecureServer de Hospedagem de DNS)</span><span class="sxs-lookup"><span data-stu-id="5f2e8-153">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="5f2e8-154">Domínios MadDog</span><span class="sxs-lookup"><span data-stu-id="5f2e8-154">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="5f2e8-155">Baratosnames</span><span class="sxs-lookup"><span data-stu-id="5f2e8-155">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="5f2e8-156">O que acontece com meus emails e sites?</span><span class="sxs-lookup"><span data-stu-id="5f2e8-156">What happens to my email and website?</span></span>

<span data-ttu-id="5f2e8-157">Depois que você concluir a instalação, o registro MX do seu domínio será atualizado para apontar para o Microsoft 365 e todos os emails do seu domínio serão iniciados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-157">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="5f2e8-158">Verifique se você adicionou usuários e configurou caixas de correio no Microsoft 365 para todas as pessoas que recebem emails no seu domínio!</span><span class="sxs-lookup"><span data-stu-id="5f2e8-158">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="5f2e8-159">Se você tiver um site que usa com a empresa, ele continuará funcionando onde está.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-159">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="5f2e8-160">As etapas de configuração de conexão de domínio não afetam o site.</span><span class="sxs-lookup"><span data-stu-id="5f2e8-160">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5f2e8-161">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="5f2e8-161">Related articles</span></span>

[<span data-ttu-id="5f2e8-162">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="5f2e8-162">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="5f2e8-163">O que é um domínio?</span><span class="sxs-lookup"><span data-stu-id="5f2e8-163">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="5f2e8-164">Comprar um nome de domínio no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f2e8-164">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="5f2e8-165">Configurar seu domínio (instruções específicas do host)</span><span class="sxs-lookup"><span data-stu-id="5f2e8-165">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="5f2e8-166">Obter ajuda com domínios</span><span class="sxs-lookup"><span data-stu-id="5f2e8-166">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
