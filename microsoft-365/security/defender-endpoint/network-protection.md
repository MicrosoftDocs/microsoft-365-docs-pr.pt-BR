---
title: Usar a proteção de rede para ajudar a evitar conexões com sites ruins
description: Proteja sua rede impedindo que os usuários acessem endereços de rede mal-intencionados e suspeitos conhecidos
keywords: Proteção de rede, explorações, site mal-intencionado, ip, domínio, domínios
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
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644495"
---
# <a name="protect-your-network"></a><span data-ttu-id="35b1e-104">Proteger sua rede</span><span class="sxs-lookup"><span data-stu-id="35b1e-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35b1e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="35b1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="35b1e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="35b1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35b1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35b1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="35b1e-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="35b1e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35b1e-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="35b1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="35b1e-110">A proteção de rede ajuda a reduzir a superfície de ataque de seus dispositivos de eventos baseados na Internet.</span><span class="sxs-lookup"><span data-stu-id="35b1e-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="35b1e-111">Ele impede que os funcionários usem qualquer aplicativo para acessar domínios perigosos que possam hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet.</span><span class="sxs-lookup"><span data-stu-id="35b1e-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="35b1e-112">A proteção de rede expande o escopo do [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo o tráfego HTTP de saída que tenta se conectar a fontes de baixa reputação (com base no domínio ou nome do host).</span><span class="sxs-lookup"><span data-stu-id="35b1e-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="35b1e-113">A proteção de rede é suportada no Windows, começando com o Windows 10, versão 1709.</span><span class="sxs-lookup"><span data-stu-id="35b1e-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="35b1e-114">Para obter mais informações sobre como habilitar a proteção de rede, consulte [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="35b1e-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="35b1e-115">Use A Política de Grupo, PowerShell ou CSPs MDM para habilitar e gerenciar a proteção de rede em sua rede.</span><span class="sxs-lookup"><span data-stu-id="35b1e-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="35b1e-116">Consulte o site de plano de teste do Microsoft Defender ATP no demo.wd.microsoft.com [para](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ver como funciona a proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="35b1e-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="35b1e-117">A proteção de rede funciona melhor com o [Microsoft Defender para Ponto](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)de Extremidade, que fornece relatórios detalhados sobre eventos e bloqueios de proteção de exploração como parte dos cenários de investigação de [alerta.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="35b1e-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="35b1e-118">Quando a proteção de rede bloqueia uma conexão, uma notificação é exibida do Centro de Ações.</span><span class="sxs-lookup"><span data-stu-id="35b1e-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="35b1e-119">Sua equipe de operações de segurança [pode personalizar a notificação](customize-attack-surface-reduction.md#customize-the-notification) com os detalhes e informações de contato da sua organização.</span><span class="sxs-lookup"><span data-stu-id="35b1e-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="35b1e-120">Além disso, as regras individuais de redução de superfície de ataque podem ser habilitadas e personalizadas para se adequar a determinadas técnicas a serem monitoradas.</span><span class="sxs-lookup"><span data-stu-id="35b1e-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="35b1e-121">Você também pode usar [o modo de auditoria](audit-windows-defender.md) para avaliar como a proteção de rede afetaria sua organização se ela estivesse habilitada.</span><span class="sxs-lookup"><span data-stu-id="35b1e-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="35b1e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35b1e-122">Requirements</span></span>

