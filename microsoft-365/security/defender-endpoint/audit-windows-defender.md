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
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769600"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="bd7e3-104">Testar a redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bd7e3-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd7e3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bd7e3-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd7e3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bd7e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bd7e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd7e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bd7e3-108">Se você faz parte da equipe de segurança da sua organização, pode configurar recursos de redução de superfície de ataque para executar no modo de auditoria para ver como eles funcionarão em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="bd7e3-109">Em particular, você pode habilitar regras de redução de superfície de ataque, proteção de exploração, proteção de rede e acesso controlado a pastas no modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="bd7e3-110">O modo de auditoria permite que você veja um registro do *que teria* ocorrido se você tivesse habilitado o recurso.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="bd7e3-111">Talvez você queira habilitar o modo de auditoria ao testar como os recursos funcionarão em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="bd7e3-112">Isso ajudará a garantir que seus aplicativos de linha de negócios não sejam afetados.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="bd7e3-113">Você também pode ter uma ideia de quantas tentativas suspeitas de modificação de arquivo ocorrem em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="bd7e3-114">Os recursos não bloquearão ou impedirão que aplicativos, scripts ou arquivos seja modificado.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="bd7e3-115">No entanto, o Windows log de eventos registrará eventos como se os recursos fossem totalmente habilitados.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="bd7e3-116">Com o modo de auditoria, você pode revisar o log de eventos para ver o impacto que o recurso teria se ele estivesse habilitado.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="bd7e3-117">Para encontrar as entradas auditadas, acesse **Aplicativos e Serviços**  >  **microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="bd7e3-118">Você pode usar o Defender para o Ponto de Extremidade para obter maiores detalhes para cada evento, especialmente para investigar regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="bd7e3-119">Usar o console defender para ponto de extremidade permite investigar problemas como parte da linha do tempo de alerta [e cenários de investigação.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bd7e3-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="bd7e3-120">Você pode usar a Política de Grupo, o PowerShell e os provedores de serviços de configuração (CSPs) para habilitar o modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="bd7e3-121">Você também pode visitar o site Windows Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Testground no demo.wd.microsoft.com para confirmar se os recursos estão funcionando e ver como eles funcionam.</span><span class="sxs-lookup"><span data-stu-id="bd7e3-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="bd7e3-122">**Opções de auditoria**</span><span class="sxs-lookup"><span data-stu-id="bd7e3-122">**Audit options**</span></span> | <span data-ttu-id="bd7e3-123">**Como habilitar o modo de auditoria**</span><span class="sxs-lookup"><span data-stu-id="bd7e3-123">**How to enable audit mode**</span></span> | <span data-ttu-id="bd7e3-124">**Como exibir eventos**</span><span class="sxs-lookup"><span data-stu-id="bd7e3-124">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="bd7e3-125">Auditoria se aplica a todos os eventos</span><span class="sxs-lookup"><span data-stu-id="bd7e3-125">Audit applies to all events</span></span> | [<span data-ttu-id="bd7e3-126">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="bd7e3-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="bd7e3-127">Eventos de acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="bd7e3-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="bd7e3-128">Auditoria se aplica a regras individuais</span><span class="sxs-lookup"><span data-stu-id="bd7e3-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="bd7e3-129">Habilitar regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="bd7e3-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="bd7e3-130">Eventos de regra de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="bd7e3-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="bd7e3-131">Auditoria se aplica a todos os eventos</span><span class="sxs-lookup"><span data-stu-id="bd7e3-131">Audit applies to all events</span></span> | [<span data-ttu-id="bd7e3-132">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="bd7e3-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="bd7e3-133">Eventos de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="bd7e3-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="bd7e3-134">A auditoria se aplica a mitigações individuais</span><span class="sxs-lookup"><span data-stu-id="bd7e3-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="bd7e3-135">Habilitar a proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="bd7e3-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="bd7e3-136">Explorar eventos de proteção</span><span class="sxs-lookup"><span data-stu-id="bd7e3-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


