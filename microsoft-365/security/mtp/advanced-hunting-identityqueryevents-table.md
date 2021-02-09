---
title: Tabela IdentityQueryEvents no esquema de busca avançada
description: Saiba mais sobre os eventos de consulta do Active Directory na tabela IdentityQueryEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
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
ms.openlocfilehash: 48a1520e9fc6239fd3105f01a32a03e5e58df174
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145278"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre consultas realizadas em objetos do Active Directory, como `IdentityQueryEvents` usuários, grupos, dispositivos e domínios. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal para](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) obter detalhes |
| `Application` | string | Aplicativo que realizou a ação gravada |
| `QueryType` | string | Tipo de consulta, como QueryGroup, QueryUser ou EnumerateUsers |
| `QueryTarget` | string | Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade que está sendo consultado |
| `Query` | string | Cadeia de caracteres usada para executar a consulta |
| `Protocol` | string | Protocolo usado durante a comunicação |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome UPN da conta |
| `AccountSid` | string | Sid (Identificador de Segurança) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome. |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do ponto de extremidade |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `Port` | string | Porta TCP usada durante a comunicação |
| `DestinationDeviceName` | string | Nome do dispositivo que executa o aplicativo servidor que processou a ação gravada |
| `DestinationIPAddress` | string | Endereço IP do dispositivo que executa o aplicativo servidor que processou a ação gravada |
| `DestinationPort` | string | Porta de destino de comunicações de rede relacionadas |
| `TargetDeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo ao qual a ação gravada foi aplicada |
| `TargetAccountUpn` | string | Nome UPN da conta à que a ação gravada foi aplicada |
| `TargetAccountDisplayName` | string | Nome de exibição da conta à que a ação gravada foi aplicada |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
