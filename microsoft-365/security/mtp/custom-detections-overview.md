---
title: Visão geral das detecções personalizadas no Microsoft 365 Defender
description: Entenda como você pode usar a busca avançada para criar detecções personalizadas e gerar alertas
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, microsoft 365, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928803"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="582b6-104">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="582b6-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="582b6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="582b6-105">**Applies to:**</span></span>
- <span data-ttu-id="582b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="582b6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="582b6-107">Com detecções personalizadas, você pode monitorar e responder proativamente a vários eventos e estados do sistema, incluindo atividades suspeitas de violação e pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="582b6-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="582b6-108">Isso é possível por meio de regras de detecção personalizáveis que disparam alertas automaticamente, bem como ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="582b6-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="582b6-109">As detecções personalizadas funcionam com a busca [avançada,](advanced-hunting-overview.md)que fornece uma linguagem de consulta avançada e flexível que abrange um amplo conjunto de informações de eventos e do sistema de sua rede.</span><span class="sxs-lookup"><span data-stu-id="582b6-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="582b6-110">Você pode defini-los para que sejam executados em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver resultados.</span><span class="sxs-lookup"><span data-stu-id="582b6-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="582b6-111">As detecções personalizadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="582b6-111">Custom detections provide:</span></span>
- <span data-ttu-id="582b6-112">Alertas para detecções baseadas em regras criadas a partir de consultas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="582b6-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="582b6-113">Ações de resposta automática</span><span class="sxs-lookup"><span data-stu-id="582b6-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="582b6-114">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="582b6-114">Related topic</span></span>
- [<span data-ttu-id="582b6-115">Criar e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="582b6-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="582b6-116">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="582b6-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
