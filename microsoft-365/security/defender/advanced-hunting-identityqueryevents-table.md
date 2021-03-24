---
title: Tabela IdentityQueryEvents no esquema de busca avançado
description: Saiba mais sobre eventos de consulta do Active Directory na tabela IdentityQueryEvents do esquema de busca avançado
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f663a9dcc5bebd3a7fd124bbd0c0fece5dbb62e4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054424"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre consultas realizadas em objetos do Active Directory, como `IdentityQueryEvents` usuários, grupos, dispositivos e domínios. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `QueryType` | cadeia de caracteres | Tipo de consulta, como QueryGroup, QueryUser ou EnumerateUsers |
| `QueryTarget` | cadeia de caracteres | Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade que está sendo consultado |
| `Query` | cadeia de caracteres | Cadeia de caracteres usada para executar a consulta |
| `Protocol` | cadeia de caracteres | Protocolo usado durante a comunicação |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do ponto de extremidade |
| `IPAddress` | cadeia de caracteres | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `Port` | cadeia de caracteres | Porta TCP usada durante a comunicação |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationPort` | cadeia de caracteres | Porta de destino de comunicações de rede relacionadas |
| `TargetDeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação gravada foi aplicada |
| `TargetAccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta à que a ação gravada foi aplicada |
| `TargetAccountDisplayName` | cadeia de caracteres | Nome de exibição da conta à que a ação gravada foi aplicada |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
