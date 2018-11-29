---
title: Criar e editar os dispositivos do AutoPilot
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o piloto automático no Microsoft 365 Business. Você pode atribuir um perfil para um dispositivo ou um grupo de dispositivos.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864928"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="d5291-104">Criar e editar os dispositivos do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="d5291-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="d5291-105">Carregar uma lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d5291-105">Upload a list of devices</span></span>

<span data-ttu-id="d5291-106">Você pode usar o [Guia passo a passo](add-autopilot-devices-and-profile.md) para carregar dispositivos, mas também pode carregar na guia **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="d5291-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="d5291-107">Os dispositivos precisam atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="d5291-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="d5291-108">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="d5291-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="d5291-109">Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="d5291-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="d5291-110">No Centro de administração do Microsoft 365 Business, escolha **Implantar o Windows com o AutoPilot** no cartão **Ações do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="d5291-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="d5291-112">Na página **Preparar o Windows**, escolha a guia **Dispositivos** \> **Adicionar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="d5291-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="d5291-114">No painel **Adicionar dispositivos** , navegue até uma [lista de dispositivos arquivo CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que você preparou \> **Salvar** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="d5291-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="d5291-115">Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que gerará um arquivo csv.</span><span class="sxs-lookup"><span data-stu-id="d5291-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="d5291-116">Atribuir um perfil a um dispositivo ou a um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d5291-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="d5291-117">Na página **Preparar Windows**, escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5291-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="d5291-118">No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**.</span><span class="sxs-lookup"><span data-stu-id="d5291-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="d5291-119">Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="d5291-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
