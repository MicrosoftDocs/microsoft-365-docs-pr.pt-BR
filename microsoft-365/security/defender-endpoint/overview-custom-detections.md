---
title: Visão geral das detecções personalizadas no Microsoft Defender ATP
ms.reviewer: ''
description: Entenda como você pode usar a busca avançada para criar detecções personalizadas e gerar alertas
keywords: detecções personalizadas, alertas, regras de detecção, busca avançada, busca, consulta, ações de resposta, intervalo, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500647"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="d2742-104">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="d2742-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2742-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d2742-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2742-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d2742-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2742-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2742-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d2742-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d2742-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2742-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d2742-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="d2742-110">Com detecções personalizadas, você pode monitorar e responder proativamente a vários eventos e estados do sistema, incluindo atividades suspeitas de violação e dispositivos configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="d2742-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="d2742-111">Você pode fazer isso com regras de detecção personalizáveis que disparam automaticamente alertas e ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="d2742-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="d2742-112">As detecções personalizadas funcionam com a busca avançada [,](advanced-hunting-overview.md)que fornece uma linguagem de consulta poderosa e flexível que abrange um amplo conjunto de eventos e informações do sistema de sua rede.</span><span class="sxs-lookup"><span data-stu-id="d2742-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="d2742-113">Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver corresponde.</span><span class="sxs-lookup"><span data-stu-id="d2742-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="d2742-114">As detecções personalizadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="d2742-114">Custom detections provide:</span></span>
- <span data-ttu-id="d2742-115">Alertas para detecções baseadas em regras criadas a partir de consultas de busca avançadas</span><span class="sxs-lookup"><span data-stu-id="d2742-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="d2742-116">Ações de resposta automática que se aplicam a arquivos e dispositivos</span><span class="sxs-lookup"><span data-stu-id="d2742-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="d2742-117">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d2742-117">Related topics</span></span>
- [<span data-ttu-id="d2742-118">Criar regras de detecção</span><span class="sxs-lookup"><span data-stu-id="d2742-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="d2742-119">Exibir e gerenciar regras de detecção</span><span class="sxs-lookup"><span data-stu-id="d2742-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="d2742-120">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="d2742-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
