---
title: Criar e editar os perfis do AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Saiba como criar, editar, excluir ou remover perfis do AutoPilot.
ms.openlocfilehash: 28f5b679d58711d11d9af26dffb7022024b72c79
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065868"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="9e5d6-103">Criar e editar os perfis do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="9e5d6-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="9e5d6-104">Criar um perfil</span><span class="sxs-lookup"><span data-stu-id="9e5d6-104">Create a profile</span></span>

<span data-ttu-id="9e5d6-105">Um perfil aplica-se a um dispositivo ou a um grupo de dispositivos,</span><span class="sxs-lookup"><span data-stu-id="9e5d6-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="9e5d6-106">No centro de administração do Microsoft 365 Business, escolha **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="9e5d6-107">Na página **piloto automático** , escolha a guia **perfis** para \> **Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="9e5d6-108">Na página **Criar perfil** , digite um nome para o perfil que o ajuda a identificá-lo, por exemplo, marketing.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="9e5d6-109">Ative a configuração desejada e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="9e5d6-110">Para obter mais informações sobre as configurações de perfil do AutoPilot, consulte [sobre as configurações de perfil do AutoPilot](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9e5d6-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="9e5d6-112">Aplicar perfil a um dispositivo</span><span class="sxs-lookup"><span data-stu-id="9e5d6-112">Apply profile to a device</span></span>

<span data-ttu-id="9e5d6-113">Depois de criar um perfil, você pode aplicá-lo a um dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="9e5d6-114">Você pode escolher um perfil existente no guia passo a [passo](add-autopilot-devices-and-profile.md) e aplicá-lo a novos dispositivos ou substituir um perfil existente para um dispositivo ou grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="9e5d6-115">Na página **Preparar o Windows**, escolha a guia **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="9e5d6-116">Marque a caixa de seleção ao lado de um nome de dispositivo e, no painel **dispositivo** , escolha um perfil na lista \> suspensa **perfil atribuído** **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="9e5d6-118">Editar, excluir ou remover um perfil</span><span class="sxs-lookup"><span data-stu-id="9e5d6-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="9e5d6-p103">Após atribuir um perfil a um dispositivo, você poderá atualizá-lo, mesmo que já tenha atribuído o dispositivo a um usuário. Quando o dispositivo se conecta à Internet, ele baixa a versão mais recente do seu perfil durante o processo de configuração. Se o usuário restaurar o dispositivo para as configurações padrão de fábrica, o dispositivo baixará novamente as atualizações mais recentes para seu perfil.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="9e5d6-122">Editar um perfil</span><span class="sxs-lookup"><span data-stu-id="9e5d6-122">Edit a profile</span></span>

1. <span data-ttu-id="9e5d6-123">Na página **Preparar o Windows**, escolha a guia **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="9e5d6-124">Marque a caixa de seleção ao lado de um nome de dispositivo e, no painel **perfil** , atualize qualquer uma das \> configurações disponíveis **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="9e5d6-125">Se você fizer isso antes de um usuário conectar o dispositivo à internet, o perfil será aplicado ao processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="9e5d6-126">Excluir um perfil</span><span class="sxs-lookup"><span data-stu-id="9e5d6-126">Delete a profile</span></span>

1. <span data-ttu-id="9e5d6-127">Na página **Preparar o Windows**, escolha a guia **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="9e5d6-128">Marque a caixa de seleção ao lado de um nome de dispositivo e, no painel **perfil** , selecione **excluir** \> **salvar**perfil.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="9e5d6-129">Quando você exclui um perfil, ele é removido de um dispositivo ou grupo de dispositivos ao qual foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="9e5d6-130">Remover um perfil</span><span class="sxs-lookup"><span data-stu-id="9e5d6-130">Remove a profile</span></span>

1. <span data-ttu-id="9e5d6-131">Na página **Preparar o Windows**, escolha a guia **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="9e5d6-132">Marque a caixa de seleção ao lado de um nome de dispositivo e, no painel **dispositivo** , escolha **nenhum** na lista \> suspensa **perfil atribuído** **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9e5d6-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
