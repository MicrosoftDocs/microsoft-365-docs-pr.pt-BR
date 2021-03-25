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
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198643"
---
# <a name="protect-your-network"></a>Proteger sua rede

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

A proteção de rede ajuda a reduzir a superfície de ataque de seus dispositivos de eventos baseados na Internet. Ele impede que os funcionários usem qualquer aplicativo para acessar domínios perigosos que possam hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet. A proteção de rede expande o escopo do [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo o tráfego HTTP de saída que tenta se conectar a fontes de baixa reputação (com base no domínio ou nome do host).

A proteção de rede é suportada no Windows, começando com o Windows 10, versão 1709. 

Para obter mais informações sobre como habilitar a proteção de rede, consulte [Enable network protection](enable-network-protection.md). Use A Política de Grupo, PowerShell ou CSPs MDM para habilitar e gerenciar a proteção de rede em sua rede.

> [!TIP]
> Consulte o site de plano de teste do Microsoft Defender ATP no demo.wd.microsoft.com [para](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ver como funciona a proteção de rede.

A proteção de rede funciona melhor com o [Microsoft Defender para Ponto](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)de Extremidade, que fornece relatórios detalhados sobre eventos e bloqueios de proteção de exploração como parte dos cenários de investigação de [alerta.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Quando a proteção de rede bloqueia uma conexão, uma notificação é exibida do Centro de Ações. Sua equipe de operações de segurança [pode personalizar a notificação](customize-attack-surface-reduction.md#customize-the-notification) com os detalhes e informações de contato da sua organização. Além disso, as regras individuais de redução de superfície de ataque podem ser habilitadas e personalizadas para se adequar a determinadas técnicas a serem monitoradas.

Você também pode usar [o modo de auditoria](audit-windows-defender.md) para avaliar como a proteção de rede afetaria sua organização se ela estivesse habilitada.

## <a name="requirements"></a>Requisitos

A proteção de rede exige proteção em tempo real do Windows 10 Pro ou Enterprise e do Microsoft Defender Antivírus.

| Versão do Windows | Microsoft Defender Antivírus |
|:---|:---|
| Windows 10 versão 1709 ou posterior <p>Windows Server 1803 ou posterior | [A proteção em tempo real](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) do Microsoft Defender Antivírus e a proteção entregue na [nuvem](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) devem estar habilitadas |

Depois de habilitar os serviços, talvez seja necessário configurar sua rede ou firewall para permitir as conexões entre os serviços e seus dispositivos (também chamados de pontos de extremidade).  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Revisar eventos de proteção de rede no Centro de Segurança do Microsoft Defender para Ponto de Extremidade

O Microsoft Defender para Ponto de Extremidade fornece relatórios detalhados sobre eventos e blocos como parte de seus cenários de investigação [de alerta.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Você pode consultar dados do Microsoft Defender para o Ponto de Extremidade usando [a busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection). Se você estiver usando o modo [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para ver como as configurações de proteção de rede afetariam seu ambiente se elas fossem habilitadas.

Aqui está uma consulta de exemplo

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisar eventos de proteção de rede no Visualizador de Eventos do Windows

Você pode revisar o log de eventos do Windows para ver eventos criados quando a proteção de rede bloqueia (ou audita) o acesso a um IP ou domínio mal-intencionado:

1. [Copie o XML diretamente](event-views.md).

2. Selecione **OK**.

Este procedimento cria uma exibição personalizada que filtra apenas os seguintes eventos relacionados à proteção de rede:

| ID de evento | Descrição |
|:---|:---|
| 5007 | Evento quando as configurações são alteradas |
| 1125 | Evento quando a proteção de rede é a incêndio no modo de auditoria |
| 1126 | Evento quando a proteção de rede dispara no modo de bloqueio |

## <a name="related-articles"></a>Artigos relacionados

- [Avaliar a proteção](evaluate-network-protection.md) de rede | Empreenda um cenário rápido que demonstra como o recurso funciona e quais eventos normalmente seriam criados.

- [Habilitar a proteção](enable-network-protection.md) de rede | Use A Política de Grupo, PowerShell ou CSPs MDM para habilitar e gerenciar a proteção de rede em sua rede.
