---
title: Configurar recursos do Microsoft Defender Antivírus
description: Você pode configurar Microsoft Defender Antivírus recursos com o Intune, Microsoft Endpoint Configuration Manager, Política de Grupo e PowerShell.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, configurar, configuração, Gerenciador de Configurações, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gerenciamento de dispositivo móvel, GP, política de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275103"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="c5c22-104">Configurar recursos do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="c5c22-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c5c22-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c5c22-105">**Applies to:**</span></span>

- [<span data-ttu-id="c5c22-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c5c22-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c5c22-107">Você pode configurar Microsoft Defender Antivírus com várias ferramentas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="c5c22-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="c5c22-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c5c22-108">Microsoft Intune</span></span>
- <span data-ttu-id="c5c22-109">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="c5c22-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="c5c22-110">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="c5c22-110">Group Policy</span></span>
- <span data-ttu-id="c5c22-111">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5c22-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="c5c22-112">Windows Instrumentação de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="c5c22-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="c5c22-113">As seguintes categorias amplas de recursos podem ser configuradas:</span><span class="sxs-lookup"><span data-stu-id="c5c22-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="c5c22-114">Proteção fornecida na nuvem</span><span class="sxs-lookup"><span data-stu-id="c5c22-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="c5c22-115">Proteção sempre em tempo real, incluindo proteção comportamental, heurística e baseada em aprendizado de máquina</span><span class="sxs-lookup"><span data-stu-id="c5c22-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="c5c22-116">Como os usuários finais interagem com o cliente em pontos de extremidade individuais</span><span class="sxs-lookup"><span data-stu-id="c5c22-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="c5c22-117">Os artigos a seguir descrevem como executar tarefas-chave ao configurar Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="c5c22-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c5c22-118">Cada artigo inclui instruções para a ferramenta de configuração aplicável (ou ferramentas).</span><span class="sxs-lookup"><span data-stu-id="c5c22-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="c5c22-119">Artigo</span><span class="sxs-lookup"><span data-stu-id="c5c22-119">Article</span></span>  |<span data-ttu-id="c5c22-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="c5c22-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="c5c22-121">Usar a proteção Microsoft Defender Antivírus microsoft</span><span class="sxs-lookup"><span data-stu-id="c5c22-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="c5c22-122">Use a proteção entregue na nuvem para detecção avançada, rápida e robusta de antivírus.</span><span class="sxs-lookup"><span data-stu-id="c5c22-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="c5c22-123">Configurar a proteção comportamental, heurística e em tempo real</span><span class="sxs-lookup"><span data-stu-id="c5c22-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="c5c22-124">Habilita a proteção antivírus baseada em comportamento, heurística e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c5c22-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="c5c22-125">Configurar a interação do usuário final com Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="c5c22-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="c5c22-126">Configure como os usuários finais em sua organização interagem com Microsoft Defender Antivírus, quais notificações eles veem e se eles podem substituir as configurações.</span><span class="sxs-lookup"><span data-stu-id="c5c22-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="c5c22-127">Você também pode revisar os [tópicos De referência](configuration-management-reference-microsoft-defender-antivirus.md) para ferramentas de gerenciamento e configuração para uma visão geral de cada ferramenta e links para ajudar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="c5c22-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>