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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a65a8e78dfa09bc0a417669a1efd35320e261da
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798774"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A `IdentityDirectoryEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém eventos que envolvem um controlador de domínio local executando o Active Directory (AD). Esta tabela captura vários eventos relacionados à identidade, como alterações de senha, expiração de senha e alterações de nome de usuário principal (UPN). Ele também captura eventos do sistema no controlador de domínio, como agendamento de tarefas e atividade do PowerShell. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes |
| `Application` | string | Aplicativo que executou a ação gravada |
| `TargetAccountUpn` | string | Nome principal do usuário (UPN) da conta à qual a ação registrada foi aplicada |
| `TargetAccountDisplayName` | string | Nome para exibição da conta à qual a ação registrada foi aplicada |
| `TargetDeviceName` | string | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada |
| `DestinationDeviceName` | string | Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada |
| `DestinationIPAddress` | string | Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada |
| `DestinationPort` | string | Porta de destino da atividade |
| `Protocol` | string | Protocolo usado durante a comunicação |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome principal do usuário (UPN) da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | string | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `IPAddress` | string | Endereço IP atribuído ao dispositivo durante a comunicação |
| `Port` | string | Porta TCP usada durante a comunicação |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `ISP` | string | Provedor de serviços de Internet associado ao endereço IP |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
