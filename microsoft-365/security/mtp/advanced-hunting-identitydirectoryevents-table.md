---
title: Tabela IdentityDirectoryEvents no esquema de busca avançada
description: Saiba mais sobre o controlador de domínio e eventos do Active Directory na tabela IdentityDirectoryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityDirectoryEvents, controlador de domínio, Active Directory, Azure ATP, identidades
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
ms.openlocfilehash: 9113d12face141b5e8005340af25061c98d5dfe3
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412845"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `IdentityDirectoryEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém eventos que envolvem um controlador de domínio local executando o Active Directory (AD). Esta tabela captura vários eventos relacionados à identidade, como alterações de senha, expiração de senha e alterações de nome de usuário principal (UPN). Ele também captura eventos do sistema no controlador de domínio, como agendamento de tarefas e atividade do PowerShell. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes |
| `Application` | cadeia de caracteres | Aplicativo que executou a ação gravada |
| `TargetAccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta à qual a ação registrada foi aplicada |
| `TargetAccountDisplayName` | cadeia de caracteres | Nome para exibição da conta à qual a ação registrada foi aplicada |
| `TargetDeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada |
| `DestinationPort` | cadeia de caracteres | Porta de destino da atividade |
| `Protocol` | cadeia de caracteres | Protocolo usado durante a comunicação |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountSid` | cadeia de caracteres | Identificador de segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo para a conta no Azure Active Directory |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `IPAddress` | cadeia de caracteres | Endereço IP atribuído ao dispositivo durante a comunicação |
| `Port` | cadeia de caracteres | Porta TCP usada durante a comunicação |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `ISP` | cadeia de caracteres | Provedor de serviços de Internet associado ao endereço IP |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
