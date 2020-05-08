---
title: Configurar o Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra as etapas de configuração para o Microsoft 365 Business Premium, incluindo a adição de um domínio e usuários, a configuração de políticas de segurança e muito mais.
ms.openlocfilehash: 03f446f790a664af85cc630048bc022d88b6e54f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165768"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="eacd2-103">Configurar o Microsoft 365 Business Premium no assistente de configuração</span><span class="sxs-lookup"><span data-stu-id="eacd2-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="eacd2-104">Assista a este vídeo para obter uma visão geral da configuração do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="eacd2-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="eacd2-105">Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="eacd2-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="eacd2-106">Adicionar o domínio, os usuários e as políticas de configuração</span><span class="sxs-lookup"><span data-stu-id="eacd2-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="eacd2-107">[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="eacd2-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="eacd2-108">Ao comprar o Microsoft 365 Business Premium, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [inscrição](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="eacd2-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="eacd2-109">Se você comprou um novo domínio ao se inscrever, seu domínio está configurado e você pode mover para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="eacd2-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="eacd2-110">Adicionar seu domínio para personalizar a entrada</span><span class="sxs-lookup"><span data-stu-id="eacd2-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="eacd2-111">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="eacd2-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="eacd2-112">Escolha **ir para a configuração** para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="eacd2-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Selecione ir para a configuração.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="eacd2-114">Na página **instalar aplicativos do Office** , você pode, opcionalmente, instalar os aplicativos no seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="eacd2-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="eacd2-115">Na etapa **Adicionar domínio** , insira o nome de domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eacd2-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eacd2-116">Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** .</span><span class="sxs-lookup"><span data-stu-id="eacd2-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="eacd2-117">Em vez disso, vá para [Adicionar usuários](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="eacd2-117">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Captura de tela da página personalizar sua sessão de entrada.](../media/adddomain.png)

    
4. <span data-ttu-id="eacd2-119">Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="eacd2-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="eacd2-120">Se você souber seu host de domínio, consulte também as [instruções específicas do host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="eacd2-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="eacd2-121">Se o seu provedor de hospedagem for o GoDaddy ou outro host habilitado com o [domínio Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e você será solicitado a entrar novamente e permitir que a Microsoft autentique em seu nome.</span><span class="sxs-lookup"><span data-stu-id="eacd2-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Na página Confirmar acesso do GoDaddy, selecione autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="eacd2-123">Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="eacd2-123">Add users and assign licenses</span></span>

<span data-ttu-id="eacd2-124">Você pode adicionar usuários no assistente, mas você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="eacd2-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="eacd2-125">Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="eacd2-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="eacd2-126">Adicionar usuários no assistente</span><span class="sxs-lookup"><span data-stu-id="eacd2-126">Add users in the wizard</span></span>

<span data-ttu-id="eacd2-127">Todos os usuários adicionados ao assistente recebem automaticamente uma licença do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="eacd2-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Captura de tela da página Adicionar novos usuários no assistente](../media/addnewuserspage.png)

1. <span data-ttu-id="eacd2-129">Se sua assinatura do Microsoft 365 Business Premium tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá uma opção para atribuir licenças a eles agora.</span><span class="sxs-lookup"><span data-stu-id="eacd2-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="eacd2-130">Adicione licenças para eles também.</span><span class="sxs-lookup"><span data-stu-id="eacd2-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="eacd2-131">Depois de adicionar os usuários, você também terá uma opção de compartilhar credenciais com os novos usuários que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="eacd2-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="eacd2-132">Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="eacd2-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="eacd2-133">Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="eacd2-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="eacd2-134">Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect para configurar usuários, esta etapa não será exibida.</span><span class="sxs-lookup"><span data-stu-id="eacd2-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="eacd2-135">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="eacd2-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="eacd2-136">O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="eacd2-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="eacd2-137">Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="eacd2-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="eacd2-138">Se você tiver registros DNS existentes, por exemplo, um site existente, mas seu host DNS estiver habilitado para [conexão de domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), escolha **adicionar registros para mim**.</span><span class="sxs-lookup"><span data-stu-id="eacd2-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="eacd2-139">Na página **escolha seus serviços online** , aceite todos os padrões e escolha **Avançar**e escolha **autorizar** na página do seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="eacd2-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="eacd2-140">Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), será necessário gerenciar seus próprios registros DNS para garantir que os serviços existentes permaneçam conectados.</span><span class="sxs-lookup"><span data-stu-id="eacd2-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="eacd2-141">Confira [noções básicas sobre domínios](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eacd2-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Página ativar registros.](../media/activaterecords.png)

2. <span data-ttu-id="eacd2-143">Siga as etapas do assistente e email e outros serviços serão configurados para você.</span><span class="sxs-lookup"><span data-stu-id="eacd2-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="eacd2-144">Proteger sua organização</span><span class="sxs-lookup"><span data-stu-id="eacd2-144">Protect your organization</span></span> 

<span data-ttu-id="eacd2-145">As políticas configuradas no assistente são aplicadas automaticamente a um [grupo de segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *todos os usuários*.</span><span class="sxs-lookup"><span data-stu-id="eacd2-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="eacd2-146">Você também pode criar grupos adicionais para atribuir políticas ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="eacd2-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="eacd2-147">Com o **aumento da proteção contra ameaças avançadas da Cyber**, é recomendável que você aceite os padrões para permitir a [proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) examinar arquivos e links em aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="eacd2-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Captura de tela da página aumentar proteção.](../media/increasetreatprotection.png)


2. <span data-ttu-id="eacd2-149">Na página **evitar vazamentos de dados confidenciais** , aceite os padrões para ativar a prevenção de perda de dados (DLP) do Office 365 para rastrear dados confidenciais em aplicativos do Office e impedir o compartilhamento acidental desses fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="eacd2-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="eacd2-150">Na página **proteger dados no Office para celular** , deixe gerenciamento de aplicativo móvel, expanda as configurações e revise-as e selecione **criar política de gerenciamento de aplicativo móvel**.</span><span class="sxs-lookup"><span data-stu-id="eacd2-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Captura de tela de proteger dados no Office para páginas móveis.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="eacd2-152">Proteger computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="eacd2-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="eacd2-153">Na barra de navegação esquerda, selecione **configuração** e, em seguida, em **entrada e segurança**, escolha **proteger seus computadores com Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="eacd2-153">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="eacd2-154">Escolha **Exibir** para começar.</span><span class="sxs-lookup"><span data-stu-id="eacd2-154">Choose **View** to get started.</span></span> <span data-ttu-id="eacd2-155">Confira [proteger seus computadores com Windows 10](secure-win-10-pcs.md) para obter instruções completas.</span><span class="sxs-lookup"><span data-stu-id="eacd2-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="eacd2-156">Implantar aplicativos cliente do Office 365</span><span class="sxs-lookup"><span data-stu-id="eacd2-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="eacd2-157">Se você optar por instalar automaticamente aplicativos do Office durante a instalação, os aplicativos serão instalados nos dispositivos Windows 10 depois que eles entrarem no Azure AD de seus dispositivos Windows, usando suas credenciais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="eacd2-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="eacd2-158">Para instalar o Office em dispositivos móveis iOS ou Android, confira [configurar dispositivos móveis para usuários do Microsoft 365 Business Premium](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="eacd2-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="eacd2-159">Você também pode instalar o Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="eacd2-159">You can also install Office individually.</span></span> <span data-ttu-id="eacd2-160">Confira [instalar o Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="eacd2-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="eacd2-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="eacd2-161">See also</span></span>

[<span data-ttu-id="eacd2-162">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="eacd2-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
