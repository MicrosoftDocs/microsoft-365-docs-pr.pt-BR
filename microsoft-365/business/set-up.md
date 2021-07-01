---
title: Configurar o Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Descubra as etapas de instalação para Microsoft 365 Business Premium, incluindo adicionar um domínio e usuários, configurar políticas de segurança e muito mais.
ms.openlocfilehash: 74a98e915577cf86ec32a706bd3b8f558f49db95
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227630"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="34240-103">Configurar Microsoft 365 Business Premium no assistente de configuração</span><span class="sxs-lookup"><span data-stu-id="34240-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

## <a name="watch-overview-of-microsoft-365-setup"></a><span data-ttu-id="34240-104">Assista: Visão geral da Microsoft 365 configuração</span><span class="sxs-lookup"><span data-stu-id="34240-104">Watch: Overview of Microsoft 365 setup</span></span>

<span data-ttu-id="34240-105">Assista a este vídeo para ver uma visão geral Microsoft 365 Business Premium configuração.</span><span class="sxs-lookup"><span data-stu-id="34240-105">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="34240-106">Adicionar seu domínio, usuários e configurar políticas</span><span class="sxs-lookup"><span data-stu-id="34240-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="34240-107">Ao comprar Microsoft 365 Business Premium, você tem a opção de usar um domínio que você possui ou comprar um durante a [assinatura](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="34240-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="34240-108">Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="34240-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="34240-109">Adicione seu domínio para personalizar o login</span><span class="sxs-lookup"><span data-stu-id="34240-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="34240-110">Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="34240-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="34240-111">Clique em **Ir para a Configuração** pra iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="34240-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Selecione Ir para a instalação.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="34240-113">Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="34240-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="34240-114">Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="34240-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="34240-p101">Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui. Vá para [Adicionar usuários](#add-users-and-assign-licenses) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="34240-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Captura de tela da página Personalizar sua assinatura.](../media/adddomain.png)

    
4. <span data-ttu-id="34240-118">Siga as etapas no assistente para Criar [registros DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) em qualquer provedor de hospedagem DNS para Microsoft 365 que verifica se você é o próprio domínio.</span><span class="sxs-lookup"><span data-stu-id="34240-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="34240-119">Se você conhece seu host de domínio, consulte [Também Adicionar um domínio a Microsoft 365](/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="34240-119">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="34240-120">Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.</span><span class="sxs-lookup"><span data-stu-id="34240-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="34240-122">Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="34240-122">Add users and assign licenses</span></span>

<span data-ttu-id="34240-123">Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../admin/add-users/add-users.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="34240-123">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="34240-124">Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="34240-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="34240-125">Adicionar usuários ao assistente</span><span class="sxs-lookup"><span data-stu-id="34240-125">Add users in the wizard</span></span>

<span data-ttu-id="34240-126">Todos os usuários que você adicionar no assistente receberão automaticamente uma Microsoft 365 Business Premium de usuário.</span><span class="sxs-lookup"><span data-stu-id="34240-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Captura de tela da página Adicionar novos usuários no assistente](../media/addnewuserspage.png)

1. <span data-ttu-id="34240-128">Se sua assinatura Microsoft 365 Business Premium tiver usuários existentes (por exemplo, se você usou o Azure AD Conexão), você terá a opção de atribuir licenças a eles agora.</span><span class="sxs-lookup"><span data-stu-id="34240-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="34240-129">Também adicione licenças para eles.</span><span class="sxs-lookup"><span data-stu-id="34240-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="34240-p105">Depois de adicionar os usuários, você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="34240-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="34240-132">Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="34240-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="34240-133">Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.</span><span class="sxs-lookup"><span data-stu-id="34240-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="34240-134">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="34240-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="34240-135">O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="34240-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="34240-136">Caso não seja, [altere os nameservers](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)para configurar Microsoft 365 com qualquer registrador de domínios.</span><span class="sxs-lookup"><span data-stu-id="34240-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="34240-137">Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**.</span><span class="sxs-lookup"><span data-stu-id="34240-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="34240-138">Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.</span><span class="sxs-lookup"><span data-stu-id="34240-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="34240-p108">Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), você irá desejar gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados. Veja [domínios básicos](/office365/admin/get-help-with-domains/dns-basics) para mais informações.</span><span class="sxs-lookup"><span data-stu-id="34240-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Ativar a página de registros.](../media/activaterecords.png)

2. <span data-ttu-id="34240-142">Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.</span><span class="sxs-lookup"><span data-stu-id="34240-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="34240-143">Proteger sua organização</span><span class="sxs-lookup"><span data-stu-id="34240-143">Protect your organization</span></span> 

<span data-ttu-id="34240-144">As políticas configuradas no assistente são aplicadas automaticamente a um grupo [de Segurança](/office365/admin/create-groups/compare-groups#security-groups) chamado *Todos os Usuários.*</span><span class="sxs-lookup"><span data-stu-id="34240-144">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="34240-145">Você também pode criar grupos adicionais para atribuir políticas no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="34240-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="34240-146">Em Aumentar [a](../security/office-365-security/defender-for-office-365.md) **proteção contra** ameaças cibernéticas avançadas, é recomendável que você aceite os padrões para permitir Office 365 Proteção Avançada contra Ameaças examinar arquivos e links em Office aplicativos.</span><span class="sxs-lookup"><span data-stu-id="34240-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Captura de tela da página Aumentar proteção.](../media/increasetreatprotection.png)


2. <span data-ttu-id="34240-148">Na página Impedir vazamentos de dados confidenciais, aceite os padrões para ativar Office 365 DLP (Prevenção contra Perda de Dados) para rastrear dados confidenciais em **aplicativos** Office e impedir o compartilhamento acidental desses dados fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="34240-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="34240-149">Na página **Proteger dados Office** para dispositivos móveis, deixe o gerenciamento de aplicativos móveis, expanda as configurações e revise-os e selecione Criar política de gerenciamento de aplicativo **móvel.**</span><span class="sxs-lookup"><span data-stu-id="34240-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Captura de tela de proteger dados Office página móvel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="34240-151">Proteger computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="34240-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="34240-152">À esquerda, selecione  Instalação e, em Logon e **segurança,** escolha Proteger seus computadores **Windows 10 .**</span><span class="sxs-lookup"><span data-stu-id="34240-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="34240-153">Escolha **Exibir** para começar.</span><span class="sxs-lookup"><span data-stu-id="34240-153">Choose **View** to get started.</span></span> <span data-ttu-id="34240-154">Consulte [proteger seus computadores Windows 10 para](secure-win-10-pcs.md) obter instruções completas.</span><span class="sxs-lookup"><span data-stu-id="34240-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="34240-155">Implantar Office 365 aplicativos cliente</span><span class="sxs-lookup"><span data-stu-id="34240-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="34240-156">Se você optar por instalar automaticamente Office aplicativos durante a instalação, os aplicativos serão instalados nos dispositivos Windows 10 depois que os usuários entrarem no Azure AD a partir de seus dispositivos Windows, usando suas credenciais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="34240-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="34240-157">Para instalar Office em dispositivos móveis iOS ou Android, consulte Configurar dispositivos móveis [para Microsoft 365 Business Premium usuários](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="34240-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="34240-158">Você também pode instalar Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="34240-158">You can also install Office individually.</span></span> <span data-ttu-id="34240-159">Consulte [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="34240-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="34240-160">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="34240-160">Related content</span></span>

<span data-ttu-id="34240-161">[Vídeos de treinamento do Microsoft 365 Business ](../business-video/index.yml) (link da página)</span><span class="sxs-lookup"><span data-stu-id="34240-161">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
