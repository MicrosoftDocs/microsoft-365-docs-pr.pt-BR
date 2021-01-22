---
title: Tabela IdentityInfo no esquema de busca avançada
description: Saiba mais sobre as informações da conta de usuário na tabela IdentityInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AccountInfo, IdentityInfo, conta
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929905"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre contas de usuário obtidas de vários serviços, incluindo o `IdentityInfo` Azure [](advanced-hunting-overview.md) Active Directory. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!NOTE]
>Esta tabela foi renomeada de `AccountInfo` . Durante as renomeações, todas as consultas salvas no portal são atualizadas automaticamente. Verifique as consultas que você salvou em outro lugar.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountUpn` | string | Nome UPN da conta |
| `OnPremSid` | string | Identificador de segurança (SID) local da conta |
| `CloudSid` | string | Identificador de segurança na nuvem da conta |
| `GivenName` | string | Nome ou nome do usuário da conta |
| `Surname` | string | Sobrenome, nome de família ou sobrenome do usuário da conta |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome. |
| `Department` | string | Nome do departamento ao que o usuário da conta pertence |
| `JobTitle` | string | Cargo do usuário da conta |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `EmailAddress` | string | Endereço SMTP da conta |
| `SipProxyAddress` | string | Endereço SIP (voice over IP) de sessão de início de sessão (SIP) da conta |
| `City` | string | Cidade onde o usuário da conta está localizado |
| `Country` | string | País/região onde o usuário da conta está localizado |
| `IsAccountEnabled` | booliano | Indica se a conta está habilitada ou não |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
