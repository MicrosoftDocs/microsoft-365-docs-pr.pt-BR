---
title: Obter informações relevantes sobre uma entidade em busca de ir
description: Saiba como usar a ferramenta ir para busca para consultar rapidamente informações relevantes sobre uma entidade ou evento usando a busca avançada.
keywords: busca avançada, incidente, pivô, entidade, ir à busca, eventos relevantes, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929497"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Busca rápida por informações de entidade ou evento com a busca

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Com a *ação de busca de* ir, você pode investigar rapidamente eventos e vários tipos de entidade usando recursos avançados de busca avançados baseados [em](advanced-hunting-overview.md) consulta poderosos. Essa ação executa automaticamente uma consulta de busca avançada para encontrar informações relevantes sobre o evento ou entidade selecionada.

A *ação de busca de* ir está disponível em várias seções do centro de segurança sempre que os detalhes do evento ou da entidade são exibidos. Por exemplo, você pode usar *a busca nas* seguintes seções:

- Na página [de incidentes,](investigate-incidents.md#incident-overview)você pode analisar detalhes sobre usuários, dispositivos e muitas outras entidades associadas a um incidente. À medida que você seleciona uma entidade, você pode obter informações adicionais, bem como várias ações que podem ser tomadas sobre essa direitos. No exemplo a seguir, uma caixa de correio é selecionada, mostrando detalhes sobre a caixa de correio, bem como a opção para procurar mais informações sobre a caixa de correio.

    ![Imagem mostrando detalhes da caixa de correio com a opção de busca de ir](../../media/mtp-ah/go-hunt-email.png)

- Na página de incidentes, você também pode acessar uma lista de entidades na guia evidências. Selecionar uma dessas entidades oferece uma opção para rapidamente procurar informações sobre essa entidade.

    ![Imagem mostrando o arquivo selecionado com a opção ir para busca na guia Evidências](../../media/mtp-ah/go-hunt-evidence-file.png)


- Ao exibir a linha do tempo de um dispositivo, você pode selecionar um evento na linha do tempo para exibir informações adicionais sobre esse evento. Depois que um evento é selecionado, você tem a opção de procurar outros eventos relevantes na busca avançada.

    ![Imagem mostrando detalhes do evento com a opção de busca de ir](../../media/mtp-ah/go-hunt-event.png)

Selecionar **Ir para busca** ou **procurar** eventos relacionados passa por consultas diferentes, dependendo se você selecionou uma entidade ou um evento.

## <a name="query-for-entity-information"></a>Consulta por informações de entidade
Ao usar *ir* à busca para consultar informações sobre um usuário, dispositivo ou qualquer outro tipo de entidade, a consulta verifica todas as tabelas de esquema relevantes para quaisquer eventos envolvendo essa entidade. Para manter os resultados gerenciáveis, a consulta tem como escopo cerca do mesmo período de tempo que a atividade mais antiga nos últimos 30 dias que envolve a entidade e está associada ao incidente.

Aqui está um exemplo da consulta de busca de ir para um dispositivo:

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
Você pode usar *ir à busca* após selecionar qualquer um desses tipos de entidade:

- Arquivos
- Emails
- Clusters de email
- Caixas de correio
- Usuários
- Dispositivos
- Endereços IP
- URLs

## <a name="query-for-event-information"></a>Consulta de informações sobre o evento
Ao usar *ir à* busca para consultar informações sobre um evento de linha do tempo, a consulta verifica todas as tabelas de esquema relevantes para outros eventos em torno da hora do evento selecionado. Por exemplo, a consulta a seguir lista eventos em várias tabelas de esquema que ocorreram durante o mesmo período no mesmo dispositivo:

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
Com algum conhecimento da [linguagem de consulta,](advanced-hunting-query-language.md)você pode ajustar a consulta à sua preferência. Por exemplo, você pode ajustar essa linha, que determina o tamanho da janela de tempo:

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
