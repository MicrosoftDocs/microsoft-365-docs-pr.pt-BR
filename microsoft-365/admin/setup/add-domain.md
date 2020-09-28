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
ms.openlocfilehash: 09a66b9ac4f97a076d71dd7f259678181378ae48
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295017"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="6c917-104">Adicionar um domínio ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c917-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6c917-105">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="6c917-105">The admin center is changing.</span></span> <span data-ttu-id="6c917-106">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6c917-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="6c917-107">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6c917-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="6c917-108">*Para adicionar, modificar ou remover domínios, você **deve** ser um **administrador global** de um [plano comercial ou empresarial](https://products.office.com/business/office). Essas alterações afetam todo o locatário, *os administradores personalizados* ou *os usuários regulares* não poderão fazer essas alterações.*</span><span class="sxs-lookup"><span data-stu-id="6c917-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="6c917-109">Siga estas etapas para adicionar, configurar ou continuar a configurar um domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6c917-110">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="6c917-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="6c917-111">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="6c917-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6c917-112">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="6c917-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="6c917-113">Vá para a página de domínios de **configurações**  >  **Domains** .</span><span class="sxs-lookup"><span data-stu-id="6c917-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="6c917-114">Selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="6c917-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="6c917-115">Insira o nome do domínio que você deseja adicionar e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6c917-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="6c917-116">Escolha como deseja verificar se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="6c917-117">Se o seu registrador de domínio usar a [conexão de domínio](#domain-connect-registrars-integrating-with-microsoft-365), [a Microsoft configurará seus registros automaticamente](../get-help-with-domains/domain-connect.md) , fazendo você entrar em seu registrador e confirmar a conexão com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c917-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="6c917-118">Você retornará ao centro de administração e a Microsoft verificará automaticamente o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="6c917-119">Use um registro TXT para verificar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="6c917-120">Selecione-o e selecione **Avançar** para ver instruções sobre como adicionar esse registro DNS ao site do registrador.</span><span class="sxs-lookup"><span data-stu-id="6c917-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="6c917-121">Isso pode levar até 30 minutos para verificar após você ter adicionado o registro.</span><span class="sxs-lookup"><span data-stu-id="6c917-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="6c917-122">Você pode adicionar um arquivo de texto ao site do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="6c917-123">Selecione e baixe o arquivo. txt do assistente de instalação e, em seguida, carregue o arquivo para a pasta de nível superior do seu site.</span><span class="sxs-lookup"><span data-stu-id="6c917-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="6c917-124">O caminho para o arquivo deve ser semelhante a: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="6c917-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="6c917-125">Vamos confirmar que você é o proprietário do domínio encontrando o arquivo no seu site.</span><span class="sxs-lookup"><span data-stu-id="6c917-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="6c917-126">Escolha como você deseja fazer as alterações de DNS necessárias para que a Microsoft use seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="6c917-127">Escolha **adicionar os registros DNS para mim** se o seu registrador oferecer suporte à [conexão de domínio](#domain-connect-registrars-integrating-with-microsoft-365)e a Microsoft [configurar seus registros automaticamente](../get-help-with-domains/domain-connect.md) , fazendo você entrar em seu registrador e confirmar a conexão com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c917-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="6c917-128">Escolha **eu mesmo adicionarei os registros DNS** se você quiser anexar apenas serviços específicos da Microsoft 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso mais tarde.</span><span class="sxs-lookup"><span data-stu-id="6c917-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="6c917-129">**Escolha essa opção se você souber exatamente o que está fazendo:**</span><span class="sxs-lookup"><span data-stu-id="6c917-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="6c917-130">Se você optar por *adicionar registros DNS por conta própria*  , selecione **Avançar** e verá uma página com todos os registros que você precisa adicionar ao site de registradores para configurar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="6c917-131">Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="6c917-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="6c917-132">Confira a nossa lista de [instruções específicas de host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para encontrar seu host e siga as etapas para adicionar todos os registros necessários.</span><span class="sxs-lookup"><span data-stu-id="6c917-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="6c917-133">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="6c917-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="6c917-134">Se você quiser aguardar mais tarde, desmarque todos os serviços e clique em **continuar**, ou na etapa de conexão de domínio anterior, escolha **mais opções** e selecione **ignorar isso por enquanto**.</span><span class="sxs-lookup"><span data-stu-id="6c917-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="6c917-135">Selecione **concluir** -você terminou!</span><span class="sxs-lookup"><span data-stu-id="6c917-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="6c917-136">Adicionar ou editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="6c917-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="6c917-137">Siga as etapas abaixo para adicionar um registro personalizado para um site ou serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="6c917-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="6c917-138">Entre no centro de administração da Microsoft em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="6c917-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="6c917-139">Vá para a página de domínios de **configurações**   >  **Domains** .</span><span class="sxs-lookup"><span data-stu-id="6c917-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="6c917-140">Selecione um domínio na página **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="6c917-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="6c917-141">Em **configurações de DNS**, selecione **registros personalizados**; em seguida, selecione **novo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="6c917-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="6c917-142">Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.</span><span class="sxs-lookup"><span data-stu-id="6c917-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="6c917-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6c917-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="6c917-144">Registradores com conexão de domínio</span><span class="sxs-lookup"><span data-stu-id="6c917-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="6c917-145">Os registradores habilitados para [conexão de domínio](https://www.domainconnect.org/) permitem que você adicione seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos.</span><span class="sxs-lookup"><span data-stu-id="6c917-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="6c917-146">No assistente, apenas confirmará que você é o proprietário do domínio e, em seguida, configurar automaticamente os registros do seu domínio, para que os emails sejam da Microsoft 365 e de outros serviços da Microsoft 365, como o Teams, trabalhem com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6c917-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c917-147">Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="6c917-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="6c917-148">Registradores de conexão de domínio que se integram ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c917-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="6c917-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="6c917-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="6c917-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="6c917-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="6c917-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="6c917-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="6c917-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="6c917-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="6c917-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="6c917-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="6c917-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="6c917-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="6c917-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="6c917-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="6c917-156">SecureServer ou WildWestDomains (GoDaddy revendedores usando o SecureServer de Hospedagem de DNS)</span><span class="sxs-lookup"><span data-stu-id="6c917-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="6c917-157">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="6c917-157">Examples:</span></span>
        - [<span data-ttu-id="6c917-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="6c917-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="6c917-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="6c917-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="6c917-160">O que acontece com meus emails e sites?</span><span class="sxs-lookup"><span data-stu-id="6c917-160">What happens to my email and website?</span></span>

<span data-ttu-id="6c917-161">Depois que você concluir a instalação, o registro MX do seu domínio será atualizado para apontar para o Microsoft 365 e todos os emails do seu domínio serão iniciados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c917-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6c917-162">Verifique se você adicionou usuários e configurou caixas de correio no Microsoft 365 para todas as pessoas que recebem emails no seu domínio!</span><span class="sxs-lookup"><span data-stu-id="6c917-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="6c917-163">Se você tiver um site que usa com a empresa, ele continuará funcionando onde está.</span><span class="sxs-lookup"><span data-stu-id="6c917-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="6c917-164">As etapas de configuração de conexão de domínio não afetam o site.</span><span class="sxs-lookup"><span data-stu-id="6c917-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c917-165">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="6c917-165">Related articles</span></span>

[<span data-ttu-id="6c917-166">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="6c917-166">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="6c917-167">O que é um domínio?</span><span class="sxs-lookup"><span data-stu-id="6c917-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="6c917-168">Comprar um nome de domínio no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c917-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="6c917-169">Configurar seu domínio (instruções específicas do host)</span><span class="sxs-lookup"><span data-stu-id="6c917-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
