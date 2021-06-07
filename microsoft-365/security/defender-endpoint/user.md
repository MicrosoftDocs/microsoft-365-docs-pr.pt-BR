---
title: Tipo de recurso do usuário
description: Recupere alertas recentes do Microsoft Defender para Ponto de Extremidade relacionados aos usuários.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
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
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772132"
---
# <a name="user-resource-type"></a><span data-ttu-id="1b1dc-104">Tipo de recurso do usuário</span><span class="sxs-lookup"><span data-stu-id="1b1dc-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b1dc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1b1dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="1b1dc-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1b1dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1b1dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b1dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1b1dc-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1b1dc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1b1dc-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1b1dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="1b1dc-110">Método</span><span class="sxs-lookup"><span data-stu-id="1b1dc-110">Method</span></span>|<span data-ttu-id="1b1dc-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="1b1dc-111">Return Type</span></span> |<span data-ttu-id="1b1dc-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b1dc-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1b1dc-113">Listar alertas relacionados ao usuário</span><span class="sxs-lookup"><span data-stu-id="1b1dc-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="1b1dc-114">conjunto [alerta](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="1b1dc-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="1b1dc-115">Listar todos os alertas associados a um [usuário](user.md).</span><span class="sxs-lookup"><span data-stu-id="1b1dc-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="1b1dc-116">Listar dispositivos relacionados ao usuário</span><span class="sxs-lookup"><span data-stu-id="1b1dc-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="1b1dc-117">[coleção machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="1b1dc-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="1b1dc-118">Listar todos os dispositivos que foram conectados por um [usuário](user.md).</span><span class="sxs-lookup"><span data-stu-id="1b1dc-118">List all the devices that were logged on by a [user](user.md).</span></span>
