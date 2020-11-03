---
title: Visão geral das detecções personalizadas no Microsoft 365 defender
description: Entender como você pode usar a busca avançada para criar detecções personalizadas e gerar alertas
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: fe2b9f1b52fa2c8d9031bb58597992f3dda91520
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843907"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="d40bd-104">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="d40bd-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d40bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d40bd-105">**Applies to:**</span></span>
- <span data-ttu-id="d40bd-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d40bd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d40bd-107">Com detecções personalizadas, você pode monitorar e responder de forma proativa vários eventos e Estados do sistema, incluindo a suspeita de falha da atividade e os pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="d40bd-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="d40bd-108">Isso é possível por regras de detecção personalizáveis que disparam alertas automaticamente e ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="d40bd-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="d40bd-109">As detecções personalizadas funcionam com a [busca avançada](advanced-hunting-overview.md), que oferece uma linguagem de consulta poderosa e flexível que abrange um amplo conjunto de informações de eventos e do sistema da sua rede.</span><span class="sxs-lookup"><span data-stu-id="d40bd-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="d40bd-110">Você pode defini-los para executar em intervalos regulares, gerar alertas e realizar ações de resposta sempre que houver correspondências.</span><span class="sxs-lookup"><span data-stu-id="d40bd-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="d40bd-111">As detecções personalizadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="d40bd-111">Custom detections provide:</span></span>
- <span data-ttu-id="d40bd-112">Alertas para detecções baseadas em regra criadas a partir de consultas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="d40bd-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="d40bd-113">Ações de resposta automática</span><span class="sxs-lookup"><span data-stu-id="d40bd-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="d40bd-114">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="d40bd-114">Related topic</span></span>
- [<span data-ttu-id="d40bd-115">Criar e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="d40bd-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="d40bd-116">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="d40bd-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