<span data-ttu-id="35b1e-123">A proteção de rede exige proteção em tempo real do Windows 10 Pro ou Enterprise e do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="35b1e-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="35b1e-124">Versão do Windows</span><span class="sxs-lookup"><span data-stu-id="35b1e-124">Windows version</span></span> | <span data-ttu-id="35b1e-125">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="35b1e-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="35b1e-126">Windows 10 versão 1709 ou posterior</span><span class="sxs-lookup"><span data-stu-id="35b1e-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="35b1e-127">Windows Server 1803 ou posterior</span><span class="sxs-lookup"><span data-stu-id="35b1e-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="35b1e-128">[A proteção em tempo real](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) do Microsoft Defender Antivírus e a proteção entregue na [nuvem](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) devem estar habilitadas</span><span class="sxs-lookup"><span data-stu-id="35b1e-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="35b1e-129">Depois de habilitar os serviços, talvez seja necessário configurar sua rede ou firewall para permitir as conexões entre os serviços e seus dispositivos (também chamados de pontos de extremidade).</span><span class="sxs-lookup"><span data-stu-id="35b1e-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="35b1e-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="35b1e-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="35b1e-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="35b1e-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="35b1e-132">Revisar eventos de proteção de rede no Centro de Segurança do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="35b1e-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="35b1e-133">O Microsoft Defender para Ponto de Extremidade fornece relatórios detalhados sobre eventos e blocos como parte de seus cenários de investigação [de alerta.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="35b1e-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="35b1e-134">Você pode consultar dados do Microsoft Defender para o Ponto de Extremidade usando [a busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="35b1e-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="35b1e-135">Se você estiver usando o modo [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para ver como as configurações de proteção de rede afetariam seu ambiente se elas fossem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="35b1e-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="35b1e-136">Aqui está uma consulta de exemplo</span><span class="sxs-lookup"><span data-stu-id="35b1e-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="35b1e-137">Revisar eventos de proteção de rede no Visualizador de Eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="35b1e-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="35b1e-138">Você pode revisar o log de eventos do Windows para ver eventos criados quando a proteção de rede bloqueia (ou audita) o acesso a um IP ou domínio mal-intencionado:</span><span class="sxs-lookup"><span data-stu-id="35b1e-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="35b1e-139">[Copie o XML diretamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="35b1e-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="35b1e-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="35b1e-140">Select **OK**.</span></span>

<span data-ttu-id="35b1e-141">Este procedimento cria uma exibição personalizada que filtra apenas os seguintes eventos relacionados à proteção de rede:</span><span class="sxs-lookup"><span data-stu-id="35b1e-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="35b1e-142">ID de evento</span><span class="sxs-lookup"><span data-stu-id="35b1e-142">Event ID</span></span> | <span data-ttu-id="35b1e-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="35b1e-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="35b1e-144">5007</span><span class="sxs-lookup"><span data-stu-id="35b1e-144">5007</span></span> | <span data-ttu-id="35b1e-145">Evento quando as configurações são alteradas</span><span class="sxs-lookup"><span data-stu-id="35b1e-145">Event when settings are changed</span></span> |
| <span data-ttu-id="35b1e-146">1125</span><span class="sxs-lookup"><span data-stu-id="35b1e-146">1125</span></span> | <span data-ttu-id="35b1e-147">Evento quando a proteção de rede é a incêndio no modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="35b1e-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="35b1e-148">1126</span><span class="sxs-lookup"><span data-stu-id="35b1e-148">1126</span></span> | <span data-ttu-id="35b1e-149">Evento quando a proteção de rede dispara no modo de bloqueio</span><span class="sxs-lookup"><span data-stu-id="35b1e-149">Event when network protection fires in block mode</span></span> |

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="35b1e-150">Solução de problemas de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="35b1e-150">Network protection troubleshooting</span></span>

<span data-ttu-id="35b1e-151">Devido ao ambiente em que a Proteção de Rede é executado, a Microsoft pode não ser capaz de detectar configurações de proxy do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="35b1e-151">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="35b1e-152">Em alguns casos, os clientes de Proteção de Rede não conseguem alcançar o Serviço de Nuvem.</span><span class="sxs-lookup"><span data-stu-id="35b1e-152">In some cases, Network Protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="35b1e-153">Para resolver o problema de conectividade, os clientes com licenças do E5 devem configurar uma das seguintes chaves do Registro do Defender:</span><span class="sxs-lookup"><span data-stu-id="35b1e-153">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="35b1e-154">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="35b1e-154">Related articles</span></span>

- <span data-ttu-id="35b1e-155">[Avaliar a proteção](evaluate-network-protection.md) de rede | Empreenda um cenário rápido que demonstra como o recurso funciona e quais eventos normalmente seriam criados.</span><span class="sxs-lookup"><span data-stu-id="35b1e-155">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="35b1e-156">[Habilitar a proteção](enable-network-protection.md) de rede | Use A Política de Grupo, PowerShell ou CSPs MDM para habilitar e gerenciar a proteção de rede em sua rede.</span><span class="sxs-lookup"><span data-stu-id="35b1e-156">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
