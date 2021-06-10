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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4843894638ccf119c0cadcf003e159e793c18368
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843729"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="3660c-104">Notas de versão da API do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3660c-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="3660c-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3660c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3660c-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3660c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3660c-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3660c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3660c-108">As informações a seguir listam as atualizações feitas para as APIs do Microsoft Defender para Ponto de Extremidade e as datas em que foram feitas.</span><span class="sxs-lookup"><span data-stu-id="3660c-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="3660c-109">RSS feed: seja notificado quando esta página for atualizada copiando e colar a SEGUINTE URL no leitor de feeds:</span><span class="sxs-lookup"><span data-stu-id="3660c-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="3660c-110">Notas de versão - mais recente para mais antiga (dd.mm.yyyy)</span><span class="sxs-lookup"><span data-stu-id="3660c-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="05252021"></a><span data-ttu-id="3660c-111">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="3660c-111">05.25.2021</span></span>

- <span data-ttu-id="3660c-112">Adicionados novos métodos de avaliação de exportação de API [e propriedades por dispositivo.](get-assessment-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="3660c-112">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="3660c-113">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="3660c-113">03.05.2021</span></span>

- <span data-ttu-id="3660c-114">Adicionada nova API: métodos e propriedades de atividade [de correção.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="3660c-114">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="3660c-115">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="3660c-115">10.02.2021</span></span>

- <span data-ttu-id="3660c-116">Adicionada nova API: [alertas de atualização em lotes.](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3660c-116">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="3660c-117">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="3660c-117">25.01.2021</span></span>

- <span data-ttu-id="3660c-118">Limitações de taxa atualizadas para [a API de Busca Avançada](run-advanced-query-api.md) de 15 a 45 solicitações por minuto.</span><span class="sxs-lookup"><span data-stu-id="3660c-118">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="3660c-119">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="3660c-119">21.01.2021</span></span>

- <span data-ttu-id="3660c-120">Adicionada nova API: [Encontre dispositivos por marca](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="3660c-120">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="3660c-121">Adicionada nova API: [Indicadores de importação](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="3660c-121">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="3660c-122">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="3660c-122">03.01.2021</span></span>

- <span data-ttu-id="3660c-123">Evidência de alerta atualizada: adicionadas ***detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** propriedades.</span><span class="sxs-lookup"><span data-stu-id="3660c-123">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="3660c-124">Entidade [Alerta Atualizada](alerts.md): adicionada a propriedade ***detectorId.***</span><span class="sxs-lookup"><span data-stu-id="3660c-124">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="3660c-125">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="3660c-125">15.12.2020</span></span>

- <span data-ttu-id="3660c-126">Entidade [Do dispositivo](machine.md) atualizada: adicionada a lista ***IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="3660c-126">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="3660c-127">Consulte [Listar dispositivos](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="3660c-127">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="3660c-128">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="3660c-128">04.11.2020</span></span>

- <span data-ttu-id="3660c-129">Adicionada nova API: [definir o valor do dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="3660c-129">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="3660c-130">Entidade [Device](machine.md) atualizada: adicionada a ***propriedade deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="3660c-130">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="3660c-131">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="3660c-131">01.09.2020</span></span>

- <span data-ttu-id="3660c-132">Opção adicionada para expandir a entidade Alert com suas evidências relacionadas.</span><span class="sxs-lookup"><span data-stu-id="3660c-132">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="3660c-133">Consulte [List Alerts](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="3660c-133">See [List Alerts](get-alerts.md).</span></span>
