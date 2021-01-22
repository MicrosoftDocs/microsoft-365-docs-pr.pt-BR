---
title: Tabela IdentityDirectoryEvents no esquema de busca avançada
description: Saiba mais sobre os eventos do controlador de domínio e do Active Directory na tabela IdentityDirectoryEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityDirectoryEvents, controlador de domínio, Active Directory, Azure ATP, identidades
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929929"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém eventos envolvendo um controlador de domínio local executando o `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD). Esta tabela captura vários eventos relacionados à identidade, como alterações de senha, expiração de senha e alterações de nome UPN. Ele também captura eventos do sistema no controlador de domínio, como o agendamento de tarefas e a atividade do PowerShell. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal para](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) obter detalhes |
| `Application` | string | Aplicativo que realizou a ação gravada |
| `TargetAccountUpn` | string | Nome UPN da conta à que a ação gravada foi aplicada |
| `TargetAccountDisplayName` | string | Nome de exibição da conta à que a ação gravada foi aplicada |
| `TargetDeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo ao qual a ação gravada foi aplicada |
| `DestinationDeviceName` | string | Nome do dispositivo que executa o aplicativo servidor que processou a ação gravada |
| `DestinationIPAddress` | string | Endereço IP do dispositivo que executa o aplicativo servidor que processou a ação gravada |
| `DestinationPort` | string | Porta de destino da atividade |
| `Protocol` | string | Protocolo usado durante a comunicação |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome UPN da conta |
| `AccountSid` | string | Sid (Identificador de Segurança) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure Active Directory |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome. |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo |
| `IPAddress` | string | Endereço IP atribuído ao dispositivo durante a comunicação |
| `Port` | string | Porta TCP usada durante a comunicação |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `ISP` | string | Provedor de serviços de Internet associado ao endereço IP |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
