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
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197952"
---
# <a name="user-resource-type"></a><span data-ttu-id="d7722-104">Tipo de recurso do usuário</span><span class="sxs-lookup"><span data-stu-id="d7722-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7722-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d7722-105">**Applies to:**</span></span>
- [<span data-ttu-id="d7722-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d7722-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d7722-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7722-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d7722-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d7722-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d7722-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d7722-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="d7722-110">Método</span><span class="sxs-lookup"><span data-stu-id="d7722-110">Method</span></span>|<span data-ttu-id="d7722-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="d7722-111">Return Type</span></span> |<span data-ttu-id="d7722-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7722-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d7722-113">Listar alertas relacionados ao usuário</span><span class="sxs-lookup"><span data-stu-id="d7722-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="d7722-114">conjunto [alerta](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="d7722-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="d7722-115">Listar todos os alertas associados a um [usuário](user.md).</span><span class="sxs-lookup"><span data-stu-id="d7722-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="d7722-116">Listar dispositivos relacionados ao usuário</span><span class="sxs-lookup"><span data-stu-id="d7722-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="d7722-117">[coleção machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="d7722-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="d7722-118">Listar todos os dispositivos que foram conectados por um [usuário](user.md).</span><span class="sxs-lookup"><span data-stu-id="d7722-118">List all the devices that were logged on by a [user](user.md).</span></span>
