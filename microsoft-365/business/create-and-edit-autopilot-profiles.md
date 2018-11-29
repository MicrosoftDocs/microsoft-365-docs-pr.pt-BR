---
title: Criar e editar os perfis do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Saiba como criar, editar, excluir ou remover perfis de piloto automático. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864983"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="33211-103">Criar e editar os perfis do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="33211-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="33211-104">Criar um perfil</span><span class="sxs-lookup"><span data-stu-id="33211-104">Create a profile</span></span>

<span data-ttu-id="33211-105">Um perfil aplica-se a um dispositivo ou a um grupo de dispositivos,</span><span class="sxs-lookup"><span data-stu-id="33211-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="33211-106">No Centro de administração do Microsoft 365 Business, escolha **Implantar o Windows com o AutoPilot** no cartão **Ações do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="33211-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="33211-108">Na página **Preparar o Windows**, escolha a guia **Perfis** \> **Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="33211-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="33211-109">Na página **Criar perfil**, insira um nome para o perfil que o ajude a identificá-lo, por exemplo, Marketing, ative a configuração desejada (confira [Sobre as configurações de perfil de AutoPilot](autopilot-profile-settings.md) para saber mais), e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33211-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="33211-111">Aplicar perfil a um dispositivo</span><span class="sxs-lookup"><span data-stu-id="33211-111">Apply profile to a device</span></span>

<span data-ttu-id="33211-p101">Depois de criar um perfil, pode aplicá-lo a um dispositivo ou a um grupo de dispositivos. Você pode escolher um perfil existente no [guia passo a passo](add-autopilot-devices-and-profile.md), aplicá-lo a outros dispositivos ou substituir um perfil existente para um dispositivo ou grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="33211-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="33211-114">Na página **Preparar o Windows**, escolha a guia **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="33211-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="33211-115">Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Dispositivo**, escolha um perfil no menu suspenso **Perfil atribuído** \> **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33211-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="33211-117">Editar, excluir ou remover um perfil</span><span class="sxs-lookup"><span data-stu-id="33211-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="33211-p102">Após atribuir um perfil a um dispositivo, você poderá atualizá-lo, mesmo que já tenha atribuído o dispositivo a um usuário. Quando o dispositivo se conecta à Internet, ele baixa a versão mais recente do seu perfil durante o processo de configuração. Se o usuário restaurar o dispositivo para as configurações padrão de fábrica, o dispositivo baixará novamente as atualizações mais recentes para seu perfil.</span><span class="sxs-lookup"><span data-stu-id="33211-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="33211-121">Editar um perfil</span><span class="sxs-lookup"><span data-stu-id="33211-121">Edit a profile</span></span>

1. <span data-ttu-id="33211-122">Na página **Preparar o Windows**, escolha a guia **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="33211-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="33211-123">Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Perfil**, atualize qualquer uma das configurações disponíveis \> **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33211-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="33211-124">Se você fizer isso antes de um usuário conectar o dispositivo à internet, o perfil será aplicado ao processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="33211-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="33211-125">Excluir um perfil</span><span class="sxs-lookup"><span data-stu-id="33211-125">Delete a profile</span></span>

1. <span data-ttu-id="33211-126">Na página **Preparar o Windows**, escolha a guia **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="33211-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="33211-127">Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Perfil**, clique em **Excluir perfil** \> **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33211-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="33211-128">Quando você exclui um perfil, ele é removido de um dispositivo ou grupo de dispositivos ao qual foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="33211-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="33211-129">Remover um perfil</span><span class="sxs-lookup"><span data-stu-id="33211-129">Remove a profile</span></span>

1. <span data-ttu-id="33211-130">Na página **Preparar o Windows**, escolha a guia **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="33211-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="33211-131">Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Dispositivo**, escolha **Nenhum** no menu suspenso **Perfil atribuído** \> **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33211-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
