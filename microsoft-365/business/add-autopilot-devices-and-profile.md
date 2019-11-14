---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa.
ms.openlocfilehash: 5f40dac57285b83da57d4506bac58e562475522c
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323086"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="f87cd-103">Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot</span><span class="sxs-lookup"><span data-stu-id="f87cd-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="f87cd-104">Você pode usar o Windows AutoPilot para configurar **novos** dispositivos Windows 10 para sua empresa, de modo que eles fiquem prontos para uso quando você os conceder aos seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="f87cd-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="f87cd-105">Requisitos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f87cd-105">Device requirements</span></span>

<span data-ttu-id="f87cd-106">Os dispositivos devem atender a estes requisitos:</span><span class="sxs-lookup"><span data-stu-id="f87cd-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="f87cd-107">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f87cd-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="f87cd-108">Novos dispositivos que não foram transferidos pela experiência inicial pelo Windows</span><span class="sxs-lookup"><span data-stu-id="f87cd-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="f87cd-109">Usar o guia de configuração para criar perfis e dispositivos</span><span class="sxs-lookup"><span data-stu-id="f87cd-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="f87cd-110">[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="f87cd-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="f87cd-111">Se você ainda não criou grupos ou perfis de dispositivos, a melhor maneira de começar é usando o guia passo a passo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="f87cd-112">Você também pode [Adicionar dispositivos](create-and-edit-autopilot-devices.md) e [atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia.</span><span class="sxs-lookup"><span data-stu-id="f87cd-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="f87cd-113">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f87cd-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f87cd-114">No painel de navegação esquerdo, escolha **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![No centro de administração, escolha dispositivos e, em seguida, piloto automático.](media/AutoPilot.png)
  
2. <span data-ttu-id="f87cd-116">Na página **AutoPilot** , clique ou toque em **iniciar guia**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="f87cd-118">Na página **carregar arquivo. csv com a lista de dispositivos** , navegue até um local onde você está preparado. CSV e, em seguida, **abra** \> **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="f87cd-119">O arquivo deve ter três cabeçalhos:</span><span class="sxs-lookup"><span data-stu-id="f87cd-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="f87cd-120">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f87cd-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="f87cd-121">Coluna B: ID do produto Windows</span><span class="sxs-lookup"><span data-stu-id="f87cd-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="f87cd-122">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="f87cd-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="f87cd-123">Você pode obter essas informações do seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f87cd-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="f87cd-p103">Para saber mais, confira o [Arquivo CSV da lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-p103">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="f87cd-126">Na página **atribuir um perfil** , você pode escolher um perfil existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="f87cd-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="f87cd-127">Se você ainda não tiver um, você será solicitado a criar um.</span><span class="sxs-lookup"><span data-stu-id="f87cd-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="f87cd-128">Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f87cd-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="f87cd-129">Os recursos padrão são necessários e são definidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f87cd-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="f87cd-130">Os recursos padrão são:</span><span class="sxs-lookup"><span data-stu-id="f87cd-130">The default features are:</span></span>
    
    - <span data-ttu-id="f87cd-131">Ignorar o registro de Cortana, OneDrive e OEM.</span><span class="sxs-lookup"><span data-stu-id="f87cd-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="f87cd-132">Crie uma experiência de entrada com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="f87cd-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="f87cd-133">Conecte seus dispositivos às contas do Azure Active Directory e registre-os automaticamente para serem gerenciados pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f87cd-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="f87cd-134">Para obter mais informações, consulte [sobre as configurações de perfil do AutoPilot](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f87cd-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="f87cd-135">As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="f87cd-136">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="f87cd-137">**Você concluiu** indica que o perfil criado (ou escolhido) será aplicado ao grupo de dispositivos que você criou carregando a lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f87cd-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="f87cd-138">As configurações entrarão em vigor quando os usuários do dispositivo entrarem em seguida.</span><span class="sxs-lookup"><span data-stu-id="f87cd-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="f87cd-139">Escolha **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f87cd-139">Choose **Close**.</span></span>
    