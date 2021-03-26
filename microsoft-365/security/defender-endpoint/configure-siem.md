---
title: Pull detections to your SIEM tools from Microsoft Defender for Endpoint
description: Saiba como usar a API REST e configurar as ferramentas de gerenciamento de eventos e informações de segurança com suporte para receber e puxar detecções.
keywords: configurar siem, ferramentas de gerenciamento de informações e eventos de segurança, splunk, arcsight, indicadores personalizados, api de repouso, definições de alerta, indicadores de comprometimento
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222330"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="7fa3b-104">Pull detections to your SIEM tools</span><span class="sxs-lookup"><span data-stu-id="7fa3b-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7fa3b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7fa3b-105">**Applies to:**</span></span>
- [<span data-ttu-id="7fa3b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7fa3b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7fa3b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fa3b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7fa3b-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="7fa3b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7fa3b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="7fa3b-110">Pull detections using security information and events management (SIEM) tools</span><span class="sxs-lookup"><span data-stu-id="7fa3b-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="7fa3b-111">[O Alerta do Microsoft Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="7fa3b-112">[O Microsoft Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Dispositivo e seus detalhes de Alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="7fa3b-113">-A API de alerta do Microsoft Defender for Endpoint é a API mais recente para consumo de alerta e contém uma lista detalhada de evidências relacionadas para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="7fa3b-114">Para obter mais informações, consulte [Métodos de alerta e propriedades](alerts.md) e [Alertas de lista.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7fa3b-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="7fa3b-115">O Defender for Endpoint oferece suporte a ferramentas de gerenciamento de informações de segurança e de eventos (SIEM) para detectar detecções.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="7fa3b-116">O Defender for Endpoint expõe alertas por meio de um ponto de extremidade HTTPS hospedado no Azure.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="7fa3b-117">O ponto de extremidade pode ser configurado para puxar detecções do seu locatário corporativo no Azure Active Directory (AAD) usando o protocolo de autenticação OAuth 2.0 para um aplicativo AAD que representa o conector SIEM específico instalado em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="7fa3b-118">O Defender for Endpoint atualmente dá suporte às seguintes ferramentas de solução SIEM específicas por meio de um modelo de integração SIEM dedicado:</span><span class="sxs-lookup"><span data-stu-id="7fa3b-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="7fa3b-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="7fa3b-119">IBM QRadar</span></span>
- <span data-ttu-id="7fa3b-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="7fa3b-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="7fa3b-121">Outras soluções SIEM (como Splunk, RSA NetWitness) são suportadas por meio de um modelo de integração diferente com base na nova API de Alerta.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="7fa3b-122">Para obter mais informações, consulte a página [Aplicativo parceiro](https://securitycenter.microsoft.com/interoperability/partners) e selecione a seção Informações de Segurança e Análise para obter detalhes completos.</span><span class="sxs-lookup"><span data-stu-id="7fa3b-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="7fa3b-123">Para usar uma dessas ferramentas SIEM com suporte, você precisará:</span><span class="sxs-lookup"><span data-stu-id="7fa3b-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="7fa3b-124">Habilitar a integração do SIEM no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7fa3b-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="7fa3b-125">Configure a ferramenta SIEM suportada:</span><span class="sxs-lookup"><span data-stu-id="7fa3b-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="7fa3b-126">Configurar o Micro Focus ArcSight para puxar o Defender para detecções de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7fa3b-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="7fa3b-127">Configurar IBM QRadar para puxar o Defender para detecções de ponto de extremidade Para obter mais informações, consulte [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span><span class="sxs-lookup"><span data-stu-id="7fa3b-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="7fa3b-128">Para obter mais informações sobre a lista de campos expostos na API de Detecção, consulte [Defender for Endpoint Detection fields](api-portal-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="7fa3b-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
