---
title: Configurar redução de superfície de ataque
description: Use o Microsoft Intune, o Microsoft Endpoint Configuration Manager, os cmdlets do PowerShell e a Política de Grupo para configurar a redução de superfície de ataque.
keywords: asr, redução de superfície de ataque, windows defender, microsoft defender, antivírus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166156"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="ae65c-104">Configurar redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ae65c-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ae65c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ae65c-105">**Applies to:**</span></span>
- [<span data-ttu-id="ae65c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ae65c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae65c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae65c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ae65c-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ae65c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ae65c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ae65c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="ae65c-110">Você pode configurar a redução de superfície de ataque com várias ferramentas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="ae65c-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="ae65c-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ae65c-111">Microsoft Intune</span></span>
* <span data-ttu-id="ae65c-112">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="ae65c-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="ae65c-113">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="ae65c-113">Group Policy</span></span>
* <span data-ttu-id="ae65c-114">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae65c-114">PowerShell cmdlets</span></span>

<span data-ttu-id="ae65c-115">Artigo</span><span class="sxs-lookup"><span data-stu-id="ae65c-115">Article</span></span> | <span data-ttu-id="ae65c-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="ae65c-116">Description</span></span>
-|-
[<span data-ttu-id="ae65c-117">Habilitar isolamento baseado em hardware para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ae65c-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="ae65c-118">Como preparar e instalar o Application Guard, incluindo requisitos de hardware e software</span><span class="sxs-lookup"><span data-stu-id="ae65c-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="ae65c-119">Habilitar o controle do aplicativo</span><span class="sxs-lookup"><span data-stu-id="ae65c-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="ae65c-120">Como controlar aplicativos executados por usuários e proteger processos de modo kernel</span><span class="sxs-lookup"><span data-stu-id="ae65c-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="ae65c-121">Proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="ae65c-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="ae65c-122">Como aplicar automaticamente técnicas de mitigação de exploração em processos do sistema operacional e em aplicativos individuais</span><span class="sxs-lookup"><span data-stu-id="ae65c-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="ae65c-123">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="ae65c-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="ae65c-124">Como impedir que os usuários usem aplicativos para acessar domínios perigosos</span><span class="sxs-lookup"><span data-stu-id="ae65c-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="ae65c-125">Acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="ae65c-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="ae65c-126">Como proteger dados valiosos de aplicativos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="ae65c-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="ae65c-127">Redução da superfície do ataque.</span><span class="sxs-lookup"><span data-stu-id="ae65c-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="ae65c-128">Como evitar ações e aplicativos que normalmente são usados por malware de exploração</span><span class="sxs-lookup"><span data-stu-id="ae65c-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="ae65c-129">Firewall de rede</span><span class="sxs-lookup"><span data-stu-id="ae65c-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="ae65c-130">Como proteger dispositivos e dados em uma rede</span><span class="sxs-lookup"><span data-stu-id="ae65c-130">How to protect devices and data across a network</span></span>

