---
title: Configurar e gerenciar o Microsoft Defender para recursos de ponto de extremidade
ms.reviewer: ''
description: Configurar e gerenciar o Microsoft Defender para recursos de ponto de extremidade, como redução de superfície de ataque e proteção de próxima geração
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861330"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="e16bd-104">Configurar e gerenciar o Microsoft Defender para recursos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e16bd-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e16bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e16bd-105">**Applies to:**</span></span>

- [<span data-ttu-id="e16bd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e16bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e16bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e16bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e16bd-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e16bd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e16bd-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e16bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e16bd-110">Saiba como configurar e gerenciar recursos do Defender para Ponto de Extremidade, para obter a melhor proteção de segurança para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e16bd-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="e16bd-111">Para conselhos práticos sobre como conectar novos dispositivos em sua organização, consulte [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e16bd-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e16bd-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e16bd-112">In this section</span></span>

<span data-ttu-id="e16bd-113">Tópico</span><span class="sxs-lookup"><span data-stu-id="e16bd-113">Topic</span></span> | <span data-ttu-id="e16bd-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e16bd-114">Description</span></span>
:---|:---
[<span data-ttu-id="e16bd-115">Configurar configurações do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e16bd-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="e16bd-116">Configure as configurações relacionadas ao portal, como configurações gerais, recursos avançados ou habilita a experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="e16bd-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="e16bd-117">Configurar recursos de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="e16bd-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="e16bd-118">Configure os recursos de redução de superfície de ataque, para garantir que as configurações sejam aplicadas corretamente e que as técnicas de mitigação de exploração sejam definidas.</span><span class="sxs-lookup"><span data-stu-id="e16bd-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="e16bd-119">Configurar a proteção de última geração</span><span class="sxs-lookup"><span data-stu-id="e16bd-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="e16bd-120">Configure a proteção de última geração para capturar todos os tipos de ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="e16bd-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="e16bd-121">Configurar recursos de Especialistas em Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e16bd-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="e16bd-122">Configure e gerencie a inteligência de ameaças de segurança cibernética dos Especialistas em Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e16bd-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="e16bd-123">Configurar a integração com a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e16bd-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="e16bd-124">Configure outras soluções que se integram ao Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e16bd-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="e16bd-125">Gerenciamento e suporte à API</span><span class="sxs-lookup"><span data-stu-id="e16bd-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="e16bd-126">Puxe alertas para seu SIEM (Gerenciamento de Informações e Eventos de Segurança) ou use APIs para criar alertas personalizados.</span><span class="sxs-lookup"><span data-stu-id="e16bd-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="e16bd-127">Criar e criar relatórios do Power BI.</span><span class="sxs-lookup"><span data-stu-id="e16bd-127">Create and build Power BI reports.</span></span>
