---
title: Configurar recursos do Microsoft Defender Antivírus
description: Você pode configurar Microsoft Defender Antivírus recursos com o Intune, Microsoft Endpoint Configuration Manager, Política de Grupo e PowerShell.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, configurar, configuração, Gerenciador de Configurações, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gerenciamento de dispositivo móvel, GP, política de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7fa5959ede9f0c71c75cefafc0fcb0d4376a1a4f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925390"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="3769b-104">Configurar recursos do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="3769b-104">Configure Microsoft Defender Antivirus features</span></span>


<span data-ttu-id="3769b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3769b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3769b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3769b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3769b-107">Você pode configurar Microsoft Defender Antivírus com várias ferramentas, como:</span><span class="sxs-lookup"><span data-stu-id="3769b-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="3769b-108">Microsoft Endpoint Manager (que inclui Microsoft Intune e Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="3769b-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="3769b-109">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="3769b-109">Group Policy</span></span>
- <span data-ttu-id="3769b-110">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3769b-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="3769b-111">Windows Instrumentação de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="3769b-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="3769b-112">As seguintes categorias amplas de recursos podem ser configuradas:</span><span class="sxs-lookup"><span data-stu-id="3769b-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="3769b-113">Proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3769b-113">Cloud-delivered protection.</span></span> <span data-ttu-id="3769b-114">Consulte Proteção e proteção [entregues na nuvem Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3769b-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="3769b-115">Proteção sempre em tempo real, incluindo proteção comportamental, heurística e baseada em aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="3769b-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="3769b-116">Consulte [Configurar proteção comportamental, heurística e em tempo real.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3769b-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="3769b-117">Como os usuários finais interagem com o cliente em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="3769b-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="3769b-118">Consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="3769b-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="3769b-119">Impedir que os usuários vejam ou interajam com a Microsoft Defender Antivírus do usuário</span><span class="sxs-lookup"><span data-stu-id="3769b-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="3769b-120">Impedir ou permitir que os usuários modifiquem localmente Microsoft Defender Antivírus configurações de política</span><span class="sxs-lookup"><span data-stu-id="3769b-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="3769b-121">Revise [tópicos de referência para ferramentas de gerenciamento e configuração.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3769b-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>
