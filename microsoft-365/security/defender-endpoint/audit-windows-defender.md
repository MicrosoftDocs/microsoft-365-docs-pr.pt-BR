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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985091"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8c61a-104">Testar a redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8c61a-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c61a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8c61a-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c61a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8c61a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8c61a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c61a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8c61a-108">Como parte da equipe de segurança da sua organização, você pode configurar recursos de redução de superfície de ataque para executar no modo de auditoria para ver como eles funcionarão.</span><span class="sxs-lookup"><span data-stu-id="8c61a-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="8c61a-109">No modo de auditoria, você pode habilitar:</span><span class="sxs-lookup"><span data-stu-id="8c61a-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="8c61a-110">Regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="8c61a-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="8c61a-111">Proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="8c61a-111">Exploit protection</span></span>
- <span data-ttu-id="8c61a-112">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="8c61a-112">Network protection</span></span>
- <span data-ttu-id="8c61a-113">E acesso controlado a pastas no modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="8c61a-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="8c61a-114">O modo de auditoria permite que você veja um registro do *que teria* ocorrido se você tivesse habilitado o recurso.</span><span class="sxs-lookup"><span data-stu-id="8c61a-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="8c61a-115">Você pode habilitar o modo de auditoria ao testar como os recursos funcionarão.</span><span class="sxs-lookup"><span data-stu-id="8c61a-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="8c61a-116">Isso ajudará a garantir que seus aplicativos de linha de negócios não sejam afetados.</span><span class="sxs-lookup"><span data-stu-id="8c61a-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="8c61a-117">Você também pode ter uma ideia de quantas tentativas suspeitas de modificação de arquivo ocorrem em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="8c61a-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="8c61a-118">Os recursos não bloquearão ou impedirão que aplicativos, scripts ou arquivos seja modificado.</span><span class="sxs-lookup"><span data-stu-id="8c61a-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="8c61a-119">No entanto, o Windows log de eventos registrará eventos como se os recursos fossem totalmente habilitados.</span><span class="sxs-lookup"><span data-stu-id="8c61a-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="8c61a-120">Com o modo de auditoria, você pode revisar o log de eventos para ver o que afetaria o recurso se ele estivesse habilitado.</span><span class="sxs-lookup"><span data-stu-id="8c61a-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="8c61a-121">Para encontrar as entradas auditadas, acesse **Aplicativos e Serviços**  >  **microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="8c61a-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="8c61a-122">Use o Defender para o Ponto de Extremidade para obter maiores detalhes para cada evento, especialmente para investigar regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="8c61a-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="8c61a-123">Usar o console defender para ponto de extremidade permite investigar problemas como parte da linha do tempo de alerta [e cenários de investigação.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8c61a-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="8c61a-124">Você pode habilitar o modo de auditoria usando a Política de Grupo, o PowerShell e os provedores de serviços de configuração (CSPs).</span><span class="sxs-lookup"><span data-stu-id="8c61a-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="8c61a-125">Você também pode visitar o site Windows Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Testground no demo.wd.microsoft.com para confirmar se os recursos estão funcionando e ver como eles funcionam.</span><span class="sxs-lookup"><span data-stu-id="8c61a-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="8c61a-126">Opções de auditoria</span><span class="sxs-lookup"><span data-stu-id="8c61a-126">Audit options</span></span> | <span data-ttu-id="8c61a-127">Como habilitar o modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="8c61a-127">How to enable audit mode</span></span> | <span data-ttu-id="8c61a-128">Como exibir eventos</span><span class="sxs-lookup"><span data-stu-id="8c61a-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="8c61a-129">Auditoria se aplica a todos os eventos</span><span class="sxs-lookup"><span data-stu-id="8c61a-129">Audit applies to all events</span></span> | [<span data-ttu-id="8c61a-130">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="8c61a-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="8c61a-131">Eventos de acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="8c61a-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="8c61a-132">Auditoria se aplica a regras individuais</span><span class="sxs-lookup"><span data-stu-id="8c61a-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="8c61a-133">Habilitar regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="8c61a-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="8c61a-134">Eventos de regra de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="8c61a-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="8c61a-135">Auditoria se aplica a todos os eventos</span><span class="sxs-lookup"><span data-stu-id="8c61a-135">Audit applies to all events</span></span> | [<span data-ttu-id="8c61a-136">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="8c61a-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="8c61a-137">Eventos de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="8c61a-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="8c61a-138">A auditoria se aplica a mitigações individuais</span><span class="sxs-lookup"><span data-stu-id="8c61a-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="8c61a-139">Habilitar a proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="8c61a-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="8c61a-140">Explorar eventos de proteção</span><span class="sxs-lookup"><span data-stu-id="8c61a-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
