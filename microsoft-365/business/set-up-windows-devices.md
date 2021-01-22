---
title: Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium
f1.keywords:
- CSH
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
description: Saiba como configurar dispositivos Windows que executam o Windows 10 Pro para usuários do Microsoft 365 Business Premium, habilitando controles de segurança e gerenciamento centralizados.
ms.openlocfilehash: b1877d83f113a2ba23d0db374967e0afcd7fe067
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928715"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="0bf68-103">Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0bf68-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="0bf68-104">Pré-requisitos para configurar dispositivos Windows para usuários do Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0bf68-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="0bf68-105">Antes de configurar dispositivos Windows para usuários do Microsoft 365 Business Premium, certifique-se de que todos os dispositivos Windows estão executando o Windows 10 Pro, versão 1703 (Atualização para Criadores).</span><span class="sxs-lookup"><span data-stu-id="0bf68-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="0bf68-106">O Windows 10 Pro é um pré-requisito para implantar o Windows 10 Business, que é um conjunto de serviços de nuvem e recursos de gerenciamento de dispositivos que complementam o Windows 10 Pro e permitem o gerenciamento centralizado e os controles de segurança do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0bf68-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="0bf68-107">Se você tiver dispositivos Windows que executam o Windows 7 Pro, Windows 8 Pro ou Windows 8.1 Pro, sua assinatura do Microsoft 365 Business Premium lhe dará direito a uma atualização do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0bf68-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="0bf68-108">Para obter mais informações sobre como atualizar dispositivos Windows para a Atualização do Windows 10 Pro para Criadores, siga as etapas deste tópico: [Atualize dispositivos Windows para a Atualização do Windows Pro para Criadores](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="0bf68-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="0bf68-109">Confira [Verificar se o dispositivo está conectado ao Azure AD](#verify-the-device-is-connected-to-azure-ad) para verificar se você tem a atualização ou se a atualização funcionou.</span><span class="sxs-lookup"><span data-stu-id="0bf68-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="0bf68-110">Assista a um vídeo curto sobre como conectar o Windows ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0bf68-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="0bf68-111">Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="0bf68-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="0bf68-112">Ingressar dispositivos Windows 10 ao Azure AD de sua organização</span><span class="sxs-lookup"><span data-stu-id="0bf68-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="0bf68-113">Quando todos os dispositivos Windows em sua organização foram atualizados para a Atualização do Windows 10 Pro para Criadores ou já estão executando a Atualização do Windows 10 Pro para Criadores, você pode ingressar esses dispositivos no Azure Active Directory da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0bf68-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="0bf68-114">Depois que os dispositivos ingressarem, eles serão automaticamente atualizados para o Windows 10 Business, que faz parte da sua assinatura do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0bf68-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="0bf68-115">No caso de um dispositivo Windows 10 Pro novo ou atualizado recentemente</span><span class="sxs-lookup"><span data-stu-id="0bf68-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="0bf68-116">No caso de um novo dispositivo que executa a Atualização do Windows 10 Pro para Criadores ou um dispositivo que foi atualizado para a Atualização do Windows 10 Pro para Criadores, mas não passou pela configuração do dispositivo Windows 10, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0bf68-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="0bf68-117">Execute a configuração do dispositivo Windows 10 até chegar à página **Como você deseja configurar?**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="0bf68-119">Aqui, escolha **Configurar para uma organização e** insira seu nome de usuário e senha para o Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0bf68-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="0bf68-120">Conclua a configuração do dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0bf68-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="0bf68-p103">Quando terminar, o usuário será conectado ao Azure AD de sua organização. Para garantir a conexão, confira [Verifique se o dispositivo está conectado ao Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="0bf68-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="0bf68-123">Para um dispositivo já configurado executando o Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="0bf68-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="0bf68-124">**Conecte os usuários ao Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="0bf68-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="0bf68-125">No PC Windows do usuário, que esteja executando o Windows 10 Pro, versão 1703 (Atualização do Criador) (veja os [pré-requisitos](pre-requisites-for-data-protection.md)), clique no logotipo do Windows e, em seguida, no ícone de Configurações.</span><span class="sxs-lookup"><span data-stu-id="0bf68-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="0bf68-127">Em **Configurações**, vá para **Contas**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="0bf68-129">Na página **Suas informações**, clique em **Acessar trabalho ou escola** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="0bf68-131">Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, em **Ações alternativas**, escolha **Ingressar este dispositivo no Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="0bf68-133">Na página de **login**, insira sua conta corporativa ou de estudante \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="0bf68-134">Na página **Insira sua senha**, insira a senha \> **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="0bf68-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="0bf68-137">Em **Você está tudo pronto!**</span><span class="sxs-lookup"><span data-stu-id="0bf68-137">On the **You're all set!**</span></span> <span data-ttu-id="0bf68-138">page, chosse **Done**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-138">page, chosse **Done**.</span></span>
  
   ![Na tela Certifique-se de que esta seja a sua organização, escolha Ingressar](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="0bf68-140">Se você carregou arquivos no OneDrive for Business, sincronize-os novamente.</span><span class="sxs-lookup"><span data-stu-id="0bf68-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="0bf68-141">Se você usou uma ferramenta de terceiros para migrar perfis e arquivos, sincronize-os também com o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="0bf68-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="0bf68-142">Verifique se o dispositivo está conectado ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="0bf68-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="0bf68-143">Para verificar seu status de sincronização, na página trabalho ou escola do **Access** em Configurações, selecione a área Conectado a **_** _ para expor os botões \<organization name\> **Informações** e **Desconectar.**</span><span class="sxs-lookup"><span data-stu-id="0bf68-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="0bf68-144">Escolha **Informações para** obter o status de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0bf68-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="0bf68-145">Na página **Status da Sincronização,** escolha **Sincronizar** para obter as políticas de gerenciamento de dispositivo móvel mais recentes no computador.</span><span class="sxs-lookup"><span data-stu-id="0bf68-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="0bf68-146">Para começar a usar a conta do Microsoft 365 Business Premium, vá para o botão Iniciar do **Windows,** clique com o botão direito do mouse na imagem da sua conta atual e, em seguida, **altere a conta.**</span><span class="sxs-lookup"><span data-stu-id="0bf68-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="0bf68-147">Entre com o email e a senha da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0bf68-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="0bf68-149">Verificar se o computador foi atualizado para o Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="0bf68-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="0bf68-150">Verifique se seus dispositivos Windows 10 ingressados no Azure AD foram atualizados para o Windows 10 Business como parte da sua assinatura do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0bf68-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="0bf68-151">Vá para **Configurações** \> **Sistema** \> **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="0bf68-152">Confirme se a opção **Edição** exibe **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="0bf68-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="0bf68-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0bf68-154">Next steps</span></span>

<span data-ttu-id="0bf68-155">Para configurar seus dispositivos móveis, confira Configurar dispositivos móveis para usuários do [Microsoft 365 Business Premium,](set-up-mobile-devices.md)para definir políticas de proteção de dispositivos ou de proteção de aplicativos, confira Gerenciar o [Microsoft 365 para empresas.](manage.md)</span><span class="sxs-lookup"><span data-stu-id="0bf68-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="0bf68-156">Para obter mais informações sobre como configurar e usar o Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0bf68-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="0bf68-157">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="0bf68-157">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
