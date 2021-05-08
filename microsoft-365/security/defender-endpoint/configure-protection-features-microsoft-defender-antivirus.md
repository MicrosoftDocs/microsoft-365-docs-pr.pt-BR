---
title: Habilitar e configurar recursos de proteção do Microsoft Defender Antivírus
description: Habilita a proteção baseada em comportamento, heurística e em tempo real no Microsoft Defender AV.
keywords: heurística, aprendizado de máquina, monitor de comportamento, proteção em tempo real, always-on, Microsoft Defender Antivírus, antimalware, segurança, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274592"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="ee360-104">Configurar a proteção comportamental, heurística e em tempo real</span><span class="sxs-lookup"><span data-stu-id="ee360-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ee360-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ee360-105">**Applies to:**</span></span>

- [<span data-ttu-id="ee360-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ee360-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ee360-107">O Microsoft Defender Antivírus usa vários métodos para fornecer proteção contra ameaças:</span><span class="sxs-lookup"><span data-stu-id="ee360-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="ee360-108">Proteção entregue na nuvem para detecção quase instantânea e bloqueio de ameaças novas e emergentes</span><span class="sxs-lookup"><span data-stu-id="ee360-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="ee360-109">Verificação sempre em tempo real, usando monitoramento de comportamento de arquivo e processo e outras heurísticas (também conhecidas como "proteção em tempo real")</span><span class="sxs-lookup"><span data-stu-id="ee360-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="ee360-110">Atualizações de proteção dedicadas com base em aprendizado de máquina, análise de grandes dimensões humana e automatizada e pesquisa de resistência de ameaças aprofundada</span><span class="sxs-lookup"><span data-stu-id="ee360-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="ee360-111">Você pode configurar como o Microsoft Defender Antivírus usa esses métodos com Política de Grupo, Gerenciamento de Configuração do System Center, cmdlets do PowerShell e Instrumentação de Gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="ee360-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="ee360-112">Esta seção aborda a configuração para a verificação always-on, incluindo como detectar e bloquear aplicativos considerados não seguros, mas que podem não ser detectados como malware.</span><span class="sxs-lookup"><span data-stu-id="ee360-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="ee360-113">Consulte [Usar tecnologias do Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md) de próxima geração por meio da proteção entregue na nuvem para habilitar e configurar a proteção entregue na nuvem do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="ee360-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ee360-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ee360-114">In this section</span></span>

 <span data-ttu-id="ee360-115">Tópico</span><span class="sxs-lookup"><span data-stu-id="ee360-115">Topic</span></span> | <span data-ttu-id="ee360-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee360-116">Description</span></span>
---|---
[<span data-ttu-id="ee360-117">Detectar e bloquear aplicativos potencialmente indesejados</span><span class="sxs-lookup"><span data-stu-id="ee360-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="ee360-118">Detectar e bloquear aplicativos que podem ser indesejados em sua rede, como adware, modificadores de navegador e barras de ferramentas e aplicativos antivírus desonestos ou falsos</span><span class="sxs-lookup"><span data-stu-id="ee360-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="ee360-119">Habilitar e configurar recursos de proteção do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="ee360-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="ee360-120">Habilitar e configurar a proteção em tempo real, heurística e outros recursos de monitoramento always-on do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="ee360-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>