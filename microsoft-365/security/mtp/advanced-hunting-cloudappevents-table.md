---
title: Tabela CloudAppEvents no esquema de busca avançada
description: Saiba mais sobre eventos de aplicativos e serviços em nuvem na tabela CloudAppEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928445"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Disponível atualmente na visualização, a tabela no esquema de busca avançada contém informações sobre atividades em vários aplicativos e serviços de nuvem, especificamente `CloudAppEvents` Microsoft Teams e Exchange Online. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

Esta tabela será expandida para incluir mais atividades monitoradas pelo Microsoft Cloud App Security. Eventualmente, esta tabela incluirá a atividade de arquivo atualmente armazenada na [tabela AppFileEvents.](advanced-hunting-appfileevents-table.md) A Microsoft fornecerá orientações adicionais à medida que mais dados se moverem para esta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento |
| `Application` | string | Aplicativo que realizou a ação gravada |
| `ApplicationId` | string | Identificador exclusivo do aplicativo |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure Active Directory |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome. |
| `IsAdminOperation` | string | Indica se a atividade foi executada por um administrador |
| `DeviceType` | string | Tipo de dispositivo com base em finalidade e funcionalidade, como "Dispositivo de rede", "Estação de trabalho", "Servidor", "Celular", "Console de jogos" ou "Impressora" | 
| `OSPlatform` | string | Plataforma do sistema operacional em execução no dispositivo. Esta coluna indica sistemas operacionais específicos, incluindo variações dentro da mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `IsAnonymousProxy` | string | Indica se o endereço IP pertence a um proxy anônimo conhecido |
| `CountryCode` | string | Código de duas letras indicando o país onde o endereço IP do cliente está geolocalado |
| `City` | string | Cidade onde o endereço IP do cliente está geolocaltado |
| `Isp` | string | Provedor de serviços de Internet (ISP) associado ao endereço IP |
| `UserAgent` | string | Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente |
| `ActivityType` | string | Tipo de atividade que disparou o evento |
| `ActivityObjects` | string | Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade gravada |
| `ObjectName` | string | Nome do objeto ao que a ação gravada foi aplicada |
| `ObjectType` | string | Tipo de objeto, como um arquivo ou uma pasta, ao qual a ação gravada foi aplicada |
| `ObjectId` | string | Identificador exclusivo do objeto ao que a ação gravada foi aplicada |
| `ReportId` | string | Identificador exclusivo do evento |
| `RawEventData` | string | Informações de evento brutas do aplicativo ou serviço de origem no formato JSON |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
