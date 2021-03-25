---
title: Configurar e gerenciar recursos do Microsoft Defender ATP
ms.reviewer: ''
description: Configurar e gerenciar recursos do Microsoft Defender ATP, como redução de superfície de ataque e proteção de próxima geração
keywords: configurar, gerenciar, recursos, redução de superfície de ataque, proteção de última geração, controles de segurança, detecção e resposta do ponto de extremidade, investigação automática e correção, controles de segurança, controles
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
ms.openlocfilehash: a0872de9774773c136bca6febd621daba5b2d7d3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186372"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="a86a5-104">Configurar e gerenciar o Microsoft Defender para recursos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a86a5-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a86a5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a86a5-105">**Applies to:**</span></span>
- [<span data-ttu-id="a86a5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a86a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a86a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a86a5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a86a5-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a86a5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a86a5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a86a5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a86a5-110">Configure e gerencie todos os recursos do Defender for Endpoint para obter a melhor proteção de segurança para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a86a5-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="a86a5-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a86a5-111">In this section</span></span> 
<span data-ttu-id="a86a5-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="a86a5-112">Topic</span></span> | <span data-ttu-id="a86a5-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="a86a5-113">Description</span></span> 
:---|:---
[<span data-ttu-id="a86a5-114">Configurar recursos de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="a86a5-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="a86a5-115">Ao garantir que as configurações sejam definidas corretamente e que as técnicas de mitigação de exploração sejam aplicadas, esse conjunto de recursos resistem a ataques e exploração.</span><span class="sxs-lookup"><span data-stu-id="a86a5-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="a86a5-116">Configurar a proteção de última geração</span><span class="sxs-lookup"><span data-stu-id="a86a5-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="a86a5-117">Configure a proteção de última geração para capturar todos os tipos de ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="a86a5-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="a86a5-118">Configurar recursos de Especialistas em Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a86a5-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="a86a5-119">Configure e gerencie como você gostaria de obter inteligência contra ameaças de segurança cibernética dos Especialistas em Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a86a5-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="a86a5-120">Configurar a integração com a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a86a5-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="a86a5-121">Configure outras soluções que se integram ao Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="a86a5-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="a86a5-122">Gerenciamento e suporte à API</span><span class="sxs-lookup"><span data-stu-id="a86a5-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="a86a5-123">Puxe alertas para seu SIEM ou use APIs para criar alertas personalizados.</span><span class="sxs-lookup"><span data-stu-id="a86a5-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="a86a5-124">Criar e criar relatórios do Power BI.</span><span class="sxs-lookup"><span data-stu-id="a86a5-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="a86a5-125">Configurar configurações do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a86a5-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="a86a5-126">Configure as configurações relacionadas ao portal, como configurações gerais, recursos avançados, habilitar a experiência de visualização e outros.</span><span class="sxs-lookup"><span data-stu-id="a86a5-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



