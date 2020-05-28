---
title: Arquivo CSV de lista de dispositivos
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
description: Saiba como criar um arquivo CSV para o piloto automático no Microsoft 365 for Business.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399357"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="2800c-103">Arquivo CSV de lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2800c-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="2800c-104">Formato de arquivo. csv de lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2800c-104">Device list .csv file format</span></span>

<span data-ttu-id="2800c-105">Para gerenciar e implantar dispositivos por meio do Windows AutoPilot, você precisará de um arquivo. csv que contenha informações específicas sobre os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2800c-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="2800c-106">As colunas no arquivo de lista de dispositivos devem ter os seguintes cabeçalhos na ordem especificada:</span><span class="sxs-lookup"><span data-stu-id="2800c-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="2800c-107">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2800c-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="2800c-108">Coluna B: deixar em branco</span><span class="sxs-lookup"><span data-stu-id="2800c-108">Column B: leave blank</span></span>

- <span data-ttu-id="2800c-109">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="2800c-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="2800c-110">Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2800c-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="2800c-111">Ao adicionar dispositivos, você também precisa adicioná-los a um perfil.</span><span class="sxs-lookup"><span data-stu-id="2800c-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="2800c-112">Um perfil é usado para aplicar perfis de implantação do piloto automático a um dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2800c-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="2800c-113">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="2800c-113">Related articles</span></span>

[<span data-ttu-id="2800c-114">Documentação e recursos do Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="2800c-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="2800c-115">Introdução ao Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="2800c-115">Get started with Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[<span data-ttu-id="2800c-116">Gerenciar o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2800c-116">Manage Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/manage)
  
