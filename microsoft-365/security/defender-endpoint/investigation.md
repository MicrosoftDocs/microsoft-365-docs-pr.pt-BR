---
title: Tipo de recurso de investigação
description: Entidade Microsoft Defender ATP Investigation.
keywords: apis, api gráfica, apis com suporte, obter, alertas, investigações
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187034"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="73d74-104">Tipo de recurso de investigação</span><span class="sxs-lookup"><span data-stu-id="73d74-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73d74-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="73d74-105">**Applies to:**</span></span>
- [<span data-ttu-id="73d74-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="73d74-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="73d74-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73d74-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="73d74-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="73d74-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="73d74-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="73d74-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="73d74-110">Represente uma entidade de Investigação Automatizada no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="73d74-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="73d74-111">Confira [Visão geral das investigações automatizadas](automated-investigations.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="73d74-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="73d74-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="73d74-112">Methods</span></span>
<span data-ttu-id="73d74-113">Método</span><span class="sxs-lookup"><span data-stu-id="73d74-113">Method</span></span>|<span data-ttu-id="73d74-114">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="73d74-114">Return Type</span></span> |<span data-ttu-id="73d74-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="73d74-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="73d74-116">List Investigations</span><span class="sxs-lookup"><span data-stu-id="73d74-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="73d74-117">Coleção Investigation</span><span class="sxs-lookup"><span data-stu-id="73d74-117">Investigation collection</span></span> | <span data-ttu-id="73d74-118">Obter coleção de Investigação</span><span class="sxs-lookup"><span data-stu-id="73d74-118">Get collection of Investigation</span></span>
[<span data-ttu-id="73d74-119">Obter investigação única</span><span class="sxs-lookup"><span data-stu-id="73d74-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="73d74-120">Entidade de investigação</span><span class="sxs-lookup"><span data-stu-id="73d74-120">Investigation entity</span></span> | <span data-ttu-id="73d74-121">Obtém uma única entidade De investigação.</span><span class="sxs-lookup"><span data-stu-id="73d74-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="73d74-122">Iniciar Investigação</span><span class="sxs-lookup"><span data-stu-id="73d74-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="73d74-123">Entidade de investigação</span><span class="sxs-lookup"><span data-stu-id="73d74-123">Investigation entity</span></span> | <span data-ttu-id="73d74-124">Inicia a investigação em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73d74-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="73d74-125">Propriedades</span><span class="sxs-lookup"><span data-stu-id="73d74-125">Properties</span></span>
<span data-ttu-id="73d74-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="73d74-126">Property</span></span> |  <span data-ttu-id="73d74-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="73d74-127">Type</span></span>    |   <span data-ttu-id="73d74-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="73d74-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="73d74-129">id</span><span class="sxs-lookup"><span data-stu-id="73d74-129">id</span></span> | <span data-ttu-id="73d74-130">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73d74-130">String</span></span> | <span data-ttu-id="73d74-131">Identidade da entidade de investigação.</span><span class="sxs-lookup"><span data-stu-id="73d74-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="73d74-132">startTime</span><span class="sxs-lookup"><span data-stu-id="73d74-132">startTime</span></span> | <span data-ttu-id="73d74-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="73d74-133">DateTime Nullable</span></span> | <span data-ttu-id="73d74-134">A data e a hora em que a investigação foi criada.</span><span class="sxs-lookup"><span data-stu-id="73d74-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="73d74-135">endTime</span><span class="sxs-lookup"><span data-stu-id="73d74-135">endTime</span></span> | <span data-ttu-id="73d74-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="73d74-136">DateTime Nullable</span></span> | <span data-ttu-id="73d74-137">A data e a hora em que a investigação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="73d74-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="73d74-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="73d74-138">cancelledBy</span></span> | <span data-ttu-id="73d74-139">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73d74-139">String</span></span> | <span data-ttu-id="73d74-140">A ID do usuário/aplicativo que cancelou essa investigação.</span><span class="sxs-lookup"><span data-stu-id="73d74-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="73d74-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="73d74-141">investigationState</span></span> | <span data-ttu-id="73d74-142">Enum</span><span class="sxs-lookup"><span data-stu-id="73d74-142">Enum</span></span> | <span data-ttu-id="73d74-143">O estado atual da investigação.</span><span class="sxs-lookup"><span data-stu-id="73d74-143">The current state of the investigation.</span></span> <span data-ttu-id="73d74-144">Os valores possíveis são: 'Unknown', 'Terminado', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="73d74-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="73d74-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="73d74-145">statusDetails</span></span> | <span data-ttu-id="73d74-146">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73d74-146">String</span></span> | <span data-ttu-id="73d74-147">Informações adicionais sobre o estado da investigação.</span><span class="sxs-lookup"><span data-stu-id="73d74-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="73d74-148">machineId</span><span class="sxs-lookup"><span data-stu-id="73d74-148">machineId</span></span> | <span data-ttu-id="73d74-149">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73d74-149">String</span></span> | <span data-ttu-id="73d74-150">A ID do dispositivo no qual a investigação é executada.</span><span class="sxs-lookup"><span data-stu-id="73d74-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="73d74-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="73d74-151">computerDnsName</span></span> | <span data-ttu-id="73d74-152">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73d74-152">String</span></span> | <span data-ttu-id="73d74-153">O nome do dispositivo no qual a investigação é executada.</span><span class="sxs-lookup"><span data-stu-id="73d74-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="73d74-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="73d74-154">triggeringAlertId</span></span> | <span data-ttu-id="73d74-155">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73d74-155">String</span></span> | <span data-ttu-id="73d74-156">A ID do alerta que disparou a investigação.</span><span class="sxs-lookup"><span data-stu-id="73d74-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="73d74-157">Representação Json</span><span class="sxs-lookup"><span data-stu-id="73d74-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
