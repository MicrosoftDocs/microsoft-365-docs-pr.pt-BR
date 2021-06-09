---
title: Investigar eventos de conexão que ocorrem por meio de proxies de encaminhamento
description: Saiba como usar o monitoramento avançado de nível HTTP por meio da proteção de rede no Microsoft Defender para Ponto de Extremidade, que apresenta um destino real, em vez de um proxy.
keywords: proxy, proteção de rede, proxy de encaminhamento, eventos de rede, auditoria, bloco, nomes de domínio, domínio
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 55c001781ff016d7a23dc5db286d454b39fac5de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841049"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Investigar eventos de conexão que ocorrem por meio de proxies de encaminhamento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

O Defender para Ponto de Extremidade oferece suporte ao monitoramento de conexão de rede de diferentes níveis da pilha de rede. Um caso desafiador é quando a rede usa um proxy de encaminhamento como um gateway para a Internet.

O proxy age como se fosse o ponto de extremidade de destino.  Nesses casos, os monitores de conexão de rede simples auditarão as conexões com o proxy que está correto, mas tem menor valor de investigação. 

O Defender for Endpoint oferece suporte ao monitoramento avançado de nível HTTP por meio da proteção de rede. Quando ligado, um novo tipo de evento é a superfície que expõe os nomes de domínio de destino reais.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Usar a proteção de rede para monitorar a conexão de rede atrás de um firewall
O monitoramento da conexão de rede por trás de um proxy de encaminhamento é possível devido a eventos de rede adicionais que se originam da proteção de rede. Para vê-los em uma linha do tempo do dispositivo, a ligue a proteção de rede (no mínimo no modo de auditoria). 

A proteção de rede pode ser controlada usando os seguintes modos:

- **Bloquear** <br> Os usuários ou aplicativos serão impedidos de se conectar a domínios perigosos. Você poderá ver essa atividade no Central de Segurança do Microsoft Defender.
- **Auditoria** <br> Os usuários ou aplicativos não serão impedidos de se conectar a domínios perigosos. No entanto, você ainda verá essa atividade no Central de Segurança do Microsoft Defender.


Se você desativar a proteção de rede, os usuários ou aplicativos não serão impedidos de se conectar a domínios perigosos. Você não verá nenhuma atividade de rede no Central de Segurança do Microsoft Defender.

Se você não configurá-lo, o bloqueio de rede será desligado por padrão.

Para obter mais informações, consulte [Enable network protection](enable-network-protection.md).

## <a name="investigation-impact"></a>Impacto da investigação
Quando a proteção de rede estiver 100%, você verá que, na linha do tempo de um dispositivo, o endereço IP manterá representando o proxy, enquanto o endereço de destino real aparece.

![Imagem de eventos de rede na linha do tempo do dispositivo](images/atp-proxy-investigation.png)

Eventos adicionais disparados pela camada de proteção de rede agora estão disponíveis para aparecer os nomes de domínio reais mesmo atrás de um proxy.

Informações do evento:

![Imagem de evento de rede único](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Procurar eventos de conexão usando a busca avançada 
Todos os novos eventos de conexão estão disponíveis para você também procurar por meio da busca avançada. Como esses eventos são eventos de conexão, você pode encontrá-los na tabela DeviceNetworkEvents sob o `ConnecionSuccess` tipo de ação.

Usar essa consulta simples mostrará todos os eventos relevantes:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Imagem da consulta de busca avançada](images/atp-proxy-investigation-ah.png)

Você também pode filtrar eventos relacionados à conexão com o próprio proxy. 

Use a seguinte consulta para filtrar as conexões com o proxy:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a>Tópicos relacionados
- [Aplicando proteção de rede com GP - CSP de política](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
