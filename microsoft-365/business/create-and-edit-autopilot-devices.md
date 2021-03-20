---
title: Criar e editar os dispositivos do AutoPilot
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o AutoPilot no Microsoft 365 Business Premium. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913389"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="a9cbe-104">Crie e edite os dispositivos do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a9cbe-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="a9cbe-105">Carregar uma lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a9cbe-105">Upload a list of devices</span></span>

<span data-ttu-id="a9cbe-106">Você pode usar o [guia Passo a](add-autopilot-devices-and-profile.md) passo para carregar dispositivos, mas também pode carregar dispositivos na guia **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="a9cbe-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="a9cbe-107">Os dispositivos devem atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="a9cbe-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="a9cbe-108">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="a9cbe-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="a9cbe-109">Novos dispositivos que não passaram pela experiência completa do Windows</span><span class="sxs-lookup"><span data-stu-id="a9cbe-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="a9cbe-110">No centro de administração do Microsoft 365, escolha **Dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="a9cbe-111">Na página **Piloto Automático,** escolha a guia **Dispositivos** \> **Adicionar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="a9cbe-113">No painel **Adicionar dispositivos,** navegue até um arquivo [CSV](../admin/misc/device-list.md) da lista de dispositivos que você preparou \> **Salvar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="a9cbe-114">Você pode obter essas informações do fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="a9cbe-115">Atribuir um perfil a um dispositivo ou a um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a9cbe-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="a9cbe-116">Na página **Preparar o Windows,** escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="a9cbe-117">No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="a9cbe-118">Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="a9cbe-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
