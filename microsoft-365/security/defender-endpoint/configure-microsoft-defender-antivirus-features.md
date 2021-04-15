---
title: Configurar recursos do Microsoft Defender Antivírus
description: Você pode configurar recursos do Microsoft Defender Antivírus com o Intune, o Microsoft Endpoint Configuration Manager, a Política de Grupo e o PowerShell.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, configurar, configuração, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gerenciamento de dispositivo móvel, GP, política de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765162"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="ee3d6-104">Configurar recursos do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="ee3d6-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ee3d6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ee3d6-105">**Applies to:**</span></span>

- [<span data-ttu-id="ee3d6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ee3d6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ee3d6-107">Você pode configurar o Microsoft Defender Antivírus com várias ferramentas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="ee3d6-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="ee3d6-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ee3d6-108">Microsoft Intune</span></span>
- <span data-ttu-id="ee3d6-109">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee3d6-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="ee3d6-110">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="ee3d6-110">Group Policy</span></span>
- <span data-ttu-id="ee3d6-111">Cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee3d6-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="ee3d6-112">Instrumentação de Gerenciamento do Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="ee3d6-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="ee3d6-113">As seguintes categorias amplas de recursos podem ser configuradas:</span><span class="sxs-lookup"><span data-stu-id="ee3d6-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="ee3d6-114">Proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="ee3d6-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="ee3d6-115">Proteção sempre em tempo real, incluindo proteção comportamental, heurística e baseada em aprendizado de máquina</span><span class="sxs-lookup"><span data-stu-id="ee3d6-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="ee3d6-116">Como os usuários finais interagem com o cliente em pontos de extremidade individuais</span><span class="sxs-lookup"><span data-stu-id="ee3d6-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="ee3d6-117">Os artigos a seguir descrevem como executar tarefas importantes ao configurar o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="ee3d6-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ee3d6-118">Cada artigo inclui instruções para a ferramenta de configuração aplicável (ou ferramentas).</span><span class="sxs-lookup"><span data-stu-id="ee3d6-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="ee3d6-119">Artigo</span><span class="sxs-lookup"><span data-stu-id="ee3d6-119">Article</span></span>  |<span data-ttu-id="ee3d6-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee3d6-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="ee3d6-121">Usar a proteção do Microsoft Defender Antivírus fornecida na nuvem pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee3d6-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="ee3d6-122">Use a proteção entregue na nuvem para detecção avançada, rápida e robusta de antivírus.</span><span class="sxs-lookup"><span data-stu-id="ee3d6-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="ee3d6-123">Configurar a proteção comportamental, heurística e em tempo real</span><span class="sxs-lookup"><span data-stu-id="ee3d6-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="ee3d6-124">Habilita a proteção antivírus baseada em comportamento, heurística e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="ee3d6-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="ee3d6-125">Configurar a interação do usuário final com o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="ee3d6-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="ee3d6-126">Configure como os usuários finais em sua organização interagem com o Microsoft Defender Antivírus, quais notificações eles veem e se eles podem substituir as configurações.</span><span class="sxs-lookup"><span data-stu-id="ee3d6-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="ee3d6-127">Você também pode revisar os [tópicos De referência](configuration-management-reference-microsoft-defender-antivirus.md) para ferramentas de gerenciamento e configuração para uma visão geral de cada ferramenta e links para ajudar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="ee3d6-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>