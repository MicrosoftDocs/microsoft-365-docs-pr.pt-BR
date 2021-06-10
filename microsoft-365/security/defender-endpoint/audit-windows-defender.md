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
ms.openlocfilehash: e78b21b751aa398ed4449fb398f12b60f1929873
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866671"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Testar a redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se você faz parte da equipe de segurança da sua organização, pode configurar recursos de redução de superfície de ataque para executar no modo de auditoria para ver como eles funcionarão em sua organização. Em particular, você pode habilitar regras de redução de superfície de ataque, proteção de exploração, proteção de rede e acesso controlado a pastas no modo de auditoria. O modo de auditoria permite que você veja um registro do *que teria* ocorrido se você tivesse habilitado o recurso.

Talvez você queira habilitar o modo de auditoria ao testar como os recursos funcionarão em sua organização. Isso ajudará a garantir que seus aplicativos de linha de negócios não sejam afetados. Você também pode ter uma ideia de quantas tentativas suspeitas de modificação de arquivo ocorrem em um determinado período de tempo.

Os recursos não bloquearão ou impedirão que aplicativos, scripts ou arquivos seja modificado. No entanto, o Windows log de eventos registrará eventos como se os recursos fossem totalmente habilitados. Com o modo de auditoria, você pode revisar o log de eventos para ver o impacto que o recurso teria se ele estivesse habilitado.

Para encontrar as entradas auditadas, acesse **Aplicativos e Serviços**  >  **microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operacional**.

Você pode usar o Defender para o Ponto de Extremidade para obter maiores detalhes para cada evento, especialmente para investigar regras de redução de superfície de ataque. Usar o console defender para ponto de extremidade permite investigar problemas como parte da linha do tempo de alerta [e cenários de investigação.](investigate-alerts.md)

Você pode usar a Política de Grupo, o PowerShell e os provedores de serviços de configuração (CSPs) para habilitar o modo de auditoria.

> [!TIP]
> Você também pode visitar o site Windows Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Testground no demo.wd.microsoft.com para confirmar se os recursos estão funcionando e ver como eles funcionam.

| Opções de auditoria | Como habilitar o modo de auditoria | Como exibir eventos |
|---------|---------|---------|
| Auditoria se aplica a todos os eventos | [Habilitar o acesso controlado a pastas](enable-controlled-folders.md) | [Eventos de acesso controlado a pastas](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Auditoria se aplica a regras individuais | [Habilitar regras da redução da superfície de ataque](enable-attack-surface-reduction.md) | [Eventos de regra de redução de superfície de ataque](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Auditoria se aplica a todos os eventos | [Habilitar a proteção de rede](enable-network-protection.md) | [Eventos de proteção de rede](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| A auditoria se aplica a mitigações individuais | [Habilitar a proteção de exploração](enable-exploit-protection.md) | [Explorar eventos de proteção](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


