---
title: Configurar Windows dispositivos para Microsoft 365 Business Premium usuários
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Saiba como configurar Windows dispositivos executando Windows 10 Pro para Microsoft 365 Business Premium usuários, habilitando controles de segurança e gerenciamento centralizados.
ms.openlocfilehash: 3e268d81ff6fb7113b7e0b0fe5d0545ff5c72b1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244767"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="bd239-103">Configurar Windows dispositivos para Microsoft 365 Business Premium usuários</span><span class="sxs-lookup"><span data-stu-id="bd239-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="bd239-104">Pré-requisitos para configurar dispositivos Windows para Microsoft 365 Business Premium usuários</span><span class="sxs-lookup"><span data-stu-id="bd239-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="bd239-105">Antes de configurar Windows para usuários Microsoft 365 Business Premium, certifique-se de que todos os dispositivos Windows estão executando Windows 10 Pro versão 1703 (Atualização de Criadores).</span><span class="sxs-lookup"><span data-stu-id="bd239-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="bd239-106">Windows 10 Pro é um pré-requisito para a implantação do Windows 10 Business, que é um conjunto de serviços de nuvem e recursos de gerenciamento de dispositivos que complementam o Windows 10 Pro e permitem o gerenciamento centralizado e os controles de segurança do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bd239-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="bd239-107">Se você tiver Windows dispositivos executando Windows 7 Pro, Windows 8 Pro ou Windows 8.1 Pro, Microsoft 365 Business Premium assinatura do Microsoft 365 Business Premium lhe dará direito a uma atualização Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bd239-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="bd239-108">Para obter mais informações sobre como atualizar dispositivos Windows para a Atualização do Windows 10 Pro para Criadores, siga as etapas deste tópico: [Atualize dispositivos Windows para a Atualização do Windows Pro para Criadores](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="bd239-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="bd239-109">Consulte [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span><span class="sxs-lookup"><span data-stu-id="bd239-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="bd239-110">Assista a um breve vídeo sobre como conectar Windows a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd239-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="bd239-111">Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="bd239-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="bd239-112">Ingressar dispositivos Windows 10 ao Azure AD de sua organização</span><span class="sxs-lookup"><span data-stu-id="bd239-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="bd239-113">Quando todos os Windows da sua organização foram atualizados para o Windows 10 Pro Creators Update ou já estão executando o Windows 10 Pro Creators Update, você pode ingressar esses dispositivos no Azure Active Directory da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd239-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="bd239-114">Depois que os dispositivos são ingressados, eles serão atualizados automaticamente para Windows 10 Business, que faz parte da sua assinatura Microsoft 365 Business Premium usuário.</span><span class="sxs-lookup"><span data-stu-id="bd239-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="bd239-115">No caso de um dispositivo Windows 10 Pro novo ou atualizado recentemente</span><span class="sxs-lookup"><span data-stu-id="bd239-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="bd239-116">No caso de um novo dispositivo que executa a Atualização do Windows 10 Pro para Criadores ou um dispositivo que foi atualizado para a Atualização do Windows 10 Pro para Criadores, mas não passou pela configuração do dispositivo Windows 10, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bd239-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="bd239-117">Execute a configuração do dispositivo Windows 10 até chegar à página **Como você deseja configurar?**.</span><span class="sxs-lookup"><span data-stu-id="bd239-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="bd239-119">Aqui, escolha **Configurar para uma organização** e insira seu nome de usuário e senha para Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bd239-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="bd239-120">Conclua a configuração do dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bd239-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="bd239-p103">Quando terminar, o usuário será conectado ao Azure AD de sua organização. Para garantir a conexão, confira [Verifique se o dispositivo está conectado ao Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="bd239-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="bd239-123">Para um dispositivo já configurado executando o Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="bd239-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="bd239-124">**Conecte os usuários ao Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="bd239-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="bd239-125">No PC Windows do usuário, que esteja executando o Windows 10 Pro, versão 1703 (Atualização do Criador) (veja os [pré-requisitos](pre-requisites-for-data-protection.md)), clique no logotipo do Windows e, em seguida, no ícone de Configurações.</span><span class="sxs-lookup"><span data-stu-id="bd239-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="bd239-127">Em **Configurações**, vá para **Contas**.</span><span class="sxs-lookup"><span data-stu-id="bd239-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="bd239-129">Na página **Suas informações**, clique em **Acessar trabalho ou escola** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bd239-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="bd239-131">Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, em **Ações alternativas**, escolha **Ingressar este dispositivo no Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="bd239-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="bd239-133">Na página de **login**, insira sua conta corporativa ou de estudante \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bd239-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="bd239-134">Na página **Insira sua senha**, insira a senha \> **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="bd239-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="bd239-136">Na página **Certifique-se de que essa é a sua organização,** verifique se as informações estão corretas e escolha **Ingressar**.</span><span class="sxs-lookup"><span data-stu-id="bd239-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="bd239-137">No **you're all set!**</span><span class="sxs-lookup"><span data-stu-id="bd239-137">On the **You're all set!**</span></span> <span data-ttu-id="bd239-138">page, chosse **Done**.</span><span class="sxs-lookup"><span data-stu-id="bd239-138">page, chosse **Done**.</span></span>
  
   ![Na tela Certifique-se de que essa é a sua organização, escolha Ingressar](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="bd239-140">Se você carregou arquivos no OneDrive for Business, sincronize-os novamente.</span><span class="sxs-lookup"><span data-stu-id="bd239-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="bd239-141">Se você usou uma ferramenta de terceiros para migrar perfis e arquivos, sincronize-os também com o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="bd239-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="bd239-142">Verifique se o dispositivo está conectado ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="bd239-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="bd239-143">Para verificar seu status de sincronização, na página Trabalho ou  Escola do **Access** no **Configurações**, selecione a área Conectado a _ _ para expor os botões \<organization name\> **Informações** e **Desconectar.**</span><span class="sxs-lookup"><span data-stu-id="bd239-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="bd239-144">Escolha **Informações** para obter seu status de sincronização.</span><span class="sxs-lookup"><span data-stu-id="bd239-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="bd239-145">Na página **Status da sincronização,** escolha **Sincronizar** para obter as políticas de gerenciamento de dispositivos móveis mais recentes no computador.</span><span class="sxs-lookup"><span data-stu-id="bd239-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="bd239-146">Para começar a usar a Microsoft 365 Business Premium, vá para  o botão Iniciar Windows, clique com o botão direito do mouse na imagem da sua conta atual e alternar **conta**.</span><span class="sxs-lookup"><span data-stu-id="bd239-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="bd239-147">Entre com o email e a senha da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd239-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="bd239-149">Verifique se o computador foi atualizado para Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="bd239-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="bd239-150">Verifique se seus dispositivos ingressados no Azure AD Windows 10 são atualizados para Windows 10 Business como parte de sua assinatura Microsoft 365 Business Premium de usuário.</span><span class="sxs-lookup"><span data-stu-id="bd239-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="bd239-151">Vá para **Configurações** \> **Sistema** \> **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="bd239-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="bd239-152">Confirme se a opção **Edição** exibe **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="bd239-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="bd239-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bd239-154">Next steps</span></span>

<span data-ttu-id="bd239-155">Para configurar seus dispositivos móveis, consulte [Configurar](set-up-mobile-devices.md)dispositivos móveis para usuários Microsoft 365 Business Premium , Para definir políticas de proteção de dispositivos ou proteção de aplicativos, consulte [Manage Microsoft 365 for business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="bd239-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="bd239-156">Para obter mais informações sobre como configurar e usar Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bd239-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="bd239-157">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="bd239-157">Microsoft 365 for business training videos</span></span>](../business-video/index.yml)
