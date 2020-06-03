---
title: Visão geral das detecções personalizadas no Microsoft Threat Protection
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498346"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="36076-104">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="36076-104">Custom detections overview</span></span>

<span data-ttu-id="36076-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="36076-105">**Applies to:**</span></span>
- <span data-ttu-id="36076-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="36076-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="36076-107">Com detecções personalizadas, você pode monitorar e responder de forma proativa vários eventos e Estados do sistema, incluindo a suspeita de falha da atividade e os pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="36076-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="36076-108">Isso é possível por regras de detecção personalizáveis que disparam alertas automaticamente e ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="36076-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="36076-109">As detecções personalizadas funcionam com a [busca avançada](advanced-hunting-overview.md), que oferece uma linguagem de consulta poderosa e flexível que abrange um amplo conjunto de informações de eventos e do sistema da sua rede.</span><span class="sxs-lookup"><span data-stu-id="36076-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="36076-110">Você pode defini-los para executar em intervalos regulares, gerar alertas e realizar ações de resposta sempre que houver correspondências.</span><span class="sxs-lookup"><span data-stu-id="36076-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="36076-111">As detecções personalizadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="36076-111">Custom detections provide:</span></span>
- <span data-ttu-id="36076-112">Alertas para detecções baseadas em regra criadas a partir de consultas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="36076-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="36076-113">Ações de resposta automática</span><span class="sxs-lookup"><span data-stu-id="36076-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="36076-114">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="36076-114">Related topic</span></span>
- [<span data-ttu-id="36076-115">Criar e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="36076-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="36076-116">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="36076-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)