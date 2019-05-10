---
title: Configurar o Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660710"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="06b27-103">Configurar o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="06b27-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="06b27-104">Antes de começar, veja obter os detalhes de inscrição do [Microsoft 365 Business](get-microsoft-365-business.md) .</span><span class="sxs-lookup"><span data-stu-id="06b27-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="06b27-105">Assista a um [pequeno vídeo sobre como configurar o Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) usando o assistente de configuração e quando você não tem um Active Directory local</span><span class="sxs-lookup"><span data-stu-id="06b27-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="06b27-106">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="06b27-106">Overview</span></span>

<span data-ttu-id="06b27-107">A maioria das etapas de configuração pode ser feita no assistente de configuração, mas as outras opções também são listadas.</span><span class="sxs-lookup"><span data-stu-id="06b27-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="06b27-108">[Adicionar seu domínio](#add-your-domain-to-personalize-sign-in) (se você comprou seu domínio durante a [inscrição](sign-up.md), esta etapa já foi feita.)</span><span class="sxs-lookup"><span data-stu-id="06b27-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="06b27-109">Adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="06b27-109">Add users.</span></span> <span data-ttu-id="06b27-110">Você pode fazer isso de uma das três maneiras:</span><span class="sxs-lookup"><span data-stu-id="06b27-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="06b27-111">No [Assistente de configuração](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="06b27-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="06b27-112">Use a sincronização de diretórios para [Adicionar usuários usando o Azure ad Connect](#add-users-by-using-azure-ad-connect) se você tiver um Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="06b27-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="06b27-113">Você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="06b27-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="06b27-114">Configurar políticas de segurança e configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="06b27-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="06b27-115">Você pode fazer isso de uma das três maneiras:</span><span class="sxs-lookup"><span data-stu-id="06b27-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="06b27-116">No [Assistente de configuração](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="06b27-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="06b27-117">No [centro de administração](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="06b27-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="06b27-118">No [centro de administração do Intune](https://docs.microsoft.com/intune/what-is-device-management).</span><span class="sxs-lookup"><span data-stu-id="06b27-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="06b27-119">Configurar e gerenciar dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="06b27-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="06b27-120">Quando você ingressa em um dispositivo WIndows 10 no Azure AD, todas as políticas são aplicadas a ela.</span><span class="sxs-lookup"><span data-stu-id="06b27-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="06b27-121">Configurar as configurações de dispositivo do Windows 10 no [Assistente de configuração](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="06b27-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="06b27-122">Ingressar em um [novo dispositivo Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="06b27-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="06b27-123">Ingresse um [dispositivo existente do Windows 10](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="06b27-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="06b27-124">Instale o Office 365 Business.</span><span class="sxs-lookup"><span data-stu-id="06b27-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="06b27-125">Você pode instalar automaticamente o Office nos dispositivos Windows usando o [Assistente de configuração](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="06b27-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="06b27-126">Instale automaticamente o [Office](auto-install-or-uninstall-office.md) a partir do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="06b27-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="06b27-127">Permitir que os usuários [instalem aplicativos do Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="06b27-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="06b27-128">Configurar segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="06b27-128">Set up additional security.</span></span>
    - <span data-ttu-id="06b27-129">O assistente de configuração adiciona políticas para proteger seus dispositivos, mas você também pode aproveitar os recursos de [segurança adicionais](#additional-security-settings) para ajudar a proteger seus dados, contas e emails.</span><span class="sxs-lookup"><span data-stu-id="06b27-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="06b27-130">Adicionar seu domínio, usuários e configurar políticas</span><span class="sxs-lookup"><span data-stu-id="06b27-130">Add your domain, users and set up policies</span></span>

![Faixa que aponta para https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="06b27-132">Ao comprar o Microsoft 365 Business, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [inscrição](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="06b27-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="06b27-133">Se você comprou um novo domínio ao se inscrever, seu domínio está configurado e você pode mover para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="06b27-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="06b27-134">Adicionar seu domínio para personalizar a entrada</span><span class="sxs-lookup"><span data-stu-id="06b27-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="06b27-135">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="06b27-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="06b27-136">Escolha **Adicionar um domínio** para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="06b27-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Selecione Adicionar um domínio.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="06b27-138">No assistente, digite o nome de domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="06b27-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Captura de tela da página personalizar sua sessão de entrada.](media/personalizesignin.png)

    
4. <span data-ttu-id="06b27-140">Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="06b27-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="06b27-141">Se você souber seu host de domínio, consulte também as [instruções específicas do host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="06b27-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="06b27-142">Se o seu provedor de hospedagem for o GoDaddy, o processo será fácil e você será solicitado a entrar e permitir que a Microsoft autentique em seu nome:</span><span class="sxs-lookup"><span data-stu-id="06b27-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Na página Confirmar acesso do GoDaddy, selecione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="06b27-144">Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="06b27-144">Add users and assign licenses</span></span>

<span data-ttu-id="06b27-145">Você pode adicionar usuários no assistente, mas você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="06b27-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="06b27-146">Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="06b27-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="06b27-147">Adicionar usuários no assistente</span><span class="sxs-lookup"><span data-stu-id="06b27-147">Add users in the wizard</span></span>

<span data-ttu-id="06b27-148">Todos os usuários adicionados ao assistente recebem automaticamente uma licença de negócios do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06b27-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="06b27-149">Se você tiver um controlador de domínio local e estiver usando o Active Directory, consulte [How to DDD Users by using Azure ad Connect](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="06b27-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Captura de tela da página Adicionar novos usuários no assistente](media/addnewuserspage.png)

1. <span data-ttu-id="06b27-p106">Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você verá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.</span><span class="sxs-lookup"><span data-stu-id="06b27-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="06b27-153">Depois de adicionar os usuários, você também terá uma opção para compartilhar credenciais com os novos usuários que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="06b27-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="06b27-154">Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="06b27-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="06b27-155">Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**.</span><span class="sxs-lookup"><span data-stu-id="06b27-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="06b27-156">Se você estiver migrando de outro provedor de email e deseja copiar os dados mais tarde, poderá [migrar emails e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="06b27-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="06b27-157">Adicionar usuários usando o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="06b27-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="06b27-158">Se você tiver um controlador de domínio local com o Active Directory, sincronize seus usuários com o Microsoft 365 Business usando o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="06b27-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="06b27-159">Conclua isso antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="06b27-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="06b27-160">Você pode baixá-lo no centro de administração:</span><span class="sxs-lookup"><span data-stu-id="06b27-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="06b27-161">Vá para usuários **ativos**do **usuário** \> , selecione as reticências na parte superior da página e, em seguida, selecione **sincronização de diretório** para baixar o Azure ad Connect.</span><span class="sxs-lookup"><span data-stu-id="06b27-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![Na página usuários ativos, selecione reticências > Directory snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="06b27-163">Se você criar usuários dessa forma, ainda terá que atribuir licenças a eles no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="06b27-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="06b27-164">Continuar a acessar aplicativos e dispositivos associados ao domínio</span><span class="sxs-lookup"><span data-stu-id="06b27-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="06b27-165">Se você quiser continuar a acessar os aplicativos e dispositivos associados ao domínio, leia os seguintes artigos para duas maneiras diferentes de habilitar esse:</span><span class="sxs-lookup"><span data-stu-id="06b27-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="06b27-166">Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="06b27-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="06b27-167">Essa é a maneira recomendada.</span><span class="sxs-lookup"><span data-stu-id="06b27-167">This is the recommended way.</span></span>

- [<span data-ttu-id="06b27-168">Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="06b27-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="06b27-169">Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="06b27-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="06b27-170">Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect para configurar usuários, esta etapa não será exibida.</span><span class="sxs-lookup"><span data-stu-id="06b27-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="06b27-171">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="06b27-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="06b27-172">O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="06b27-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="06b27-173">Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="06b27-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="06b27-174">Se você tiver registros DNS existentes, por exemplo, um site existente, será necessário gerenciar seus próprios registros DNS para garantir que os serviços existentes permaneçam conectados.</span><span class="sxs-lookup"><span data-stu-id="06b27-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="06b27-175">Confira [noções básicas sobre domínios](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="06b27-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Conectar sua página de domínio com gerenciar meus próprios registros DNS.](media/connectyourdomainpage.png)

2. <span data-ttu-id="06b27-177">Siga as etapas do assistente e email e outros serviços serão configurados para você.</span><span class="sxs-lookup"><span data-stu-id="06b27-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="06b27-178">Configurar políticas de segurança e configurações de dispositivos</span><span class="sxs-lookup"><span data-stu-id="06b27-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="06b27-179">Essas políticas se aplicam a todos os usuários aos quais você fornece uma licença ou a um grupo de usuários se você decidir atribuir políticas diferentes a um conjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="06b27-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="06b27-180">Configurar políticas no assistente</span><span class="sxs-lookup"><span data-stu-id="06b27-180">Set up policies in the wizard</span></span>

<span data-ttu-id="06b27-181">As políticas configuradas no assistente são aplicadas automaticamente a um [grupo de segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *todos os usuários*.</span><span class="sxs-lookup"><span data-stu-id="06b27-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="06b27-182">Na lista **proteger seus arquivos de trabalho em dispositivos móveis** , a opção **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** será selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="06b27-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="06b27-183">Você pode ativar a opção **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e isso é recomendável.</span><span class="sxs-lookup"><span data-stu-id="06b27-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Captura de tela da página proteger arquivos de trabalho em dispositivos móveis.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="06b27-185">Se você expandir **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados**, os [valores padrão](protect-work-files-on-lost-or-stolen-device.md) serão previamente selecionados:</span><span class="sxs-lookup"><span data-stu-id="06b27-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Captura de tela dos valores padrão para proteção de arquivos em dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="06b27-187">Se você selecionar **gerenciar como os usuários acessarão arquivos do Office em dispositivos móveis** e o expandirem, os [valores padrão](manage-user-access-on-mobile-devices.md) serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="06b27-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="06b27-188">Recomendamos aceitar os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="06b27-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="06b27-189">Você pode criar mais políticas após concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="06b27-189">You can create more policies after setup completes.</span></span>

        ![Captura de tela das configurações de proteção para arquivos do Office em dispositivos móveis.](media/useraccessonmobile.png)

2. <span data-ttu-id="06b27-191">A última etapa para proteger dados e dispositivos permite que você configure políticas para proteger dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="06b27-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="06b27-192">Essas configurações são aplicadas automaticamente quando o Windows 10 de um usuário se conecta à sua organização.</span><span class="sxs-lookup"><span data-stu-id="06b27-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="06b27-193">Você pode expandir **dispositivos Windows 10 seguros** para ver e modificar os [valores padrão](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="06b27-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="06b27-194">Você também pode optar por [instalar automaticamente o Office](install-office-on-windows-10-during-setup.md) em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="06b27-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Captura de tela da página definir configuração de dispositivo do Windows 10.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="06b27-196">Modificar ou adicionar políticas no centro de administração</span><span class="sxs-lookup"><span data-stu-id="06b27-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="06b27-197">Consulte [Manage Microsoft 365 Business](manage.md) para links para tópicos sobre como exibir e modificar políticas de proteção de dispositivos e aplicativos, e como remover dados de ou redefinir dispositivos de usuário.</span><span class="sxs-lookup"><span data-stu-id="06b27-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="06b27-198">Implantar e gerenciar o Windows 10</span><span class="sxs-lookup"><span data-stu-id="06b27-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="06b27-199">Confira [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para se conectar manualmente ao Azure AD, seja durante a configuração de novos computadores ou alterando o perfil de logon para computadores existentes.</span><span class="sxs-lookup"><span data-stu-id="06b27-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="06b27-200">Usar o piloto automático para configurar novos dispositivos</span><span class="sxs-lookup"><span data-stu-id="06b27-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="06b27-201">Você pode usar o [Windows AutoPilot](add-autopilot-devices-and-profile.md) para configurar automaticamente **novos** dispositivos Windows 10 para um usuário, mas pode ser mais fácil obter um [parceiro](https://www.microsoft.com/solution-providers/search) que pode fazer isso para você.</span><span class="sxs-lookup"><span data-stu-id="06b27-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="06b27-202">Você também pode ir para a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) e solicitar que um especialista em tecnologia de nuvem configure novos dispositivos que você comprou para você.</span><span class="sxs-lookup"><span data-stu-id="06b27-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="06b27-203">Acessar recursos locais</span><span class="sxs-lookup"><span data-stu-id="06b27-203">Access on-premises resources</span></span>

<span data-ttu-id="06b27-204">Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="06b27-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="06b27-205">Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pela Microsoft 365 Business](manage-windows-devices.md) para configurar isso.</span><span class="sxs-lookup"><span data-stu-id="06b27-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="06b27-206">Este é o método preferencial e os dispositivos nesse estado são chamados de dispositivos do Azure AD associados híbridos.</span><span class="sxs-lookup"><span data-stu-id="06b27-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="06b27-207">Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamento de arquivos e impressoras), você poderá dar aos seus dispositivos associados ao AD do Azure acesso a esses recursos seguindo as etapas aqui: [acessar recursos locais de um Dispositivo ingressado no AD do Azure no Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="06b27-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="06b27-208">Implantar aplicativos cliente do Office 365</span><span class="sxs-lookup"><span data-stu-id="06b27-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="06b27-209">Se você optar por instalar automaticamente os aplicativos do Office no durante a configuração, os aplicativos serão instalados nos dispositivos Windows 10 depois que eles entrarem no Azure AD de seus dispositivos Windows com suas credenciais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="06b27-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="06b27-210">Para instalar o Office no Mobile iOS ou dispositivos Android, consulte [set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="06b27-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="06b27-211">Você também pode instalar o Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="06b27-211">You can also install Office individually.</span></span> <span data-ttu-id="06b27-212">Confira [instalar o Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="06b27-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="06b27-213">Configurações de segurança adicionais</span><span class="sxs-lookup"><span data-stu-id="06b27-213">Additional security settings</span></span>

<span data-ttu-id="06b27-214">Além da configuração de segurança e conformidade no assistente de instalação, você também pode definir as seguintes configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="06b27-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="06b27-215">**Proteção contra malware de email**</span><span class="sxs-lookup"><span data-stu-id="06b27-215">**Email malware protection**</span></span>
- <span data-ttu-id="06b27-216">**Anexos seguros de proteção avançada contra ameaças (ATP)**</span><span class="sxs-lookup"><span data-stu-id="06b27-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="06b27-217">**Links seguros da ATP**</span><span class="sxs-lookup"><span data-stu-id="06b27-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="06b27-218">**Anti-phishing da APT**</span><span class="sxs-lookup"><span data-stu-id="06b27-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="06b27-219">**Arquivamento do Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="06b27-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="06b27-220">**Prevenção de perda de dados (DLP)**</span><span class="sxs-lookup"><span data-stu-id="06b27-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="06b27-221">**Proteção de informações do Azure** (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="06b27-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="06b27-222">**Disponibilidade do portal do Intune**</span><span class="sxs-lookup"><span data-stu-id="06b27-222">**Intune portal availability**</span></span>

<span data-ttu-id="06b27-223">Para começar, veja [Configurar políticas avançadas de segurança](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="06b27-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="06b27-224">Confira também [as 10 maneiras principais de proteger o Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para um mapa de práticas recomendadas de segurança.</span><span class="sxs-lookup"><span data-stu-id="06b27-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>