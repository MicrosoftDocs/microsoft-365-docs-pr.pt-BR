---
title: Isolamento baseado em hardware (Windows 10)
ms.reviewer: ''
description: Saiba como o isolamento baseado em hardware no Windows 10 ajuda a combater malware.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052583"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="63a2b-103">Isolamento baseado em hardware no Windows 10</span><span class="sxs-lookup"><span data-stu-id="63a2b-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63a2b-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="63a2b-104">**Applies to:**</span></span>
- [<span data-ttu-id="63a2b-105">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="63a2b-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="63a2b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63a2b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="63a2b-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="63a2b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="63a2b-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="63a2b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="63a2b-109">O isolamento baseado em hardware ajuda a proteger a integridade do sistema no Windows 10 e é integrado ao Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="63a2b-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="63a2b-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="63a2b-110">Feature</span></span> | <span data-ttu-id="63a2b-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="63a2b-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="63a2b-112">Proteção de aplicativo do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="63a2b-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="63a2b-113">O Application Guard protege seu dispositivo contra ataques avançados enquanto o mantém produtivo.</span><span class="sxs-lookup"><span data-stu-id="63a2b-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="63a2b-114">Usando uma abordagem de isolamento baseada em hardware exclusiva, o objetivo é isolar sites não confiáveis e documentos PDF dentro de um contêiner leve que é separado do sistema operacional por meio do Windows Hypervisor nativo.</span><span class="sxs-lookup"><span data-stu-id="63a2b-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="63a2b-115">Se um site ou documento PDF não falso for mal-intencionado, ele ainda permanecerá contido no contêiner seguro do Application Guard, mantendo o computador da área de trabalho protegido e o invasor longe de seus dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="63a2b-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="63a2b-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="63a2b-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="63a2b-117">O System Guard protege e mantém a integridade do sistema à medida que ele é iniciado e depois de executado e valida a integridade do sistema usando atestado.</span><span class="sxs-lookup"><span data-stu-id="63a2b-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

