---
title: Configurar o Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: cd59570cbcb9b027780e160117b44be88770d6b9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575539"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="ffde3-103">Configurar o Microsoft 365 Business no assistente de instalação</span><span class="sxs-lookup"><span data-stu-id="ffde3-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="ffde3-104">Adicionar o domínio, os usuários e as políticas de configuração</span><span class="sxs-lookup"><span data-stu-id="ffde3-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="ffde3-105">[![Rótulo para permitir que o centro de administração esteja mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="ffde3-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="ffde3-106">Ao comprar o Microsoft 365 Business, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [inscrição](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="ffde3-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="ffde3-107">Se você comprou um novo domínio ao se inscrever, seu domínio está configurado e você pode mover para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="ffde3-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="ffde3-108">Adicionar seu domínio para personalizar a entrada</span><span class="sxs-lookup"><span data-stu-id="ffde3-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="ffde3-109">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="ffde3-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="ffde3-110">Escolha **Adicionar um domínio** ou **Adicionar usuários** para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="ffde3-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="ffde3-111">Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** .</span><span class="sxs-lookup"><span data-stu-id="ffde3-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="ffde3-112">Em vez disso, vá para [Adicionar usuários](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="ffde3-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Selecione ir para a configuração.](media/gotosetupinadmincenter.png)
    
3. <span data-ttu-id="ffde3-114">No assistente, digite o nome de domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ffde3-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Captura de tela da página personalizar sua sessão de entrada.](media/personalizesignin.png)

    
4. <span data-ttu-id="ffde3-116">Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ffde3-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="ffde3-117">Se você souber seu host de domínio, consulte também as [instruções específicas do host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="ffde3-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="ffde3-118">Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com o [domínio Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e você será solicitado a entrar novamente e permitir que a Microsoft autentique em seu nome:</span><span class="sxs-lookup"><span data-stu-id="ffde3-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Na página Confirmar acesso do GoDaddy, selecione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="ffde3-120">Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="ffde3-120">Add users and assign licenses</span></span>

<span data-ttu-id="ffde3-121">Você pode adicionar usuários no assistente, mas você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="ffde3-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="ffde3-122">Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="ffde3-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="ffde3-123">Adicionar usuários no assistente</span><span class="sxs-lookup"><span data-stu-id="ffde3-123">Add users in the wizard</span></span>

<span data-ttu-id="ffde3-124">Todos os usuários adicionados ao assistente recebem automaticamente uma licença de negócios do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffde3-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Captura de tela da página Adicionar novos usuários no assistente](media/addnewuserspage.png)

1. <span data-ttu-id="ffde3-126">Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá uma opção para atribuir licenças a eles agora.</span><span class="sxs-lookup"><span data-stu-id="ffde3-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="ffde3-127">Adicione licenças para eles também.</span><span class="sxs-lookup"><span data-stu-id="ffde3-127">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="ffde3-128">Depois de adicionar os usuários, você também terá uma opção para compartilhar credenciais com os novos usuários que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="ffde3-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="ffde3-129">Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="ffde3-129">You can choose to print them out, email them, or download them.</span></span>

3. <span data-ttu-id="ffde3-130">Na criação de equipes para sua organização, você pode optar por adicionar equipes e adicionar usuários a elas.</span><span class="sxs-lookup"><span data-stu-id="ffde3-130">On the Create Teams for your organization, you can choose to add Teams and add users to them.</span></span> <span data-ttu-id="ffde3-131">Você também pode fazer isso mais tarde.</span><span class="sxs-lookup"><span data-stu-id="ffde3-131">You can also do this later.</span></span> <span data-ttu-id="ffde3-132">Para obter mais informações, consulte [criar uma equipe para toda a empresa](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span><span class="sxs-lookup"><span data-stu-id="ffde3-132">For more information, see [create a company-wide Team](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>

4. <span data-ttu-id="ffde3-133">Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**.</span><span class="sxs-lookup"><span data-stu-id="ffde3-133">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="ffde3-134">Se você estiver migrando de outro provedor de email e deseja copiar os dados mais tarde, poderá [migrar emails e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="ffde3-134">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="ffde3-135">Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="ffde3-135">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="ffde3-136">Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect para configurar usuários, esta etapa não será exibida.</span><span class="sxs-lookup"><span data-stu-id="ffde3-136">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="ffde3-137">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="ffde3-137">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="ffde3-138">O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="ffde3-138">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="ffde3-139">Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="ffde3-139">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="ffde3-140">Se você tiver registros DNS existentes, por exemplo, um site existente, mas seu host DNS estiver habilitado para [conexão de domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), escolha **adicionar registros para mim**.</span><span class="sxs-lookup"><span data-stu-id="ffde3-140">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="ffde3-141">Na página **escolha seus serviços online** , aceite todos os padrões e escolha **Avançar**e escolha **autorizar** na página do seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="ffde3-141">On the **Choose your online services** page, accept all the defaults, and choose **Next**,and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="ffde3-142">Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), será necessário gerenciar seus próprios registros DNS para garantir que os serviços existentes permaneçam conectados.</span><span class="sxs-lookup"><span data-stu-id="ffde3-142">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="ffde3-143">Confira [noções básicas sobre domínios](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ffde3-143">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Conectar sua página de domínio com gerenciar meus próprios registros DNS.](media/connectyourdomainpage.png)

2. <span data-ttu-id="ffde3-145">Siga as etapas do assistente e email e outros serviços serão configurados para você.</span><span class="sxs-lookup"><span data-stu-id="ffde3-145">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-data-and-devices"></a><span data-ttu-id="ffde3-146">Proteger dados e dispositivos</span><span class="sxs-lookup"><span data-stu-id="ffde3-146">Protect data and devices</span></span> 

<span data-ttu-id="ffde3-147">As políticas configuradas no assistente são aplicadas automaticamente a um [grupo de segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *todos os usuários*.</span><span class="sxs-lookup"><span data-stu-id="ffde3-147">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="ffde3-148">Você também pode criar grupos adicionais para atribuir políticas ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="ffde3-148">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="ffde3-149">Na lista **proteger seus arquivos de trabalho em dispositivos móveis** , a opção **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** será selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="ffde3-149">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="ffde3-150">Você pode ativar a opção **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e isso é recomendável.</span><span class="sxs-lookup"><span data-stu-id="ffde3-150">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Captura de tela da página proteger arquivos de trabalho em dispositivos móveis.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="ffde3-152">Expanda **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** para exibir os [valores padrão](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="ffde3-152">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Captura de tela dos valores padrão para proteção de arquivos em dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="ffde3-154">Selecione **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e expanda-o para exibir os [valores padrão](manage-user-access-on-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ffde3-154">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="ffde3-155">Recomendamos que você aceite os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="ffde3-155">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="ffde3-156">Você pode criar mais políticas após concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="ffde3-156">You can create more policies after setup completes.</span></span>

        ![Captura de tela das configurações de proteção para arquivos do Office em dispositivos móveis.](media/useraccessonmobile.png)

2. <span data-ttu-id="ffde3-158">A última etapa para proteger dados e dispositivos permite que você configure políticas para proteger dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ffde3-158">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="ffde3-159">Essas configurações são aplicadas automaticamente quando o Windows 10 de um usuário se conecta à sua organização.</span><span class="sxs-lookup"><span data-stu-id="ffde3-159">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="ffde3-160">Você pode expandir **dispositivos Windows 10 seguros** para ver e modificar os [valores padrão](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ffde3-160">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="ffde3-161">Você também pode optar por [instalar automaticamente o Office](install-office-on-windows-10-during-setup.md) em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ffde3-161">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Captura de tela da página definir configuração de dispositivo do Windows 10.](media/setwin10config.png)


## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="ffde3-163">Implantar aplicativos cliente do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffde3-163">Deploy Office 365 client apps</span></span>

<span data-ttu-id="ffde3-164">Se você optar por instalar automaticamente os aplicativos do Office no durante a configuração, os aplicativos serão instalados nos dispositivos Windows 10 depois que eles entrarem no Azure AD de seus dispositivos Windows com suas credenciais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ffde3-164">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="ffde3-165">Para instalar o Office no Mobile iOS ou dispositivos Android, consulte [set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ffde3-165">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="ffde3-166">Você também pode instalar o Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="ffde3-166">You can also install Office individually.</span></span> <span data-ttu-id="ffde3-167">Confira [instalar o Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ffde3-167">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
