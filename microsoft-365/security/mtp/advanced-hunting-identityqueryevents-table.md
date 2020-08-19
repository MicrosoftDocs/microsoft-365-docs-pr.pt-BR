---
title: Tabela IdentityQueryEvents no esquema de busca avançada
description: Saiba mais sobre eventos de consulta do Active Directory na tabela IdentityQueryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b5238ca32cdf9050391ef69bae3be0914b93f452
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797799"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `IdentityQueryEvents` tabela no esquema de [caça avançada](advanced-hunting-overview.md) contém informações sobre consultas realizadas em objetos do Active Directory, como usuários, grupos, dispositivos e domínios. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes |
| `Application` | string | Aplicativo que executou a ação gravada |
| `QueryType` | string | Tipo de consulta, como o QueryUser ou o EnumerateUsers |
| `QueryTarget` | string | Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade sendo consultado |
| `Query` | string | Cadeia de caracteres usada para executar a consulta |
| `Protocol` | string | Protocolo usado durante a comunicação |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome principal do usuário (UPN) da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | string | FQDN (nome de domínio totalmente qualificado) do ponto de extremidade |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `DestinationDeviceName` | string | Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada |
| `DestinationIPAddress` | string | Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada |
| `TargetDeviceName` | string | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada |
| `TargetAccountUpn` | string | Nome principal do usuário (UPN) da conta à qual a ação registrada foi aplicada |
| `TargetAccountDisplayName` | string | Nome para exibição da conta à qual a ação registrada foi aplicada |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
