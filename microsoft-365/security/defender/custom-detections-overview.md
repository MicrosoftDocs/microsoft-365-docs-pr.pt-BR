---
title: Visão geral das detecções personalizadas no Microsoft 365 Defender
description: Entenda como você pode usar a busca avançada para criar detecções personalizadas e gerar alertas
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952531"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="9c95a-104">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="9c95a-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9c95a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9c95a-105">**Applies to:**</span></span>
- <span data-ttu-id="9c95a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c95a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="9c95a-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9c95a-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9c95a-108">Com detecções personalizadas, você pode monitorar e responder proativamente a vários eventos e estados do sistema, incluindo atividades suspeitas de violação e pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="9c95a-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="9c95a-109">Isso é possível por meio de regras de detecção personalizáveis que disparam automaticamente alertas, bem como ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c95a-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="9c95a-110">As detecções personalizadas funcionam com a busca avançada [,](advanced-hunting-overview.md)que fornece uma linguagem de consulta poderosa e flexível que abrange um amplo conjunto de eventos e informações do sistema de sua rede.</span><span class="sxs-lookup"><span data-stu-id="9c95a-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="9c95a-111">Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver corresponde.</span><span class="sxs-lookup"><span data-stu-id="9c95a-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="9c95a-112">As detecções personalizadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="9c95a-112">Custom detections provide:</span></span>
- <span data-ttu-id="9c95a-113">Alertas para detecções baseadas em regras criadas a partir de consultas de busca avançadas</span><span class="sxs-lookup"><span data-stu-id="9c95a-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="9c95a-114">Ações de resposta automáticas</span><span class="sxs-lookup"><span data-stu-id="9c95a-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="9c95a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="9c95a-115">See also</span></span>
- [<span data-ttu-id="9c95a-116">Criar e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="9c95a-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="9c95a-117">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="9c95a-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9c95a-118">Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9c95a-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
