---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa para que eles estão prontos para uso dos funcionários.
ms.openlocfilehash: 75cc51b889f8673de8dba2357c777de47fd0d296
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913493"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="b1b84-103">Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot</span><span class="sxs-lookup"><span data-stu-id="b1b84-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="b1b84-104">Você pode usar o Windows AutoPilot para configurar novos dispositivos **Windows** 10 para sua empresa para que eles possam ser usado quando você os der aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="b1b84-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="b1b84-105">Requisitos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b1b84-105">Device requirements</span></span>

<span data-ttu-id="b1b84-106">Os dispositivos devem atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="b1b84-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="b1b84-107">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="b1b84-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="b1b84-108">Novos dispositivos que não passaram pela experiência completa do Windows</span><span class="sxs-lookup"><span data-stu-id="b1b84-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="b1b84-109">Usar o guia de configuração para criar perfis e dispositivos</span><span class="sxs-lookup"><span data-stu-id="b1b84-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="b1b84-110">[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="b1b84-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="b1b84-111">Se você ainda não criou grupos de dispositivos ou perfis, a melhor maneira de começar é usando o guia passo a passo.</span><span class="sxs-lookup"><span data-stu-id="b1b84-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="b1b84-112">Você também pode [adicionar dispositivos e](create-and-edit-autopilot-devices.md) [atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia.</span><span class="sxs-lookup"><span data-stu-id="b1b84-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="b1b84-113">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b1b84-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b1b84-114">No painel de navegação esquerdo, escolha **Dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="b1b84-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![No centro de administração, escolha dispositivos e, em seguida, o AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="b1b84-116">Na página **Piloto Automático,** clique ou toque em **Guia iniciar.**</span><span class="sxs-lookup"><span data-stu-id="b1b84-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="b1b84-118">Na página **Carregar arquivo .csv com** lista de dispositivos, navegue até um local onde você tenha o . Arquivo CSV **e,** em seguida, Abrir \> **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b1b84-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="b1b84-119">O arquivo deve ter três headers:</span><span class="sxs-lookup"><span data-stu-id="b1b84-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="b1b84-120">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b1b84-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="b1b84-121">Coluna B: ID do produto Windows</span><span class="sxs-lookup"><span data-stu-id="b1b84-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="b1b84-122">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="b1b84-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="b1b84-123">Você pode obter essas informações do fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="b1b84-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="b1b84-p103">Para saber mais, confira o [Arquivo CSV da lista de dispositivos](../admin/misc/device-list.md). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b1b84-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b1b84-126">Esse script usa o WMI para recuperar as propriedades necessárias para que um cliente registre um dispositivo com o Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="b1b84-126">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="b1b84-127">Observe que é normal que o arquivo CSV resultante não colete um valor de ID de Produto do Windows (PKID), uma vez que isso não é necessário para registrar um dispositivo e PKID sendo NULL no CSV de saída está totalmente bem.</span><span class="sxs-lookup"><span data-stu-id="b1b84-127">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="b1b84-128">Somente o número de série e o hash de hardware serão preenchidos.</span><span class="sxs-lookup"><span data-stu-id="b1b84-128">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="b1b84-129">Na página **Atribuir um perfil,** você pode escolher um perfil existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="b1b84-129">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="b1b84-130">Se você ainda não tiver um, será solicitado a criar um.</span><span class="sxs-lookup"><span data-stu-id="b1b84-130">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="b1b84-131">Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b1b84-131">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="b1b84-132">Os recursos padrão são necessários e são definidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b1b84-132">The default features are required and are set automatically.</span></span> <span data-ttu-id="b1b84-133">Os recursos padrão são:</span><span class="sxs-lookup"><span data-stu-id="b1b84-133">The default features are:</span></span>
    
    - <span data-ttu-id="b1b84-134">Ignore o registro da Cortana, do OneDrive e do OEM.</span><span class="sxs-lookup"><span data-stu-id="b1b84-134">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="b1b84-135">Crie uma experiência de entrada com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="b1b84-135">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="b1b84-136">Conecte seus dispositivos às contas do Azure Active Directory e inscreva-os automaticamente para serem gerenciados pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b1b84-136">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="b1b84-137">Para obter mais informações, consulte [Sobre configurações do Perfil do AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b1b84-137">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="b1b84-138">As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="b1b84-138">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="b1b84-139">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1b84-139">Choose **Next**.</span></span>
    
6. <span data-ttu-id="b1b84-140">**Você terminou indica que** o perfil criado (ou escolhido) será aplicado ao grupo de dispositivos criado carregando a lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b1b84-140">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="b1b84-141">As configurações entrarão em vigor quando os usuários do dispositivo entrarem em seguida.</span><span class="sxs-lookup"><span data-stu-id="b1b84-141">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="b1b84-142">Escolha **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b1b84-142">Choose **Close**.</span></span>
