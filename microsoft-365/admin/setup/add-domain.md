---
title: Adicionar um domínio ao Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Adicione seu domínio ao Office 365 no centro de administração do Microsoft 365 adicionando um registro DNS no seu host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: a77526efc526073e17b535612213202ad22d5657
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800018"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="59d60-104">Adicionar um domínio ao Office 365</span><span class="sxs-lookup"><span data-stu-id="59d60-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="59d60-105">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="59d60-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="59d60-106">*Para adicionar, modificar ou remover domínios, você **deve** ser um **administrador global** de um [plano comercial ou empresarial](https://products.office.com/business/office). Essas alterações afetam todo o locatário, *os administradores personalizados* ou *os usuários regulares* não poderão fazer essas alterações.*</span><span class="sxs-lookup"><span data-stu-id="59d60-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="59d60-107">Siga estas etapas para adicionar, configurar ou continuar a configurar um domínio.</span><span class="sxs-lookup"><span data-stu-id="59d60-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59d60-108">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="59d60-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="59d60-109">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="59d60-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59d60-110">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="59d60-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="59d60-111">Vá para a página **Configurar** > **domínios** .</span><span class="sxs-lookup"><span data-stu-id="59d60-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="59d60-112">Selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="59d60-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="59d60-113">Insira o nome do domínio que você deseja adicionar e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="59d60-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="59d60-114">Escolha como deseja verificar se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="59d60-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="59d60-115">Se seu domínio estiver registrado em GoDaddy ou 1&amp;1, selecione **entrar em** > **seguida** e[a Microsoft configurará seus registros automaticamente](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="59d60-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft[will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="59d60-116">É possível enviar um email para o contato registrado do domínio com um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="59d60-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="59d60-117">Se você não reconhece ou tem acesso ao email no registro, você pode usar a terceira opção.</span><span class="sxs-lookup"><span data-stu-id="59d60-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="59d60-118">Use um registro TXT para verificar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="59d60-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="59d60-119">Selecione-o e selecione **Avançar** para ver instruções sobre como adicionar esse registro DNS ao site do registrador.</span><span class="sxs-lookup"><span data-stu-id="59d60-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="59d60-120">Isso pode levar até 30 minutos para verificar após você ter adicionado o registro.</span><span class="sxs-lookup"><span data-stu-id="59d60-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="59d60-121">Escolha como você deseja fazer as alterações de DNS necessárias para o Office usar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="59d60-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="59d60-122">Escolha **adicionar os registros DNS para mim** se quiser que o Office configure o DNS automaticamente.</span><span class="sxs-lookup"><span data-stu-id="59d60-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="59d60-123">Escolha **eu mesmo adicionará os registros DNS** se você quiser anexar apenas serviços específicos do Office 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso mais tarde.</span><span class="sxs-lookup"><span data-stu-id="59d60-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="59d60-124">**Escolha essa opção se você souber exatamente o que está fazendo:**</span><span class="sxs-lookup"><span data-stu-id="59d60-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="59d60-125">Se você optar por *adicionar registros DNS por conta própria* , selecione **Avançar** e verá uma página com todos os registros que você precisa adicionar ao site de registradores para configurar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="59d60-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="59d60-126">Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="59d60-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="59d60-127">Confira a nossa lista de [instruções específicas de host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) para encontrar seu host e siga as etapas para adicionar todos os registros necessários.</span><span class="sxs-lookup"><span data-stu-id="59d60-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="59d60-128">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="59d60-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="59d60-129">Se você quiser aguardar mais tarde, role até o final e selecione **ignorar esta etapa**.</span><span class="sxs-lookup"><span data-stu-id="59d60-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="59d60-130">Selecione **concluir** -você terminou!</span><span class="sxs-lookup"><span data-stu-id="59d60-130">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="59d60-131">Adicionar ou editar registros DNS personalizados</span><span class="sxs-lookup"><span data-stu-id="59d60-131">Add or edit custom DNS records</span></span>

<span data-ttu-id="59d60-132">Siga as etapas abaixo para adicionar um registro personalizado para um site ou serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="59d60-132">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="59d60-133">Entre no centro de administração da Microsoft em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="59d60-133">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="59d60-134">Vá para a página de**domínios** de **configurações**  > .</span><span class="sxs-lookup"><span data-stu-id="59d60-134">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="59d60-135">Selecione um domínio na página **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="59d60-135">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="59d60-136">Em **configurações de DNS**, selecione **registros personalizados**; em seguida, selecione **novo registro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="59d60-136">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="59d60-137">Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.</span><span class="sxs-lookup"><span data-stu-id="59d60-137">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="59d60-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="59d60-138">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="59d60-139">Registradores com conexão de domínio</span><span class="sxs-lookup"><span data-stu-id="59d60-139">Registrars with Domain Connect</span></span>

<span data-ttu-id="59d60-140">Os registradores habilitados para [conexão de domínio](https://www.domainconnect.org/) permitem que você adicione seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos.</span><span class="sxs-lookup"><span data-stu-id="59d60-140">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="59d60-141">No assistente, apenas confirmará que você é o proprietário do domínio e, em seguida, configurar automaticamente os registros do seu domínio, para que os emails sejam da Microsoft 365 e de outros serviços da Microsoft 365, como o Teams, trabalhem com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="59d60-141">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59d60-142">Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="59d60-142">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="59d60-143">Registradores de conexão de domínio que se integram ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59d60-143">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="59d60-144">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="59d60-144">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="59d60-145">123Reg</span><span class="sxs-lookup"><span data-stu-id="59d60-145">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="59d60-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="59d60-146">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="59d60-147">WordPress</span><span class="sxs-lookup"><span data-stu-id="59d60-147">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="59d60-148">Plesk</span><span class="sxs-lookup"><span data-stu-id="59d60-148">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="59d60-149">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="59d60-149">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="59d60-150">SecureServer ou WildWestDomains (GoDaddy revendedores usando o SecureServer de Hospedagem de DNS)</span><span class="sxs-lookup"><span data-stu-id="59d60-150">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="59d60-151">Domínios MadDog</span><span class="sxs-lookup"><span data-stu-id="59d60-151">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="59d60-152">Baratosnames</span><span class="sxs-lookup"><span data-stu-id="59d60-152">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="59d60-153">O que acontece com meus emails e sites?</span><span class="sxs-lookup"><span data-stu-id="59d60-153">What happens to my email and website?</span></span>

<span data-ttu-id="59d60-154">Depois que você concluir a instalação, o registro MX do seu domínio será atualizado para apontar para o Microsoft 365 e todos os emails do seu domínio serão iniciados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59d60-154">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="59d60-155">Verifique se você adicionou usuários e configurou caixas de correio no Office 365 para todos aqueles que recebem emails em seu domínio!</span><span class="sxs-lookup"><span data-stu-id="59d60-155">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="59d60-156">Se você tiver um site que usa com a empresa, ele continuará funcionando onde está.</span><span class="sxs-lookup"><span data-stu-id="59d60-156">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="59d60-157">As etapas de configuração de conexão de domínio não afetam o site.</span><span class="sxs-lookup"><span data-stu-id="59d60-157">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="59d60-158">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="59d60-158">Related articles</span></span>

[<span data-ttu-id="59d60-159">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="59d60-159">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="59d60-160">O que é um domínio?</span><span class="sxs-lookup"><span data-stu-id="59d60-160">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="59d60-161">Comprar um nome de domínio no Office 365</span><span class="sxs-lookup"><span data-stu-id="59d60-161">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="59d60-162">Configurar seu domínio (instruções específicas do host)</span><span class="sxs-lookup"><span data-stu-id="59d60-162">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="59d60-163">Obter ajuda com domínios</span><span class="sxs-lookup"><span data-stu-id="59d60-163">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
