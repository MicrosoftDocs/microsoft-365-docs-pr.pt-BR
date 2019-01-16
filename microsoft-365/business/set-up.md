---
title: Configurar o Microsoft 365 Business usando o assistente de configuração
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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Saiba como configurar o Microsoft 365 Business ao concluir as quatro etapas.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864685"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="14f1a-103">Configurar o Microsoft 365 Business usando o assistente de configuração</span><span class="sxs-lookup"><span data-stu-id="14f1a-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="14f1a-104">Conclua as etapas 1-4 abaixo.</span><span class="sxs-lookup"><span data-stu-id="14f1a-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="14f1a-105">Configurar o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="14f1a-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="14f1a-106">Assista a um vídeo sobre como configurar o Microsoft 365 Business quando não há um Active Directory no local:</span><span class="sxs-lookup"><span data-stu-id="14f1a-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="14f1a-p101">As etapas de configuração incluem informações de configurações que incluem o Active Directory local. Se você deseja continuar a acessar dispositivos associados a um domínio, leia os seguintes artigos para duas de maneira diferente da habilitação que e conclua as etapas antes de executar o Assistente de instalação:</span><span class="sxs-lookup"><span data-stu-id="14f1a-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="14f1a-109">Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="14f1a-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="14f1a-110">-Essa é a maneira recomendada.</span><span class="sxs-lookup"><span data-stu-id="14f1a-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="14f1a-111">Acesso a recursos de um dispositivo associado ao AD Azure no Microsoft 365 Business local</span><span class="sxs-lookup"><span data-stu-id="14f1a-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="14f1a-112">Etapa 1: Personalizar entrar</span><span class="sxs-lookup"><span data-stu-id="14f1a-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="14f1a-p102">Acesse o [Microsoft 365 Business](https://portal.microsoft.com) usando suas credenciais de administrador global. Escolha o bloco **Administrador** para ir para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="14f1a-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="14f1a-115">Escolha **Iniciar a instalação** (dependendo do seu estado, você poderá ver **Continuar instalação**) no centro de administração para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="14f1a-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="14f1a-116">Insira o nome do domínio que você deseja usar (como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="14f1a-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="14f1a-p103">Vá em frente e insira seu domínio, mesmo se você verificou durante a utilização de conectar do Azure AD, por exemplo. As duas etapas a seguintes não se aplicam a você se você usou Connect do Azure AD para verificar seu domínio.</span><span class="sxs-lookup"><span data-stu-id="14f1a-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="14f1a-119">Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de hospedagem de DNS para o Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) verifica que você é proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="14f1a-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="14f1a-p104">Você pode exibir um vídeo de exemplo da [vídeo: instalação do Office 365 no Centro de administração do novo](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Observe que este vídeo não inclui as etapas de proteção de dados do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="14f1a-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="14f1a-123">Etapa 2: Adicionar usuários e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="14f1a-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="14f1a-124">Você pode adicionar usuários aqui ou [adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="14f1a-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="14f1a-125">Os usuários que você adiciona automaticamente recebem uma licença do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="14f1a-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="14f1a-p105">Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você verá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.</span><span class="sxs-lookup"><span data-stu-id="14f1a-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="14f1a-p106">Você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.</span><span class="sxs-lookup"><span data-stu-id="14f1a-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="14f1a-130">Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**.</span><span class="sxs-lookup"><span data-stu-id="14f1a-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="14f1a-131">Se você estiver movendo de outro provedor de email e deseja copiar os dados mais tarde, você pode [migrar email e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="14f1a-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="14f1a-133">Etapa 3: Conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="14f1a-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="14f1a-134">Se você optar por usar o domínio .onmicrosoft ou usado Connect do Azure AD, você não verá esta etapa.</span><span class="sxs-lookup"><span data-stu-id="14f1a-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="14f1a-135">Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.</span><span class="sxs-lookup"><span data-stu-id="14f1a-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="14f1a-p107">Normalmente, o Assistente de instalação detecta seu registrador e fornece um link para instruções passo a passo para atualizar seus registros NS no website da registrador. Caso contrário, [nameservers de alteração para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="14f1a-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="14f1a-138">O email e outros serviços serão configurados para você</span><span class="sxs-lookup"><span data-stu-id="14f1a-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="14f1a-139">Etapa 4: Gerenciar dispositivos e arquivos de trabalho</span><span class="sxs-lookup"><span data-stu-id="14f1a-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="14f1a-p108">Nos **arquivos de trabalho Protect em seus dispositivos móveis** página Definir as configurações de **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e **proteger arquivos de trabalho quando dispositivos são perdidos ou roubados** para **ativado**. Você também pode acessar cada definição sub-recursos clicando nas divisas ao lado de cada configuração.</span><span class="sxs-lookup"><span data-stu-id="14f1a-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="14f1a-142">Todos os arquivos de trabalho dos usuários licenciados agora estão protegidos em iOS e dispositivos com Android, assim que eles [instalar aplicativos do Office](set-up-mobile-devices.md) (e autenticar com suas credenciais do Microsoft 365 Business).</span><span class="sxs-lookup"><span data-stu-id="14f1a-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="14f1a-144">Na página **configuração de dispositivo definir Windows 10** , defina a configuração de **Dispositivos do Windows 10 seguro** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="14f1a-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="14f1a-145">Você também pode acessar cada definição sub-recursos clicando na divisa ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="14f1a-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="14f1a-p109">Defina a configuração de **Instalar o Office em dispositivos do Windows 10** como **Sim** se todos os usuários tiverem computadores Windows 10, e instala o Office não existente, ou instalações do Office click-to-run. Se isso não for o caso, defina essa opção como **não**. Você pode [instalar o Office automaticamente](auto-install-or-uninstall-office.md) posterior a partir do Centro de administração após ter preparado os computadores do usuário. Para obter instruções, consulte [preparar para instalação de cliente do Office](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="14f1a-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="14f1a-150">Arquivos de trabalho dos usuários licenciados em dispositivos Windows 10 serão projetados assim que eles [ingressar em seus dispositivos Windows 10](set-up-windows-devices.md) a um domínio do Microsoft 365 Business Azure AD ou a [instalar o Windows 10 em um novo computador](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) ao ingressar simultaneamente o 365 da Microsoft Domínio do Azure AD de negócios.</span><span class="sxs-lookup"><span data-stu-id="14f1a-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="14f1a-151">Clique em **Avançar** e a instalação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="14f1a-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="14f1a-152">Envie-nos comentários nesta etapa para nos ajudar a melhorar a experiência.</span><span class="sxs-lookup"><span data-stu-id="14f1a-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="14f1a-154">Configurações de segurança adicionais</span><span class="sxs-lookup"><span data-stu-id="14f1a-154">Additional security settings</span></span>

<span data-ttu-id="14f1a-155">Além da segurança e configuração de conformidade no Assistente de instalação, você também pode configurar as seguintes configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="14f1a-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="14f1a-p110">Configure a proteção contra anexos não seguros. **Proteção de ameaça avançada** (ATP) identifica o conteúdo mal-intencionado e, em seguida, bloqueia a entrega de anexos não seguros, ajudando a protegê-lo contra os esquemas de phishing e ransomware infecções. Para ativar a proteção de anexo, consulte [Configurar políticas de anexos do Office 365 ATP seguros](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="14f1a-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="14f1a-p111">Protege o ambiente quando usuários clicarem em links mal-intencionado. ATP examina links no email no momento em que um usuário clica neles. Se não for um link não seguro, o usuário é advertido não a visitar o site ou informado que o site foi bloqueado. Isso ajuda a proteger contra esquemas de phishing. [Configurar políticas de vínculos do Office 365 ATP seguros](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) ou [Configurar políticas de vínculos do Office 365 ATP seguros](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="14f1a-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="14f1a-p112">Você pode preservar todo o conteúdo da caixa de correio incluindo itens excluídos colocando-se a caixa de correio inteira do usuário na **retenção de litígio**. Para obter instruções, consulte</span><span class="sxs-lookup"><span data-stu-id="14f1a-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="14f1a-166">[Configurar a retenção de email com o arquivamento do Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="14f1a-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="14f1a-p113">Configure **políticas de retenção**de personalizada, por exemplo, para preservar por um período específico ou excluir o conteúdo permanentemente no final do período de retenção. Você pode habilitar diretivas de retenção personalizada no Centro de conformidade, vá até a **governança de dados** de títulos e \> **retenção**e, em seguida, siga as etapas no assistente. Para saber mais, consulte [Visão geral das políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="14f1a-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="14f1a-170">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="14f1a-170">Next steps</span></span>

<span data-ttu-id="14f1a-171">Para os usuários que têm licenças, a próxima etapa será configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14f1a-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="14f1a-172">Confira [Configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) e [Configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="14f1a-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="14f1a-173">Confira [Gerenciar o Microsoft 365 Business](manage.md) para links de tópicos sobre como configurar políticas de proteção de dispositivos e aplicativos e como remover dados de dispositivos de usuários.</span><span class="sxs-lookup"><span data-stu-id="14f1a-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


