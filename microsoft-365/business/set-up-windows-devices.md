---
title: Configurar dispositivos Windows para usuários do Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Saiba como configurar dispositivos do Windows que executam o Windows 10 pro para usuários do Microsoft 365 Business. '
ms.openlocfilehash: c4edd09d952ed1c98be8f41f6bcbaff8a16319a7
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288466"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="537bf-103">Configurar dispositivos Windows para usuários do Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="537bf-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="537bf-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="537bf-104">Prerequisites</span></span>

<span data-ttu-id="537bf-p101">Antes de configurar dispositivos Windows para usuários do Microsoft 365 Business, verifique se todos os dispositivos Windows estão executando o Windows 10 Pro, versão 1703 (Atualização para Criadores). O Windows 10 Pro é um pré-requisito para a implantação do Windows 10 Business, que é um conjunto de serviços de nuvem e recursos de gerenciamento de dispositivos que complementam o Windows 10 Pro e permitem o gerenciamento centralizado e os controles de segurança do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="537bf-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="537bf-107">Se você tiver dispositivos Windows executando o Windows 7 Pro, Windows 8 Pro ou Windows 8.1 Pro, sua assinatura do Microsoft Business 365 dará direito a uma atualização do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="537bf-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="537bf-108">Para obter mais informações sobre como atualizar dispositivos Windows para a Atualização do Windows 10 Pro para Criadores, siga as etapas deste tópico: [Atualize dispositivos Windows para a Atualização do Windows Pro para Criadores](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="537bf-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="537bf-109">Confira [verificar se o dispositivo está conectado ao Azure ad](#verify-the-device-is-connected-to-azure-ad) para verificar se você tem a atualização ou se a atualização funcionou.</span><span class="sxs-lookup"><span data-stu-id="537bf-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span> 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="537bf-110">Ingressar dispositivos Windows 10 ao Azure AD de sua organização</span><span class="sxs-lookup"><span data-stu-id="537bf-110">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="537bf-p102">Depois que todos os dispositivos Windows de sua organização terem sido atualizados para a Atualização do Windows 10 Pro para Criadores ou já estiverem executando a Atualização do Windows 10 Pro para Criadores, você poderá ingressar esses dispositivos em sua organização do Azure Active Directory. Depois que os dispositivos são ingressados, eles serão automaticamente atualizados para o Windows 10 Business, que faz parte de sua assinatura do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="537bf-p102">Once all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory. Once the devices are joined, they will automatically be upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="537bf-113">No caso de um dispositivo Windows 10 Pro novo ou atualizado recentemente</span><span class="sxs-lookup"><span data-stu-id="537bf-113">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="537bf-114">No caso de um novo dispositivo que executa a Atualização do Windows 10 Pro para Criadores ou um dispositivo que foi atualizado para a Atualização do Windows 10 Pro para Criadores, mas não passou pela configuração do dispositivo Windows 10, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="537bf-114">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="537bf-115">Execute a configuração do dispositivo Windows 10 até chegar à página **Como você deseja configurar?**.</span><span class="sxs-lookup"><span data-stu-id="537bf-115">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="537bf-117">Aqui, escolha **Configuração para uma organização** e, em seguida, insira seu nome de usuário e senha do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="537bf-117">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="537bf-118">Conclua a configuração do dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="537bf-118">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="537bf-p103">Quando terminar, o usuário será conectado ao Azure AD de sua organização. Para garantir a conexão, confira [Verifique se o dispositivo está conectado ao Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="537bf-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="537bf-121">Para um dispositivo já configurado executando o Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="537bf-121">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="537bf-122">**Conecte os usuários ao Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="537bf-122">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="537bf-123">No PC Windows do usuário, que esteja executando o Windows 10 Pro, versão 1703 (Atualização do Criador) (veja os [pré-requisitos](pre-requisites-for-data-protection.md)), clique no logotipo do Windows e, em seguida, no ícone de Configurações.</span><span class="sxs-lookup"><span data-stu-id="537bf-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="537bf-125">Em **Configurações**, vá para **Contas**.</span><span class="sxs-lookup"><span data-stu-id="537bf-125">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="537bf-127">Na página **Suas informações**, clique em **Acessar trabalho ou escola** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="537bf-127">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="537bf-129">Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, em **Ações alternativas**, escolha **Ingressar este dispositivo no Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="537bf-129">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="537bf-131">Na página de **login**, insira sua conta corporativa ou de estudante \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="537bf-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="537bf-132">Na página **Insira sua senha**, insira a senha \> **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="537bf-132">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="537bf-134">Na página **Verifique se esta é sua organização** , verifique se as informações estão corretas e clique em **ingressar**.</span><span class="sxs-lookup"><span data-stu-id="537bf-134">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="537bf-p104">Na página **Tudo pronto!**, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="537bf-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="537bf-p105">Se você carregou arquivos no OneDrive for Business, sincronize-os novamente. Se você usou uma ferramenta de terceiros para migrar o perfil e arquivos, sincronize-os também com o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="537bf-p105">If you uploaded files to OneDrive for Business, sync them back down. If you used a third party tool to migrate profile and files, sync those also to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="537bf-140">Verifique se o dispositivo está conectado ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="537bf-140">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="537bf-p106">Para verificar seu status de sincronização, na página **Acessar trabalho ou escola**, em **Configurações**, clique na área **Conectado a** _ \<organization name\> _ para expor os botões **Informações** e **Desconectar**. Clique em **Informações** para obter o status da sincronização.</span><span class="sxs-lookup"><span data-stu-id="537bf-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="537bf-143">Na página de status de sincronização, clique em Sincronização para obter as últimas políticas de gerenciamento de dispositivo móvel no PC.</span><span class="sxs-lookup"><span data-stu-id="537bf-143">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="537bf-p107">Para começar a usar a conta do Microsoft 365 Business, vá para o botão **Iniciar** do Windows, clique com botão direito na imagem da conta atual e, em seguida, clique em **Trocar conta**. Entre com o email e a senha da sua organização.</span><span class="sxs-lookup"><span data-stu-id="537bf-p107">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture and then **Switch account**. Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="537bf-147">Verifique se o dispositivo está atualizado para o Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="537bf-147">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="537bf-148">Verifique se seu Azure AD ingressado em dispositivos Windows 10 foram atualizados para o Windows 10 Business como parte de sua assinatura do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="537bf-148">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="537bf-149">Vá para **Configurações** \> **Sistema** \> **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="537bf-149">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="537bf-150">Confirme se a opção **Edição** exibe **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="537bf-150">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="537bf-152">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="537bf-152">Next steps</span></span>

<span data-ttu-id="537bf-153">Para configurar seus dispositivos móveis, confira [Configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md). Para definir políticas de proteção de dispositivos ou proteção de aplicativos, confira [Gerenciar o Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="537bf-153">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
