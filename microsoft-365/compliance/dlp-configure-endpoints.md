---
title: Métodos e ferramentas de integração para Windows 10 dispositivos
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
description: Integração Windows 10 dispositivos para que eles possam enviar dados do sensor para as soluções Microsoft 365 Conformidade
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341695"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="243d8-103">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="243d8-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="243d8-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="243d8-104">**Applies to:**</span></span>
- [<span data-ttu-id="243d8-105">Microsoft 365 Prevenção contra perda de dados do ponto de extremidade (DLP)</span><span class="sxs-lookup"><span data-stu-id="243d8-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="243d8-106">Os dispositivos em sua organização devem ser configurados para que o serviço Microsoft 365 prevenção contra perda de dados do ponto de extremidade possa obter dados do sensor deles.</span><span class="sxs-lookup"><span data-stu-id="243d8-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="243d8-107">Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="243d8-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="243d8-108">As seguintes ferramentas de implantação e métodos são suportados:</span><span class="sxs-lookup"><span data-stu-id="243d8-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="243d8-109">política de grupo</span><span class="sxs-lookup"><span data-stu-id="243d8-109">group policy</span></span>
- <span data-ttu-id="243d8-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="243d8-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="243d8-111">Gerenciamento de dispositivo móvel (incluindo Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="243d8-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="243d8-112">script local</span><span class="sxs-lookup"><span data-stu-id="243d8-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="243d8-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="243d8-113">In this section</span></span>
<span data-ttu-id="243d8-114">Tópico</span><span class="sxs-lookup"><span data-stu-id="243d8-114">Topic</span></span> | <span data-ttu-id="243d8-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="243d8-115">Description</span></span>
:---|:---
[<span data-ttu-id="243d8-116">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="243d8-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="243d8-117">Use a Política de Grupo para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="243d8-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="243d8-118">Integração Windows dispositivos usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="243d8-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="243d8-119">Você pode usar o Microsoft Endpoint Configuration Manager versão 1606 ou Microsoft Endpoint Configuration Manager (branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="243d8-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="243d8-120">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="243d8-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="243d8-121">Use ferramentas de Gerenciamento de Dispositivo Móvel ou Microsoft Intune para implantar o pacote de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="243d8-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="243d8-122">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="243d8-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="243d8-123">Saiba como usar o script local para implantar o pacote de configuração nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="243d8-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="243d8-124">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="243d8-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="243d8-125">Saiba como usar o pacote de configuração para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="243d8-125">Learn how to use the configuration package to configure VDI devices.</span></span>