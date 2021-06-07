---
title: Configurar recursos de redução de superfície de ataque
description: Use Microsoft Intune, Microsoft Endpoint Configuration Manager, cmdlets do PowerShell e Política de Grupo para configurar a redução de superfície de ataque.
keywords: asr, redução de superfície de ataque, windows defender, microsoft defender, antivírus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770956"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="879de-104">Configurar recursos de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="879de-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="879de-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="879de-105">**Applies to:**</span></span>
- [<span data-ttu-id="879de-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="879de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="879de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="879de-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="879de-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="879de-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="879de-109">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="879de-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="879de-110">O Defender para Ponto de Extremidade inclui vários recursos de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="879de-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="879de-111">Para saber mais, confira [Visão geral dos recursos de redução de superfície de ataque.](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="879de-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="879de-112">Para configurar a redução de superfície de ataque em seu ambiente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="879de-112">To configure attack surface reduction in your environment, follow these steps:</span></span> 

1. <span data-ttu-id="879de-113">[Habilitar o isolamento baseado em hardware para Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span><span class="sxs-lookup"><span data-stu-id="879de-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="879de-114">Habilitar o controle do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="879de-114">Enable application control.</span></span> 

   1. <span data-ttu-id="879de-115">Revise as políticas básicas Windows.</span><span class="sxs-lookup"><span data-stu-id="879de-115">Review base policies in Windows.</span></span> <span data-ttu-id="879de-116">Consulte [políticas base de exemplo](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span><span class="sxs-lookup"><span data-stu-id="879de-116">See [example base policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="879de-117">Consulte o [guia de design de controle do aplicativo](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span><span class="sxs-lookup"><span data-stu-id="879de-117">See the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="879de-118">Consulte o guia [de design de controle do aplicativo.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="879de-118">Refer to the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="879de-119">[Habilitar acesso controlado a pastas](enable-controlled-folders.md).</span><span class="sxs-lookup"><span data-stu-id="879de-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="879de-120">[Ativar a proteção de rede](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="879de-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="879de-121">[Habilitar a proteção de exploração](enable-exploit-protection.md).</span><span class="sxs-lookup"><span data-stu-id="879de-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="879de-122">[Configurar regras de redução de superfície de ataque](enable-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="879de-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="879de-123">Configurar o firewall de rede.</span><span class="sxs-lookup"><span data-stu-id="879de-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="879de-124">Obter uma visão geral do [Windows Defender Firewall com segurança avançada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span><span class="sxs-lookup"><span data-stu-id="879de-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="879de-125">Use o [Windows Defender Firewall de design](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) para decidir como você deseja projetar suas políticas de firewall.</span><span class="sxs-lookup"><span data-stu-id="879de-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="879de-126">Use o [Windows Defender Firewall de implantação](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) para configurar o firewall da sua organização com segurança avançada.</span><span class="sxs-lookup"><span data-stu-id="879de-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span> 

> [!TIP]
> <span data-ttu-id="879de-127">Na maioria dos casos, ao configurar recursos de redução de superfície de ataque, você pode escolher entre vários métodos:</span><span class="sxs-lookup"><span data-stu-id="879de-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>
> - <span data-ttu-id="879de-128">Microsoft Endpoint Manager (que agora inclui Microsoft Intune e Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="879de-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="879de-129">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="879de-129">Group Policy</span></span>
> - <span data-ttu-id="879de-130">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="879de-130">PowerShell cmdlets</span></span>
