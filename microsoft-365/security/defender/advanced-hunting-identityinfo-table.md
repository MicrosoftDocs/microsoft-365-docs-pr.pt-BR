---
title: Tabela IdentityInfo no esquema de busca avançado
description: Saiba mais sobre as informações da conta de usuário na tabela IdentityInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AccountInfo, IdentityInfo, conta
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935816"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre contas de usuário obtidas de vários `IdentityInfo` serviços, incluindo [](advanced-hunting-overview.md) Azure Active Directory. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!NOTE]
>Esta tabela foi renomeada de `AccountInfo` . Durante os renomeados, todas as consultas salvas no portal são atualizadas automaticamente. Verifique consultas salvas em outro lugar.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `OnPremSid` | cadeia de caracteres | Identificador de segurança local (SID) da conta |
| `CloudSid` | cadeia de caracteres | Identificador de segurança na nuvem da conta |
| `GivenName` | cadeia de caracteres | Nome ou nome do usuário da conta |
| `Surname` | cadeia de caracteres | Sobrenome, nome da família ou sobrenome do usuário da conta |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome. |
| `Department` | cadeia de caracteres | Nome do departamento ao que o usuário da conta pertence |
| `JobTitle` | cadeia de caracteres | Título de trabalho do usuário da conta |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `EmailAddress` | cadeia de caracteres | Endereço SMTP da conta |
| `SipProxyAddress` | cadeia de caracteres | Endereço SIP (Protocolo de iniciação de sessão DE VOIP) de voz sobre IP da conta |
| `City` | cadeia de caracteres | Cidade onde o usuário da conta está localizado |
| `Country` | cadeia de caracteres | País/Região onde o usuário da conta está localizado |
| `IsAccountEnabled` | booliano | Indica se a conta está habilitada ou não |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
