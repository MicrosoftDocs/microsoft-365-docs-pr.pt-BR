---
title: Criar e editar os dispositivos do AutoPilot
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o piloto automático no Microsoft 365 Business. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: 1dd6b1a574166379e29465bf3699e47e3b155e0b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320249"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="0ed6e-104">Criar e editar os dispositivos do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="0ed6e-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="0ed6e-105">Carregar uma lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ed6e-105">Upload a list of devices</span></span>

<span data-ttu-id="0ed6e-106">Você pode usar o [guia](add-autopilot-devices-and-profile.md) passo a passo para carregar dispositivos, mas você também pode carregar dispositivos na guia **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="0ed6e-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="0ed6e-107">Os dispositivos devem atender a estes requisitos:</span><span class="sxs-lookup"><span data-stu-id="0ed6e-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="0ed6e-108">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="0ed6e-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="0ed6e-109">Novos dispositivos que não foram transferidos pela experiência inicial pelo Windows</span><span class="sxs-lookup"><span data-stu-id="0ed6e-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="0ed6e-110">No centro de administração do Microsoft 365 Business, escolha **dispositivos** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="0ed6e-111">Na página **piloto automático** \> , escolha a guia **dispositivos** **Adicionar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="0ed6e-113">No painel **Adicionar dispositivos** , navegue até um [arquivo CSV de lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que você preparou \> **salvar** \> **fechar**.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="0ed6e-114">Você pode obter essas informações do seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="0ed6e-115">Atribuir um perfil a um dispositivo ou a um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ed6e-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="0ed6e-116">Na página **preparar o Windows** , escolha a guia **dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="0ed6e-117">No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="0ed6e-118">Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="0ed6e-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
