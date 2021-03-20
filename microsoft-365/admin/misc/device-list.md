---
title: Arquivo CSV da lista de dispositivos
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Saiba como fazer um arquivo CSV para AutoPilot no Microsoft 365 para empresas.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914733"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="864f7-103">Arquivo CSV da lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="864f7-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="864f7-104">Formato de arquivo .csv da lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="864f7-104">Device list .csv file format</span></span>

<span data-ttu-id="864f7-105">Para gerenciar e implantar dispositivos por meio do Windows Autopilot, você precisará de um arquivo .csv que contenha informações específicas sobre os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="864f7-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="864f7-106">As colunas no arquivo de lista de dispositivos devem ter os seguintes headers na ordem especificada:</span><span class="sxs-lookup"><span data-stu-id="864f7-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="864f7-107">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="864f7-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="864f7-108">Coluna B: deixar em branco</span><span class="sxs-lookup"><span data-stu-id="864f7-108">Column B: leave blank</span></span>

- <span data-ttu-id="864f7-109">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="864f7-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="864f7-110">Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="864f7-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="864f7-111">Ao adicionar dispositivos, você também precisa adicioná-los a um Perfil.</span><span class="sxs-lookup"><span data-stu-id="864f7-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="864f7-112">Um perfil é usado para aplicar perfis de implantação do AutoPilot a um dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="864f7-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="864f7-113">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="864f7-113">Related articles</span></span>

[<span data-ttu-id="864f7-114">Recursos e documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="864f7-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="864f7-115">Começar com o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="864f7-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="864f7-116">Gerenciar o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="864f7-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
