---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636097"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="14f33-103">Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot</span><span class="sxs-lookup"><span data-stu-id="14f33-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="14f33-104">Você pode usar Windows AutoPilot para configurar novos dispositivos **Windows 10** para sua empresa para que eles possam ser usado quando você os der aos seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="14f33-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="14f33-105">Requisitos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="14f33-105">Device requirements</span></span>

<span data-ttu-id="14f33-106">Os dispositivos devem atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="14f33-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="14f33-107">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="14f33-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="14f33-108">Novos dispositivos que não passaram por Windows experiência completa</span><span class="sxs-lookup"><span data-stu-id="14f33-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="14f33-109">Usar o guia de configuração para criar perfis e dispositivos</span><span class="sxs-lookup"><span data-stu-id="14f33-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="14f33-110">Se você ainda não criou grupos de dispositivos ou perfis, a melhor maneira de começar é usando o guia passo a passo.</span><span class="sxs-lookup"><span data-stu-id="14f33-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="14f33-111">Você também pode [adicionar dispositivos e](create-and-edit-autopilot-devices.md) [atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia.</span><span class="sxs-lookup"><span data-stu-id="14f33-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="14f33-112">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="14f33-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="14f33-113">No painel de navegação esquerdo, escolha **Dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="14f33-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![No centro de administração, escolha dispositivos e, em seguida, o AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="14f33-115">Na página **Piloto Automático,** clique ou toque em **Guia iniciar.**</span><span class="sxs-lookup"><span data-stu-id="14f33-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="14f33-117">No arquivo **Upload .csv com a** lista de dispositivos, navegue até um local onde você tenha o arquivo .CSV e **Abra** \> **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="14f33-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="14f33-118">O arquivo deve ter três headers:</span><span class="sxs-lookup"><span data-stu-id="14f33-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="14f33-119">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="14f33-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="14f33-120">Coluna B: ID do produto Windows</span><span class="sxs-lookup"><span data-stu-id="14f33-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="14f33-121">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="14f33-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="14f33-122">Você pode obter essas informações do fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="14f33-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="14f33-p103">Para saber mais, confira o [Arquivo CSV da lista de dispositivos](../admin/misc/device-list.md). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="14f33-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="14f33-125">Esse script usa o WMI para recuperar as propriedades necessárias para que um cliente registre um dispositivo com Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="14f33-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="14f33-126">Observe que é normal que o arquivo CSV resultante não colete um valor de ID do Produto (PKID) de Windows, pois isso não é necessário para registrar um dispositivo e o PKID sendo NULL no CSV de saída está totalmente bem.</span><span class="sxs-lookup"><span data-stu-id="14f33-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="14f33-127">Somente o número de série e o hash de hardware serão preenchidos.</span><span class="sxs-lookup"><span data-stu-id="14f33-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="14f33-128">Na página **Atribuir um perfil,** você pode escolher um perfil existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="14f33-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="14f33-129">Se você ainda não tiver um, será solicitado a criar um.</span><span class="sxs-lookup"><span data-stu-id="14f33-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="14f33-130">Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14f33-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="14f33-131">Os recursos padrão são necessários e são definidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="14f33-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="14f33-132">Os recursos padrão são:</span><span class="sxs-lookup"><span data-stu-id="14f33-132">The default features are:</span></span>
    
    - <span data-ttu-id="14f33-133">Ignore o registro cortana, OneDrive e OEM.</span><span class="sxs-lookup"><span data-stu-id="14f33-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="14f33-134">Crie uma experiência de entrada com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="14f33-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="14f33-135">Conexão seus dispositivos para Azure Active Directory contas e inscreva-as automaticamente para serem gerenciadas por Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="14f33-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="14f33-136">Para obter mais informações, consulte [Sobre configurações do Perfil do AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="14f33-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="14f33-137">As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="14f33-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="14f33-138">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="14f33-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="14f33-139">**Você terminou indica que** o perfil criado (ou escolhido) será aplicado ao grupo de dispositivos criado carregando a lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="14f33-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="14f33-140">As configurações entrarão em vigor quando os usuários do dispositivo entrarem em seguida.</span><span class="sxs-lookup"><span data-stu-id="14f33-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="14f33-141">Escolha **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="14f33-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="14f33-142">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="14f33-142">Related content</span></span>

<span data-ttu-id="14f33-143">[Sobre as configurações do Perfil do AutoPilot](autopilot-profile-settings.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="14f33-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="14f33-144">[Opções para proteger seus dispositivos e dados do aplicativo](../admin/devices/choose-device-security.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="14f33-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
