---
title: Ferramentas e métodos de integração para dispositivos Windows 10 (versão prévia)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Dispositivos integrados do Windows 10 para que eles possam enviar dados de sensor para as soluções de conformidade da Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769638"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="6bb89-103">Ferramentas e métodos de integração para dispositivos Windows 10 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="6bb89-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="6bb89-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6bb89-104">**Applies to:**</span></span>
- [<span data-ttu-id="6bb89-105">Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="6bb89-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="6bb89-106">Os dispositivos de sua organização devem estar configurados para que o serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365 possa obter dados de sensor deles.</span><span class="sxs-lookup"><span data-stu-id="6bb89-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="6bb89-107">Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6bb89-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="6bb89-108">As seguintes ferramentas e métodos de implantação têm suporte:</span><span class="sxs-lookup"><span data-stu-id="6bb89-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="6bb89-109">política de grupo</span><span class="sxs-lookup"><span data-stu-id="6bb89-109">group policy</span></span>
- <span data-ttu-id="6bb89-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6bb89-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="6bb89-111">Gerenciamento de dispositivos móveis (incluindo o Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="6bb89-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="6bb89-112">script local</span><span class="sxs-lookup"><span data-stu-id="6bb89-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6bb89-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6bb89-113">In this section</span></span>
<span data-ttu-id="6bb89-114">Tópico</span><span class="sxs-lookup"><span data-stu-id="6bb89-114">Topic</span></span> | <span data-ttu-id="6bb89-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="6bb89-115">Description</span></span>
:---|:---
[<span data-ttu-id="6bb89-116">Dispositivos Windows 10 integrados usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="6bb89-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="6bb89-117">Use a política de grupo para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6bb89-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="6bb89-118">Dispositivos do Windows integrados usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6bb89-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="6bb89-119">Você pode usar o Microsoft Endpoint Configuration Manager (Branch atual) versão 1606 ou o Microsoft Endpoint Configuration Manager (Branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6bb89-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="6bb89-120">Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="6bb89-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="6bb89-121">Use as ferramentas de gerenciamento de dispositivo móvel ou o Microsoft Intune para implantar o pacote de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bb89-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="6bb89-122">Dispositivos integrados do Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="6bb89-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="6bb89-123">Saiba como usar o script local para implantar o pacote de configuração em pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="6bb89-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="6bb89-124">Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="6bb89-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="6bb89-125">Saiba como usar o pacote de configuração para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="6bb89-125">Learn how to use the configuration package to configure VDI devices.</span></span>
