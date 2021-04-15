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
ms.topic: how-to
ms.openlocfilehash: 95c87330eec3cb557e5fea96148d626b7e0ee4b3
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768909"
---
# <a name="protect-your-network"></a><span data-ttu-id="089f2-104">Proteger sua rede</span><span class="sxs-lookup"><span data-stu-id="089f2-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="089f2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="089f2-105">**Applies to:**</span></span>
- [<span data-ttu-id="089f2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="089f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="089f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="089f2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="089f2-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="089f2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="089f2-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="089f2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="089f2-110">A proteção de rede ajuda a reduzir a superfície de ataque de seus dispositivos de eventos baseados na Internet.</span><span class="sxs-lookup"><span data-stu-id="089f2-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="089f2-111">Ele impede que os funcionários usem qualquer aplicativo para acessar domínios perigosos que possam hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet.</span><span class="sxs-lookup"><span data-stu-id="089f2-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="089f2-112">A proteção de rede expande o escopo do [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo o tráfego HTTP de saída que tenta se conectar a fontes de baixa reputação (com base no domínio ou nome do host).</span><span class="sxs-lookup"><span data-stu-id="089f2-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="089f2-113">A proteção de rede é suportada no Windows, começando com o Windows 10, versão 1709.</span><span class="sxs-lookup"><span data-stu-id="089f2-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="089f2-114">A proteção de rede ainda não é suportada em outros sistemas operacionais, mas a proteção da Web é suportada usando o novo Microsoft Edge com base no Chromium.</span><span class="sxs-lookup"><span data-stu-id="089f2-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="089f2-115">Para saber mais, confira [Proteção da Web](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="089f2-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="089f2-116">A proteção de rede amplia a proteção na [Web para](web-protection-overview.md) o nível do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="089f2-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="089f2-117">Ele fornece a funcionalidade de proteção da Web no Edge para outros navegadores com suporte e aplicativos que não são navegadores.</span><span class="sxs-lookup"><span data-stu-id="089f2-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="089f2-118">Além disso, a proteção de rede fornece visibilidade e bloqueio de indicadores de comprometimento (IOCs) quando usado com detecção e resposta do ponto [de extremidade.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="089f2-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="089f2-119">Por exemplo, a proteção de rede funciona com seus [indicadores personalizados.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="089f2-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="089f2-120">Para obter mais informações sobre como habilitar a proteção de rede, consulte [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="089f2-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="089f2-121">Use A Política de Grupo, PowerShell ou CSPs MDM para habilitar e gerenciar a proteção de rede em sua rede.</span><span class="sxs-lookup"><span data-stu-id="089f2-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="089f2-122">Consulte o site de plano de teste do Microsoft Defender ATP no demo.wd.microsoft.com [para](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ver como funciona a proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="089f2-122">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="089f2-123">A proteção de rede funciona melhor com o [Microsoft Defender para Ponto](microsoft-defender-endpoint.md)de Extremidade, que fornece relatórios detalhados sobre eventos e bloqueios de proteção de exploração como parte dos cenários de investigação de [alerta.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="089f2-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="089f2-124">Quando a proteção de rede bloqueia uma conexão, uma notificação é exibida do Centro de Ações.</span><span class="sxs-lookup"><span data-stu-id="089f2-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="089f2-125">Sua equipe de operações de segurança [pode personalizar a notificação](customize-attack-surface-reduction.md#customize-the-notification) com os detalhes e informações de contato da sua organização.</span><span class="sxs-lookup"><span data-stu-id="089f2-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="089f2-126">Além disso, as regras individuais de redução de superfície de ataque podem ser habilitadas e personalizadas para se adequar a determinadas técnicas a serem monitoradas.</span><span class="sxs-lookup"><span data-stu-id="089f2-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="089f2-127">Você também pode usar [o modo de auditoria](audit-windows-defender.md) para avaliar como a proteção de rede afetaria sua organização se ela estivesse habilitada.</span><span class="sxs-lookup"><span data-stu-id="089f2-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="089f2-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="089f2-128">Requirements</span></span>

<span data-ttu-id="089f2-129">A proteção de rede exige proteção em tempo real do Windows 10 Pro ou Enterprise e do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="089f2-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="089f2-130">Versão do Windows</span><span class="sxs-lookup"><span data-stu-id="089f2-130">Windows version</span></span> | <span data-ttu-id="089f2-131">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="089f2-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="089f2-132">Windows 10 versão 1709 ou posterior</span><span class="sxs-lookup"><span data-stu-id="089f2-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="089f2-133">Windows Server 1803 ou posterior</span><span class="sxs-lookup"><span data-stu-id="089f2-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="089f2-134">[A proteção em tempo real](configure-real-time-protection-microsoft-defender-antivirus.md) do Microsoft Defender Antivírus e a proteção entregue na [nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) devem estar habilitadas</span><span class="sxs-lookup"><span data-stu-id="089f2-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="089f2-135">Depois de habilitar os serviços, talvez seja necessário configurar sua rede ou firewall para permitir as conexões entre os serviços e seus dispositivos (também chamados de pontos de extremidade).</span><span class="sxs-lookup"><span data-stu-id="089f2-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="089f2-136">Revisar eventos de proteção de rede no Centro de Segurança do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="089f2-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="089f2-137">O Microsoft Defender para Ponto de Extremidade fornece relatórios detalhados sobre eventos e blocos como parte de seus cenários de investigação [de alerta.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="089f2-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="089f2-138">Você pode consultar dados do Microsoft Defender para o Ponto de Extremidade usando [a busca avançada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="089f2-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="089f2-139">Se você estiver usando o modo [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para ver como as configurações de proteção de rede afetariam seu ambiente se elas fossem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="089f2-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="089f2-140">Aqui está uma consulta de exemplo</span><span class="sxs-lookup"><span data-stu-id="089f2-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="089f2-141">Revisar eventos de proteção de rede no Visualizador de Eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="089f2-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="089f2-142">Você pode revisar o log de eventos do Windows para ver eventos criados quando a proteção de rede bloqueia (ou audita) o acesso a um IP ou domínio mal-intencionado:</span><span class="sxs-lookup"><span data-stu-id="089f2-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="089f2-143">[Copie o XML diretamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="089f2-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="089f2-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="089f2-144">Select **OK**.</span></span>

<span data-ttu-id="089f2-145">Este procedimento cria uma exibição personalizada que filtra apenas os seguintes eventos relacionados à proteção de rede:</span><span class="sxs-lookup"><span data-stu-id="089f2-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="089f2-146">ID de evento</span><span class="sxs-lookup"><span data-stu-id="089f2-146">Event ID</span></span> | <span data-ttu-id="089f2-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="089f2-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="089f2-148">5007</span><span class="sxs-lookup"><span data-stu-id="089f2-148">5007</span></span> | <span data-ttu-id="089f2-149">Evento quando as configurações são alteradas</span><span class="sxs-lookup"><span data-stu-id="089f2-149">Event when settings are changed</span></span> |
| <span data-ttu-id="089f2-150">1125</span><span class="sxs-lookup"><span data-stu-id="089f2-150">1125</span></span> | <span data-ttu-id="089f2-151">Evento quando a proteção de rede é a incêndio no modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="089f2-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="089f2-152">1126</span><span class="sxs-lookup"><span data-stu-id="089f2-152">1126</span></span> | <span data-ttu-id="089f2-153">Evento quando a proteção de rede dispara no modo de bloqueio</span><span class="sxs-lookup"><span data-stu-id="089f2-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="089f2-154">Considerações sobre a área de trabalho virtual do Windows executando o Windows 10 Enterprise Multi-Session</span><span class="sxs-lookup"><span data-stu-id="089f2-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="089f2-155">Devido à natureza multiusuária do Windows 10 Enterprise, lembre-se dos seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="089f2-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="089f2-156">A proteção de rede é um recurso em todo o dispositivo e não pode ser direcionada a sessões de usuário específicas.</span><span class="sxs-lookup"><span data-stu-id="089f2-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="089f2-157">As políticas de filtragem de conteúdo da Web também têm largura de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="089f2-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="089f2-158">Se você precisar diferenciar entre grupos de usuários, considere criar pools de host e atribuições separados da Área de Trabalho Virtual do Windows.</span><span class="sxs-lookup"><span data-stu-id="089f2-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="089f2-159">Teste a proteção de rede no modo de auditoria para avaliar seu comportamento antes de ser implantada.</span><span class="sxs-lookup"><span data-stu-id="089f2-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="089f2-160">Considere resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span><span class="sxs-lookup"><span data-stu-id="089f2-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="089f2-161">Opção alternativa para proteção de rede</span><span class="sxs-lookup"><span data-stu-id="089f2-161">Alternative option for network protection</span></span>

<span data-ttu-id="089f2-162">Para Windows 10 Enterprise Multi-Session 1909 e para cima, usado na Área de Trabalho Virtual do Windows no Azure, a proteção de rede para o Microsoft Edge pode ser habilitada usando o seguinte método:</span><span class="sxs-lookup"><span data-stu-id="089f2-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="089f2-163">Use [Ativar a proteção de rede](enable-network-protection.md) e siga as instruções para aplicar sua política.</span><span class="sxs-lookup"><span data-stu-id="089f2-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="089f2-164">Execute o seguinte comando do PowerShell: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="089f2-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="089f2-165">Solução de problemas de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="089f2-165">Network protection troubleshooting</span></span>

<span data-ttu-id="089f2-166">Devido ao ambiente em que a Proteção de Rede é executado, a Microsoft pode não ser capaz de detectar configurações de proxy do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="089f2-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="089f2-167">Em alguns casos, os clientes de proteção de rede não conseguem alcançar o Serviço de Nuvem.</span><span class="sxs-lookup"><span data-stu-id="089f2-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="089f2-168">Para resolver o problema de conectividade, os clientes com licenças do E5 devem configurar uma das seguintes chaves do Registro do Defender:</span><span class="sxs-lookup"><span data-stu-id="089f2-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="089f2-169">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="089f2-169">Related articles</span></span>

- <span data-ttu-id="089f2-170">[Avaliar a proteção](evaluate-network-protection.md) de rede | Empreenda um cenário rápido que demonstra como o recurso funciona e quais eventos normalmente seriam criados.</span><span class="sxs-lookup"><span data-stu-id="089f2-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="089f2-171">[Habilitar a proteção](enable-network-protection.md) de rede | Use A Política de Grupo, PowerShell ou CSPs MDM para habilitar e gerenciar a proteção de rede em sua rede.</span><span class="sxs-lookup"><span data-stu-id="089f2-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
