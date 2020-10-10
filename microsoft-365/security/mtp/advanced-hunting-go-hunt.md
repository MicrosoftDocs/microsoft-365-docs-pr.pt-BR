---
title: Obter informações relevantes sobre uma entidade com busca no go
description: Saiba como usar a ferramenta "buscar busca" para consultar rapidamente informações relevantes sobre uma entidade ou um evento usando a busca avançada.
keywords: caça avançada, incidente, pivô, entidade, busca de Go, eventos relevantes, busca de ameaças, busca de ameaças no cyber, pesquisa, consulta, telemetria, Microsoft 365, proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: e381793caf49318074bcd096e4301cdf49d12e88
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412185"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Busca rápida de informações de entidade ou de evento com busca no go

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Com a ação de *busca do Go* , você pode investigar rapidamente eventos e vários tipos de entidade usando recursos [avançados de busca avançada](advanced-hunting-overview.md) baseados em consulta. Esta ação executa automaticamente uma consulta de busca avançada para localizar informações relevantes sobre o evento ou entidade selecionado.

A ação ir para a *busca* está disponível em várias seções da central de segurança sempre que os detalhes do evento ou da entidade são exibidos. Por exemplo, você pode usar a *busca do Go* das seguintes seções:

- Na [página incidente](investigate-incidents.md#incident-overview), você pode revisar detalhes sobre usuários, dispositivos e muitas outras entidades associadas a um incidente. À medida que você seleciona uma entidade, obtém informações adicionais, bem como várias ações que podem ser executadas naquele entitity. No exemplo abaixo, uma caixa de correio é selecionada, mostrando os detalhes sobre a caixa de correio, bem como a opção de busca para obter mais informações sobre a caixa de correio.

    ![Imagem mostrando os detalhes da caixa de correio com a opção ir para a busca](../../media/mtp-ah/go-hunt-email.png)

- Na página incidente, você também pode acessar uma lista de entidades na guia evidência. Selecionar uma dessas entidades oferece uma opção de busca rápida de informações sobre essa entidade.

    ![Imagem mostrando o arquivo selecionado com a opção ir para a busca na guia evidência](../../media/mtp-ah/go-hunt-evidence-file.png)


- Ao exibir a linha do tempo de um dispositivo, você pode selecionar um evento na linha do tempo para exibir informações adicionais sobre o evento. Depois que um evento for selecionado, você terá a opção de procurar outros eventos relevantes na busca avançada.

    ![Imagem mostrando detalhes do evento com a opção ir para a busca](../../media/mtp-ah/go-hunt-event.png)

Selecionar a **busca de ir** ou procurar **eventos relacionados passa por** diferentes consultas, dependendo se você selecionou uma entidade ou um evento.

## <a name="query-for-entity-information"></a>Consultar informações da entidade
Ao usar a *busca do Go* para consultar informações sobre um usuário, dispositivo ou qualquer outro tipo de entidade, a consulta verifica todas as tabelas de esquema relevantes para todos os eventos que envolvem essa entidade. Para manter os resultados gerenciáveis, a consulta tem o escopo em torno do mesmo período de tempo que a atividade mais antiga nos últimos 30 dias que envolve a entidade e é associada ao incidente.

Veja um exemplo da consulta de busca do Go para um dispositivo:

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>Tipos de entidade com suporte
Você pode usar a *busca do Go* depois de selecionar qualquer um desses tipos de entidade:

- Arquivos
- Emails
- Clusters de email
- Caixas de correio
- Usuários
- Dispositivos
- Endereços IP
- URLs

## <a name="query-for-event-information"></a>Consultar informações de eventos
Ao usar a *busca do Go* para consultar informações sobre um evento de linha do tempo, a consulta verifica todas as tabelas de esquema relevantes para outros eventos em torno do momento do evento selecionado. Por exemplo, a consulta a seguir lista os eventos em várias tabelas de esquema que ocorreram em torno do mesmo período de tempo no mesmo dispositivo:

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>Ajustar a consulta
Com algum conhecimento da [linguagem de consulta](advanced-hunting-query-language.md), você pode ajustar a consulta à sua preferência. Por exemplo, você pode ajustar essa linha, que determina o tamanho da janela de tempo:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Além de modificar a consulta para obter resultados mais relevantes, você também pode:
- [Exibir os resultados como gráficos](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Criar uma regra de detecção personalizada](custom-detection-rules.md)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Regras de detecção personalizadas](custom-detection-rules.md)
