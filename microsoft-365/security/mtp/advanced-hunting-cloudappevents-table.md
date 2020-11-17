---
title: Tabela CloudAppEvents no esquema de busca avançada
description: Saiba mais sobre eventos de aplicativos e serviços em nuvem na tabela CloudAppEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, segurança do aplicativo em nuvem, MCAS
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087758"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Atualmente disponível no modo de visualização, a `CloudAppEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as atividades em vários aplicativos e serviços de nuvem, especificamente o Microsoft Teams e o Exchange Online. Use essa referência para criar consultas que retornam informações dessa tabela.

Esta tabela será expandida para incluir mais atividades monitoradas pelo Microsoft Cloud app Security. Eventualmente, esta tabela incluirá a atividade de arquivo atualmente armazenada na tabela [AppFileEvents](advanced-hunting-appfileevents-table.md) . A Microsoft fornecerá orientações adicionais à medida que mais dados são movidos para esta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento |
| `Application` | string | Aplicativo que executou a ação gravada |
| `ApplicationId` | string | Identificador exclusivo do aplicativo |
| `AccountObjectId` | string | Identificador exclusivo para a conta no Azure Active Directory |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `IsAdminOperation` | string | Indica se a atividade foi executada por um administrador |
| `DeviceType` | string | Tipo de dispositivo baseado no objetivo e na funcionalidade, como "dispositivo de rede", "estação de trabalho", "servidor", "celular", "console de jogos" ou "impressora" | 
| `OSPlatform` | string | Plataforma do sistema operacional em execução no dispositivo. Esta coluna indica sistemas operacionais específicos, incluindo variações dentro da mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `IsAnonymousProxy` | string | Indica se o endereço IP pertence a um proxy anônimo conhecido |
| `CountryCode` | string | Código de duas letras que indica o país onde o endereço IP do cliente está geolocalizado |
| `City` | string | Cidade onde o endereço IP do cliente está geolocalizado |
| `Isp` | string | Provedor de serviços de Internet (ISP) associado ao endereço IP |
| `UserAgent` | string | Informações do agente do usuário do navegador da Web ou outro aplicativo cliente |
| `ActivityType` | string | Tipo de atividade que disparou o evento |
| `ActivityObjects` | string | Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade registrada |
| `ObjectName` | string | Nome do objeto ao qual a ação registrada foi aplicada |
| `ObjectType` | string | Tipo de objeto, como um arquivo ou uma pasta, a ação gravada foi aplicada a |
| `ObjectId` | string | Identificador exclusivo do objeto ao qual a ação registrada foi aplicada |
| `ReportId` | string | Identificador exclusivo do evento |
| `RawEventData` | string | Informações de evento bruto do aplicativo de origem ou serviço no formato JSON |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
