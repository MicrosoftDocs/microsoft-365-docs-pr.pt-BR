---
title: Testar como o Microsoft Defender para recursos do Ponto de Extremidade funciona no modo de auditoria
description: O modo de auditoria ajuda você a ver como o Microsoft Defender para Ponto de Extremidade protegeria seus dispositivos se ele estivesse habilitado.
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570967"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="d15a5-104">Testar como o Microsoft Defender para recursos do Ponto de Extremidade funciona no modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="d15a5-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d15a5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d15a5-105">**Applies to:**</span></span>
- [<span data-ttu-id="d15a5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d15a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d15a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d15a5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="d15a5-108">Você pode habilitar regras de redução de superfície de ataque, proteção de exploração, proteção de rede e acesso controlado a pastas no modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d15a5-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="d15a5-109">O modo de auditoria permite que você veja um registro do *que teria* ocorrido se você tivesse habilitado o recurso.</span><span class="sxs-lookup"><span data-stu-id="d15a5-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="d15a5-110">Talvez você queira habilitar o modo de auditoria ao testar como os recursos funcionarão em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d15a5-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="d15a5-111">Isso ajudará a garantir que seus aplicativos de linha de negócios não sejam afetados.</span><span class="sxs-lookup"><span data-stu-id="d15a5-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="d15a5-112">Você também pode ter uma ideia de quantas tentativas suspeitas de modificação de arquivo ocorrem em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="d15a5-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="d15a5-113">Os recursos não bloquearão ou impedirão que aplicativos, scripts ou arquivos seja modificado.</span><span class="sxs-lookup"><span data-stu-id="d15a5-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="d15a5-114">No entanto, o Log de Eventos do Windows registrará eventos como se os recursos fossem totalmente habilitados.</span><span class="sxs-lookup"><span data-stu-id="d15a5-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="d15a5-115">Com o modo de auditoria, você pode revisar o log de eventos para ver o impacto que o recurso teria se ele estivesse habilitado.</span><span class="sxs-lookup"><span data-stu-id="d15a5-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="d15a5-116">Para encontrar as entradas auditadas, acesse **Aplicativos e Serviços**  >  **do Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="d15a5-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="d15a5-117">Você pode usar o Defender para o Ponto de Extremidade para obter maiores detalhes para cada evento, especialmente para investigar regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="d15a5-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="d15a5-118">Usar o console defender para ponto de extremidade permite investigar problemas como parte da linha do tempo de alerta [e cenários de investigação.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="d15a5-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="d15a5-119">Você pode usar a Política de Grupo, o PowerShell e os provedores de serviços de configuração (CSPs) para habilitar o modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d15a5-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="d15a5-120">Você também pode visitar o site Windows Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Testground no demo.wd.microsoft.com para confirmar se os recursos estão funcionando e ver como eles funcionam.</span><span class="sxs-lookup"><span data-stu-id="d15a5-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="d15a5-121">**Opções de auditoria**</span><span class="sxs-lookup"><span data-stu-id="d15a5-121">**Audit options**</span></span> | <span data-ttu-id="d15a5-122">**Como habilitar o modo de auditoria**</span><span class="sxs-lookup"><span data-stu-id="d15a5-122">**How to enable audit mode**</span></span> | <span data-ttu-id="d15a5-123">**Como exibir eventos**</span><span class="sxs-lookup"><span data-stu-id="d15a5-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="d15a5-124">Auditoria se aplica a todos os eventos</span><span class="sxs-lookup"><span data-stu-id="d15a5-124">Audit applies to all events</span></span> | [<span data-ttu-id="d15a5-125">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="d15a5-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="d15a5-126">Eventos de acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="d15a5-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="d15a5-127">Auditoria se aplica a regras individuais</span><span class="sxs-lookup"><span data-stu-id="d15a5-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="d15a5-128">Habilitar regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="d15a5-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="d15a5-129">Eventos de regra de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="d15a5-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="d15a5-130">Auditoria se aplica a todos os eventos</span><span class="sxs-lookup"><span data-stu-id="d15a5-130">Audit applies to all events</span></span> | [<span data-ttu-id="d15a5-131">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="d15a5-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="d15a5-132">Eventos de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="d15a5-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="d15a5-133">A auditoria se aplica a mitigações individuais</span><span class="sxs-lookup"><span data-stu-id="d15a5-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="d15a5-134">Habilitar a proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="d15a5-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="d15a5-135">Explorar eventos de proteção</span><span class="sxs-lookup"><span data-stu-id="d15a5-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="d15a5-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d15a5-136">Related topics</span></span>

* [<span data-ttu-id="d15a5-137">Proteger dispositivos de explorações</span><span class="sxs-lookup"><span data-stu-id="d15a5-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="d15a5-138">Reduzir superfícies de ataque com regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="d15a5-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="d15a5-139">Proteger sua rede</span><span class="sxs-lookup"><span data-stu-id="d15a5-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="d15a5-140">Proteger pastas importantes</span><span class="sxs-lookup"><span data-stu-id="d15a5-140">Protect important folders</span></span>](controlled-folders.md)
