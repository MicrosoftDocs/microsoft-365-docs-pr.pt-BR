---
title: Notas de versão da API do Microsoft Defender para Ponto de Extremidade
description: Notas de versão para atualizações feitas no conjunto de APIs do Microsoft Defender for Endpoint.
keywords: Notas de versão da API do Microsoft Defender para Ponto de Extremidade, mde, APIs, API do Microsoft Defender para Ponto de Extremidade, atualizações, anotações, versão
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 7bae413028a0add7e5288e52bc3184e30f319c46
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073833"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="5b27e-104">Notas de versão da API do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5b27e-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="5b27e-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5b27e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5b27e-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5b27e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b27e-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5b27e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5b27e-108">As informações a seguir listam as atualizações feitas para as APIs do Microsoft Defender para Ponto de Extremidade e as datas em que foram feitas.</span><span class="sxs-lookup"><span data-stu-id="5b27e-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="5b27e-109">RSS feed: seja notificado quando esta página for atualizada copiando e colar a SEGUINTE URL no leitor de feeds:</span><span class="sxs-lookup"><span data-stu-id="5b27e-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="5b27e-110">Notas de versão - mais recente para mais antiga</span><span class="sxs-lookup"><span data-stu-id="5b27e-110">Release notes - newest to oldest</span></span>

### <a name="10022021"></a><span data-ttu-id="5b27e-111">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="5b27e-111">10.02.2021</span></span>

- <span data-ttu-id="5b27e-112">Adicionada nova API: [alertas de atualização em lotes.](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="5b27e-112">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="5b27e-113">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="5b27e-113">25.01.2021</span></span>

- <span data-ttu-id="5b27e-114">Limitações de taxa atualizadas para [a API de Busca Avançada](run-advanced-query-api.md) de 15 a 45 solicitações por minuto.</span><span class="sxs-lookup"><span data-stu-id="5b27e-114">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="5b27e-115">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="5b27e-115">21.01.2021</span></span>

- <span data-ttu-id="5b27e-116">Adicionada nova API: [Encontre dispositivos por marca](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5b27e-116">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="5b27e-117">Adicionada nova API: [Indicadores de importação](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="5b27e-117">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="5b27e-118">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="5b27e-118">03.01.2021</span></span>

- <span data-ttu-id="5b27e-119">Evidência de alerta atualizada: adicionadas ***detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** propriedades.</span><span class="sxs-lookup"><span data-stu-id="5b27e-119">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="5b27e-120">Entidade [Alerta Atualizada](alerts.md): adicionada a propriedade ***detectorId.***</span><span class="sxs-lookup"><span data-stu-id="5b27e-120">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="5b27e-121">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="5b27e-121">15.12.2020</span></span>

- <span data-ttu-id="5b27e-122">Entidade [Do dispositivo](machine.md) atualizada: adicionada a lista ***IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="5b27e-122">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="5b27e-123">Consulte [Listar dispositivos](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="5b27e-123">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="5b27e-124">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="5b27e-124">04.11.2020</span></span>

- <span data-ttu-id="5b27e-125">Adicionada nova API: [definir o valor do dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="5b27e-125">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="5b27e-126">Entidade [Device](machine.md) atualizada: adicionada a ***propriedade deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="5b27e-126">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="5b27e-127">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="5b27e-127">01.09.2020</span></span>

- <span data-ttu-id="5b27e-128">Opção adicionada para expandir a entidade Alert com suas evidências relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5b27e-128">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="5b27e-129">Consulte [List Alerts](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5b27e-129">See [List Alerts](get-alerts.md).</span></span>
