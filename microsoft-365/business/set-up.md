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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra as etapas de instalação do Microsoft 365 Business Premium, incluindo adicionar um domínio e usuários, configurar políticas de segurança e muito mais.
ms.openlocfilehash: 5b082e78f3dc4067dcce4a96a8088b2347bc3af4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912561"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="bb5ca-103">Configurar o Microsoft 365 Business Premium no assistente de instalação</span><span class="sxs-lookup"><span data-stu-id="bb5ca-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="bb5ca-104">Assista a este vídeo para ver uma visão geral da configuração do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="bb5ca-105">Adicionar seu domínio, usuários e configurar políticas</span><span class="sxs-lookup"><span data-stu-id="bb5ca-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="bb5ca-106">Ao comprar o Microsoft 365 Business Premium, você tem a opção de usar um domínio que você possui ou comprar um durante a [assinatura](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="bb5ca-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="bb5ca-107">Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="bb5ca-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="bb5ca-108">Adicione seu domínio para personalizar o login</span><span class="sxs-lookup"><span data-stu-id="bb5ca-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="bb5ca-109">Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="bb5ca-110">Clique em **Ir para a Configuração** pra iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-110">Choose **Go to setup** to start the wizard.</span></span>

    ![Selecione Ir para a instalação.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="bb5ca-112">Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="bb5ca-113">Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bb5ca-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bb5ca-114">Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="bb5ca-115">Em vez disso, acesse [Adicionar usuários](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="bb5ca-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Captura de tela da página Personalizar sua assinatura.](../media/adddomain.png)

    
4. <span data-ttu-id="bb5ca-117">Siga as etapas no assistente para Criar registros DNS em qualquer provedor de hospedagem DNS para [o Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o próprio domínio.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="bb5ca-118">Se você conhece o host do seu domínio, também consulte as [instruções específicas do organizador](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="bb5ca-118">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="bb5ca-119">Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="bb5ca-121">Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="bb5ca-121">Add users and assign licenses</span></span>

<span data-ttu-id="bb5ca-122">Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../admin/add-users/add-users.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-122">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="bb5ca-123">Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="bb5ca-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="bb5ca-124">Adicionar usuários ao assistente</span><span class="sxs-lookup"><span data-stu-id="bb5ca-124">Add users in the wizard</span></span>

<span data-ttu-id="bb5ca-125">Todos os usuários que você adicionar no assistente receberão automaticamente uma licença do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Captura de tela da página Adicionar novos usuários no assistente](../media/addnewuserspage.png)

1. <span data-ttu-id="bb5ca-127">Se sua assinatura do Microsoft 365 Business Premium tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá a opção de atribuir licenças a eles agora.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="bb5ca-128">Também adicione licenças para eles.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="bb5ca-129">Depois de adicionar os usuários, você também terá a opção de compartilhar credenciais com os novos usuários adicionados.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="bb5ca-130">Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="bb5ca-131">Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="bb5ca-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="bb5ca-132">Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="bb5ca-133">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="bb5ca-134">O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="bb5ca-135">Caso não seja, [altere os nameservers para configurar o Microsoft 365 com qualquer registrador de domínios.](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="bb5ca-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="bb5ca-136">Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="bb5ca-137">Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="bb5ca-138">Se você possui registros DNS existentes com outros organizadores DNS (não habilitados para conexão ao domínio), convém gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="bb5ca-139">Consulte [noções básicas de domínio](/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-139">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Ativar a página de registros.](../media/activaterecords.png)

2. <span data-ttu-id="bb5ca-141">Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="bb5ca-142">Proteger sua organização</span><span class="sxs-lookup"><span data-stu-id="bb5ca-142">Protect your organization</span></span> 

<span data-ttu-id="bb5ca-143">As políticas configuradas no assistente são aplicadas automaticamente a um grupo [de Segurança](/office365/admin/create-groups/compare-groups#security-groups) chamado *Todos os Usuários.*</span><span class="sxs-lookup"><span data-stu-id="bb5ca-143">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="bb5ca-144">Você também pode criar grupos adicionais para atribuir políticas no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="bb5ca-145">Em Aumentar **a proteção contra** ameaças cibernéticas avançadas, é recomendável que você aceite os padrões para permitir que o Office [365 Advance Threat Protection](../security/office-365-security/office-365-atp.md) scan files and links in Office apps.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/office-365-atp.md) scan files and links in Office apps.</span></span>

    ![Captura de tela da página Aumentar proteção.](../media/increasetreatprotection.png)


2. <span data-ttu-id="bb5ca-147">Na página Impedir vazamentos de dados confidenciais, aceite os padrões para ativar a DLP (Prevenção contra Perda de Dados) do Office 365 para rastrear dados confidenciais em **aplicativos** do Office e impedir o compartilhamento acidental desses dados fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="bb5ca-148">Na página **Proteger dados no Office para** dispositivos móveis, deixe o gerenciamento de aplicativo móvel, expanda as configurações e revise-os e selecione Criar política de gerenciamento de aplicativo **móvel.**</span><span class="sxs-lookup"><span data-stu-id="bb5ca-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Captura de tela de proteger dados no Office para página móvel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="bb5ca-150">Proteger computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="bb5ca-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="bb5ca-151">À esquerda, selecione  Instalação e, em Logon e **segurança,** escolha **Proteger seus computadores do Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="bb5ca-152">Escolha **Exibir** para começar.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-152">Choose **View** to get started.</span></span> <span data-ttu-id="bb5ca-153">Confira [proteger seus computadores windows 10](secure-win-10-pcs.md) para obter instruções completas.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="bb5ca-154">Implantar aplicativos cliente do Office 365</span><span class="sxs-lookup"><span data-stu-id="bb5ca-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="bb5ca-155">Se você optar por instalar automaticamente os aplicativos do Office durante a instalação, os aplicativos serão instalados nos dispositivos Windows 10 depois que os usuários entrarem no Azure AD a partir de seus dispositivos Windows, usando suas credenciais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="bb5ca-156">Para instalar o Office em dispositivos móveis iOS ou Android, consulte [Configurar dispositivos móveis para usuários do Microsoft 365 Business Premium.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="bb5ca-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="bb5ca-157">Você também pode instalar o Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-157">You can also install Office individually.</span></span> <span data-ttu-id="bb5ca-158">Confira [instalar o Office em um computador ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="bb5ca-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb5ca-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="bb5ca-159">See also</span></span>

[<span data-ttu-id="bb5ca-160">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="bb5ca-160">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)