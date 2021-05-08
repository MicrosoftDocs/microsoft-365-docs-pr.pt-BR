---
title: Configurar o Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Saiba como configurar sua assinatura do Microsoft 365 Business Standard.
ms.openlocfilehash: ce45b4869000892b5640730e765dbfc9c21386ed
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244450"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="1ebc2-103">Configurar o Microsoft Business Standard</span><span class="sxs-lookup"><span data-stu-id="1ebc2-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="1ebc2-104">Adicione seu domínio para personalizar o login</span><span class="sxs-lookup"><span data-stu-id="1ebc2-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="1ebc2-105">Ao comprar o Microsoft 365 Business Standard, você tem a opção de usar um domínio que possui ou comprar um durante a inscrição.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="1ebc2-106">Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="1ebc2-107">Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="1ebc2-108">Clique em **Ir para a Configuração** pra iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="1ebc2-109">Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="1ebc2-110">Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1ebc2-111">Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="1ebc2-112">Em vez disso, acesse [Adicionar usuários](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-112">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="1ebc2-113">Siga as etapas no assistente para [Criar registros DNS em qualquer provedor de hospedagem DNS do Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifique se você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="1ebc2-114">Se você conhece o host do seu domínio, também consulte as [instruções específicas do organizador](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-114">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="1ebc2-115">Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="1ebc2-117">Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="1ebc2-117">Add users and assign licenses</span></span>

<span data-ttu-id="1ebc2-118">Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../add-users/add-users.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="1ebc2-119">Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="1ebc2-120">Adicionar usuários ao assistente</span><span class="sxs-lookup"><span data-stu-id="1ebc2-120">Add users in the wizard</span></span>

<span data-ttu-id="1ebc2-121">Todos os usuários que você adicionar no assistente recebem automaticamente uma licença do Microsoft 365 Business Standard.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="1ebc2-p104">Se sua assinatura do Microsoft 365 Business Standard tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você obterá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="1ebc2-p105">Depois de adicionar os usuários, você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="1ebc2-126">Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="1ebc2-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="1ebc2-127">Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="1ebc2-128">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="1ebc2-129">O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="1ebc2-130">Caso contrário, [Alterar os servidores de nomes para configurar o Office 365 com qualquer registrador de domínio](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="1ebc2-131">Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="1ebc2-132">Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="1ebc2-133">Se você possui registros DNS existentes com outros organizadores DNS (não habilitados para conexão ao domínio), convém gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-133">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="1ebc2-134">Consulte [noções básicas de domínio](/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-134">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="1ebc2-135">Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="1ebc2-136">Quando o processo de inscrição for concluído, você será direcionado para o centro de administração, onde acompanhará um assistente para instalar os aplicativos do Office, adicionar seu domínio, adicionar usuários e atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="1ebc2-137">Depois de concluir a configuração inicial, você poderá usar a página de **configuração** no centro de administração para continuar a instalar e configurar os serviços que vêm com as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="1ebc2-138">Para obter mais informações sobre o assistente de configuração e a página de **instalação** do centro de administração, confira [Diferença entre o assistente de configuração e a página de configuração](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="1ebc2-139">Concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="1ebc2-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="1ebc2-140">Configurar o Outlook para e-mail</span><span class="sxs-lookup"><span data-stu-id="1ebc2-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="1ebc2-141">No menu Iniciar do Windows, procure Outlook e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="1ebc2-142">(Se estiver usando um Mac, abra o Outlook na barra de ferramentas ou localize-o usando o Finder).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="1ebc2-143">Se você tiver acabado de instalar o Outlook, na página inicial, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="1ebc2-144">Escolha **Arquivo** \>**Informações**\>**Adicionar Conta**.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="1ebc2-145">Digite seu endereço de e-mail do Microsoft e selecione **conectar**.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-145">Enter your Microsoft email address and select **Connect**.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="1ebc2-146">Veja mais em [Configurar o Outlook para email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-146">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="1ebc2-147">Importar e-mail</span><span class="sxs-lookup"><span data-stu-id="1ebc2-147">Import email</span></span>

<span data-ttu-id="1ebc2-148">Se você estava usando o Outlook com outra conta de email, poderá importar seus emails, calendário e contatos antigos para sua nova conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-148">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="1ebc2-149">**Exportar seus emails antigos**</span><span class="sxs-lookup"><span data-stu-id="1ebc2-149">**Export your old email**</span></span>

    <span data-ttu-id="1ebc2-150">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-150">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="1ebc2-151">Selecione **Exportar para um Arquivo** e siga as etapas para exportar o Arquivo de Dados do Outlook (.pst) e quaisquer subpastas.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-151">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="1ebc2-152">**Importar seus emails antigos**</span><span class="sxs-lookup"><span data-stu-id="1ebc2-152">**Import your old email**</span></span>

    <span data-ttu-id="1ebc2-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="1ebc2-154">Desta vez, selecione **Importar de outro programa ou arquivo** e siga as etapas para importar o arquivo de backup criado ao exportar os emails antigos.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-154">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="1ebc2-155">Veja mais em [Importar emails com o Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-155">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="1ebc2-156">Você também pode usar o centro de administração do Exchange para importar e-mails de todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-156">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="1ebc2-157">Para obter mais informações, consulte [migrar várias contas de e-mail](/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-157">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="1ebc2-158">Usar um site público</span><span class="sxs-lookup"><span data-stu-id="1ebc2-158">Use a public website</span></span>

<span data-ttu-id="1ebc2-p111">O Microsoft 365 não inclui um site público para a sua empresa. Se quiser configurar um, considere usar um parceiro da Microsoft, como o GoDaddy ou o WIX.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-p111">Microsoft 365 doesn't include a public website for your business. If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="1ebc2-161">No Centro de Administração, vá para **Recursos** e selecione **Site público**.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-161">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="1ebc2-162">Selecione **Saiba mais** em uma das opções e depois inscreva-se com um parceiro de site e use as ferramentas dele para configurar e projetar seu site.</span><span class="sxs-lookup"><span data-stu-id="1ebc2-162">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

<span data-ttu-id="1ebc2-163">Veja mais em [Usar um site público](../../business-video/create-web-site.md).</span><span class="sxs-lookup"><span data-stu-id="1ebc2-163">More at [Use a public website](../../business-video/create-web-site.md).</span></span>