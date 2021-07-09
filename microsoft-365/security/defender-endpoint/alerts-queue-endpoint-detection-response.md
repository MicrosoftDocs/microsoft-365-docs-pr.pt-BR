---
title: Fila de alertas em Microsoft 365 Defender
ms.reviewer: ''
description: Exibir e gerenciar os alertas que surgiram Microsoft 365 Defender
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: ed65c836e74d5394d3b291ca3ebb5e781e37afa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339557"
---
# <a name="alerts-queue-in-microsoft-365-defender"></a><span data-ttu-id="82416-103">Fila de alertas em Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82416-103">Alerts queue in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82416-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="82416-104">**Applies to:**</span></span>
- [<span data-ttu-id="82416-105">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="82416-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="82416-106">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="82416-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82416-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="82416-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="82416-108">Saiba como você pode exibir e gerenciar a fila para que você possa investigar efetivamente as ameaças vistas em entidades como dispositivos, arquivos ou contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="82416-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="82416-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="82416-109">In this section</span></span>
<span data-ttu-id="82416-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="82416-110">Topic</span></span> | <span data-ttu-id="82416-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="82416-111">Description</span></span> 
:---|:---
[<span data-ttu-id="82416-112">Exibir e organizar a Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="82416-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="82416-113">Mostra uma lista de alertas que foram sinalizados em sua rede.</span><span class="sxs-lookup"><span data-stu-id="82416-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="82416-114">Gerenciar alertas</span><span class="sxs-lookup"><span data-stu-id="82416-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="82416-115">Saiba mais sobre como gerenciar alertas, como alterar seu status, atribuí-lo a um membro de operações de segurança e ver o histórico de um alerta.</span><span class="sxs-lookup"><span data-stu-id="82416-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="82416-116">Investigar alertas</span><span class="sxs-lookup"><span data-stu-id="82416-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="82416-117">Investigue alertas que estão afetando sua rede, entenda o que significam e como resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="82416-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="82416-118">Investigar arquivos</span><span class="sxs-lookup"><span data-stu-id="82416-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="82416-119">Investigue os detalhes de um arquivo associado a um alerta, comportamento ou evento específico.</span><span class="sxs-lookup"><span data-stu-id="82416-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="82416-120">Investigar dispositivos</span><span class="sxs-lookup"><span data-stu-id="82416-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="82416-121">Investigue os detalhes de um dispositivo associado a um alerta, comportamento ou evento específico.</span><span class="sxs-lookup"><span data-stu-id="82416-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="82416-122">Investigar um endereço IP</span><span class="sxs-lookup"><span data-stu-id="82416-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="82416-123">Examine a possível comunicação entre dispositivos em sua rede e endereços IP (protocolo IP) externos.</span><span class="sxs-lookup"><span data-stu-id="82416-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="82416-124">Investigar um domínio</span><span class="sxs-lookup"><span data-stu-id="82416-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="82416-125">Investigue um domínio para ver se dispositivos e servidores em sua rede estão se comunicando com um domínio mal-intencionado conhecido.</span><span class="sxs-lookup"><span data-stu-id="82416-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="82416-126">Investigar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="82416-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="82416-127">Identifique as contas de usuário com os alertas mais ativos e investigue casos de credenciais potencialmente comprometidas.</span><span class="sxs-lookup"><span data-stu-id="82416-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


