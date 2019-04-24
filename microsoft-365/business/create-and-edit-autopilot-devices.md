---
title: Criar e editar os dispositivos do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o piloto automático no Microsoft 365 Business. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277013"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="f7d24-104">Criar e editar os dispositivos do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f7d24-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="f7d24-105">Carregar uma lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f7d24-105">Upload a list of devices</span></span>

<span data-ttu-id="f7d24-106">Você pode usar o [Guia passo a passo](add-autopilot-devices-and-profile.md) para carregar dispositivos, mas também pode carregar na guia **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f7d24-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="f7d24-107">Os dispositivos precisam atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="f7d24-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="f7d24-108">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="f7d24-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="f7d24-109">Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="f7d24-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="f7d24-110">no centro de administração de negócios do 365 da Microsoft, escolha **dispositivos** \> **piloto automático** \> **adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f7d24-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot** \> **Add**.</span></span>
  
2. <span data-ttu-id="f7d24-111">Na página **Preparar o Windows**, escolha a guia **Dispositivos** \> **Adicionar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f7d24-111">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="f7d24-113">No painel **Adicionar dispositivos** , navegue até uma [lista de dispositivos CSV-arquivo](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que você preparou \> **salvar** \> **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f7d24-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="f7d24-114">Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que gerará um arquivo csv.</span><span class="sxs-lookup"><span data-stu-id="f7d24-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="f7d24-115">Atribuir um perfil a um dispositivo ou a um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f7d24-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="f7d24-116">Na página **Preparar Windows**, escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f7d24-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="f7d24-117">No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**.</span><span class="sxs-lookup"><span data-stu-id="f7d24-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="f7d24-118">Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="f7d24-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
