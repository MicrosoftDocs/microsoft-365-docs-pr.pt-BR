---
title: Tabela IdentityDirectoryEvents no esquema de busca avançado
description: Saiba mais sobre o controlador de domínio e eventos do Active Directory na tabela IdentityDirectoryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityDirectoryEvents, controlador de domínio, Active Directory, Microsoft Defender para Identidade, identidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b42ff09f1e363f115ecc06c361c8386b328b0bcb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932996"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém eventos envolvendo um controlador de domínio local executando o `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD). Esta tabela captura vários eventos relacionados à identidade, como alterações de senha, expiração de senha e alterações de nome principal do usuário (UPN). Ele também captura eventos do sistema no controlador de domínio, como agendamento de tarefas e atividade do PowerShell. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `TargetAccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta à que a ação gravada foi aplicada |
| `TargetAccountDisplayName` | cadeia de caracteres | Nome de exibição da conta à que a ação gravada foi aplicada |
| `TargetDeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação gravada foi aplicada |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationPort` | cadeia de caracteres | Porta de destino da atividade |
| `Protocol` | cadeia de caracteres | Protocolo usado durante a comunicação |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure Active Directory |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `IPAddress` | cadeia de caracteres | Endereço IP atribuído ao dispositivo durante a comunicação |
| `Port` | cadeia de caracteres | Porta TCP usada durante a comunicação |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `ISP` | cadeia de caracteres | Provedor de serviços de Internet associado ao endereço IP |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
