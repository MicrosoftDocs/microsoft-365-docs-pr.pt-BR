---
title: Microsoft 365 Integração do Defender com o Azure Sentinel
description: Use o Azure Sentinel como SIEM para Microsoft 365 incidentes e eventos do Defender.
keywords: incidentes, alertas, investigar, analisar, responder, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782916"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="cf50a-104">Microsoft 365 Integração do Defender com o Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="cf50a-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cf50a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cf50a-105">**Applies to:**</span></span>
- <span data-ttu-id="cf50a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf50a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cf50a-107">O Microsoft 365 do Defender para o Azure Sentinel (visualização) envia todas as Microsoft 365 incidentes do Defender e alerta informações para o Azure Sentinel e mantém os incidentes sincronizados.</span><span class="sxs-lookup"><span data-stu-id="cf50a-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="cf50a-108">Depois de adicionar o conector, os incidentes do Microsoft 365 Defender que incluem todos os alertas, entidades e informações relevantes associados recebidos do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade, Microsoft Defender para Office 365 e Microsoft Cloud App Security são transmitidos para o Azure Sentinel como dados de informações de segurança e gerenciamento de eventos (SIEM), fornecendo contexto para executar a triagem e a resposta a incidentes com o &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="cf50a-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="cf50a-109">Uma vez no Azure Sentinel, os incidentes permanecem sincronizados de forma bi-direcional com o Microsoft 365 Defender, permitindo que você tire proveito dos benefícios do centro de segurança do Microsoft 365 e do Azure Sentinel no portal do Azure para investigação e resposta de incidentes.</span><span class="sxs-lookup"><span data-stu-id="cf50a-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="cf50a-110">Veja como funciona.</span><span class="sxs-lookup"><span data-stu-id="cf50a-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="O fluxo e o compartilhamento de dados de incidentes entre o Microsoft 365 Defender e o Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="cf50a-112">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cf50a-112">Next steps</span></span>

1. <span data-ttu-id="cf50a-113">Obter uma compreensão mais profunda sobre [Microsoft 365 integração do Defender com o Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span><span class="sxs-lookup"><span data-stu-id="cf50a-113">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="cf50a-114">[Conexão dados do Microsoft 365 Defender para o Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="cf50a-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf50a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="cf50a-115">See also</span></span>

- [<span data-ttu-id="cf50a-116">Visão geral dos incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf50a-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="cf50a-117">Investigar incidentes com o Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="cf50a-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
