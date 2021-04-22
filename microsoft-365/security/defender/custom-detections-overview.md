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
ms.openlocfilehash: bf635ed03cb0d99d54fc94b622bf244447b32a80
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935696"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="92a4b-104">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="92a4b-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="92a4b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="92a4b-105">**Applies to:**</span></span>
- <span data-ttu-id="92a4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92a4b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="92a4b-107">Com detecções personalizadas, você pode monitorar e responder proativamente a vários eventos e estados do sistema, incluindo atividades suspeitas de violação e pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="92a4b-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="92a4b-108">Isso é possível por meio de regras de detecção personalizáveis que disparam automaticamente alertas, bem como ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="92a4b-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="92a4b-109">As detecções personalizadas funcionam com a busca avançada [,](advanced-hunting-overview.md)que fornece uma linguagem de consulta poderosa e flexível que abrange um amplo conjunto de eventos e informações do sistema de sua rede.</span><span class="sxs-lookup"><span data-stu-id="92a4b-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="92a4b-110">Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver corresponde.</span><span class="sxs-lookup"><span data-stu-id="92a4b-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="92a4b-111">As detecções personalizadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="92a4b-111">Custom detections provide:</span></span>
- <span data-ttu-id="92a4b-112">Alertas para detecções baseadas em regras criadas a partir de consultas de busca avançadas</span><span class="sxs-lookup"><span data-stu-id="92a4b-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="92a4b-113">Ações de resposta automáticas</span><span class="sxs-lookup"><span data-stu-id="92a4b-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="92a4b-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="92a4b-114">See also</span></span>
- [<span data-ttu-id="92a4b-115">Criar e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="92a4b-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="92a4b-116">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="92a4b-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="92a4b-117">Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="92a4b-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
