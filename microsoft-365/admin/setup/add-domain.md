---
title: Adicionar um domínio ao Microsoft 365
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
description: Adicione seu domínio ao Microsoft 365 no Centro de administração do Microsoft 365 adicionando um registro DNS ao host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470876"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="ea389-104">Adicionar um domínio ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ea389-104">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="ea389-105">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="ea389-105">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="ea389-106">*Para adicionar, modificar ou remover domínios, você **deve** ser um **Administrador Global** de um [plano empresarial ou corporativo.](https://products.office.com/business/office) Essas alterações afetam todo o locatário, administradores *personalizados* ou *usuários regulares* não poderão fazer essas alterações.*</span><span class="sxs-lookup"><span data-stu-id="ea389-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="ea389-107">Siga estas etapas para adicionar, configurar ou continuar configurando um domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ea389-108">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="ea389-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="ea389-109">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="ea389-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ea389-110">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="ea389-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="ea389-111">Vá para a **página Configurações**  >  **Domínios.**</span><span class="sxs-lookup"><span data-stu-id="ea389-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="ea389-112">Selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="ea389-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="ea389-113">Insira o nome do domínio que você deseja adicionar e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ea389-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="ea389-114">Escolha como deseja verificar se você é o próprio domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="ea389-115">Se o registrador de domínio usar [o Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365)a [Microsoft](../get-help-with-domains/domain-connect.md) configurará seus registros automaticamente fazendo você entrar no registrador e confirmar a conexão com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea389-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="ea389-116">Você será retornado ao centro de administração e a Microsoft verificará automaticamente seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="ea389-117">Use um registro TXT para verificar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="ea389-118">Selecione isso e selecione **Próximo** para ver instruções sobre como adicionar esse registro DNS ao site do registrador.</span><span class="sxs-lookup"><span data-stu-id="ea389-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="ea389-119">Isso pode levar até 30 minutos para verificar depois que você adicionou o registro.</span><span class="sxs-lookup"><span data-stu-id="ea389-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="ea389-120">Você pode adicionar um arquivo de texto ao site do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="ea389-121">Selecione e baixe o arquivo .txt do assistente de instalação e carregue o arquivo na pasta de nível superior do seu site.</span><span class="sxs-lookup"><span data-stu-id="ea389-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="ea389-122">O caminho para o arquivo deve ser semelhante a: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="ea389-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="ea389-123">Confirmaremos se você é o dono do domínio encontrando o arquivo em seu site.</span><span class="sxs-lookup"><span data-stu-id="ea389-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="ea389-124">Escolha como você deseja fazer as alterações dns necessárias para que a Microsoft use seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="ea389-125">Escolha **Adicionar os registros DNS** para mim se o registrador for compatível com o Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)e a [Microsoft](../get-help-with-domains/domain-connect.md) configurará seus registros automaticamente, fazendo com que você entre no registrador e confirme a conexão com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea389-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="ea389-126">Escolha **Eu mesmo adicionarei** os registros DNS se você quiser anexar apenas serviços específicos do Microsoft 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ea389-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="ea389-127">**Escolha essa opção se você souber exatamente o que está fazendo:**</span><span class="sxs-lookup"><span data-stu-id="ea389-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="ea389-128">Se você optar por adicionar registros *DNS*  por conta própria, selecione **Próximo** e verá uma página com todos os registros necessários para adicionar ao seu site de registradores para configurar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="ea389-129">Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="ea389-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="ea389-130">Confira a nossa lista de [instruções específicas de host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para encontrar seu host e siga as etapas para adicionar todos os registros necessários.</span><span class="sxs-lookup"><span data-stu-id="ea389-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="ea389-131">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="ea389-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="ea389-132">Se você quiser aguardar mais tarde, desmarque todos os serviços e clique em **Continuar** ou na etapa anterior de conexão de domínio escolha **Mais** Opções e selecione **Ignorar isso por enquanto**.</span><span class="sxs-lookup"><span data-stu-id="ea389-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="ea389-133">Selecione **Concluir** - você terminou!</span><span class="sxs-lookup"><span data-stu-id="ea389-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="ea389-134">Adicionar ou editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="ea389-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="ea389-135">Siga as etapas abaixo para adicionar um registro personalizado para um site ou serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="ea389-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="ea389-136">Entre no centro de administração da Microsoft em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="ea389-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ea389-137">Vá para a **página Configurações**   >  **Domínios.**</span><span class="sxs-lookup"><span data-stu-id="ea389-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="ea389-138">Selecione um domínio na página **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="ea389-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="ea389-139">Em **configurações DNS,** selecione Registros **Personalizados;** em seguida, **selecione Novo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="ea389-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="ea389-140">Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.</span><span class="sxs-lookup"><span data-stu-id="ea389-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="ea389-141">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ea389-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="ea389-142">Registradores com Conexão de Domínio</span><span class="sxs-lookup"><span data-stu-id="ea389-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="ea389-143">[Registradores habilitados](https://www.domainconnect.org/) para Conexão de Domínio permitem adicionar seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos.</span><span class="sxs-lookup"><span data-stu-id="ea389-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="ea389-144">No assistente, apenas confirmaremos se você é o próprio domínio e configurará automaticamente os registros do seu domínio, para que o email venha para o Microsoft 365 e outros serviços do Microsoft 365, como o Teams, trabalhar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ea389-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea389-145">Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="ea389-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="ea389-146">Registradores de Conexão de Domínio integrando-se com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ea389-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="ea389-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="ea389-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="ea389-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="ea389-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="ea389-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="ea389-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="ea389-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="ea389-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="ea389-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="ea389-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="ea389-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="ea389-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="ea389-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="ea389-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="ea389-154">SecureServer ou WildWestDomains (revendedores godaddy usando hospedagem DNS do SecureServer)</span><span class="sxs-lookup"><span data-stu-id="ea389-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="ea389-155">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="ea389-155">Examples:</span></span>
        - [<span data-ttu-id="ea389-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="ea389-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="ea389-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="ea389-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="ea389-158">O que acontece com meu email e site?</span><span class="sxs-lookup"><span data-stu-id="ea389-158">What happens to my email and website?</span></span>

<span data-ttu-id="ea389-159">Depois de concluir a instalação, o registro MX do seu domínio é atualizado para apontar para o Microsoft 365 e todos os emails para seu domínio começarão a chegar ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea389-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="ea389-160">Certifique-se de adicionar usuários e configurar caixas de correio no Microsoft 365 para todos que receberem emails em seu domínio!</span><span class="sxs-lookup"><span data-stu-id="ea389-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="ea389-161">Se você tiver um site que usa com a empresa, ele continuará funcionando onde está.</span><span class="sxs-lookup"><span data-stu-id="ea389-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="ea389-162">As etapas de configuração do Domain Connect não afetam seu site.</span><span class="sxs-lookup"><span data-stu-id="ea389-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ea389-163">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="ea389-163">Related articles</span></span>

[<span data-ttu-id="ea389-164">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="ea389-164">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="ea389-165">O que é um domínio?</span><span class="sxs-lookup"><span data-stu-id="ea389-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="ea389-166">Comprar um nome de domínio no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ea389-166">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="ea389-167">Configurar seu domínio (instruções específicas do host)</span><span class="sxs-lookup"><span data-stu-id="ea389-167">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)