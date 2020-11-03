---
title: Tabela IdentityInfo no esquema de busca avançada
description: Saiba mais sobre as informações da conta de usuário na tabela IdentityInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AccountInfo, IdentityInfo, conta
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
ms.openlocfilehash: 0b21d23cfc97576304e949c597301716c72e6871
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847435"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

A `IdentityInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre contas de usuário obtidas de vários serviços, incluindo o Active Directory do Azure. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!NOTE]
>Esta tabela foi renomeada de `AccountInfo` . Durante a renomeação, todas as consultas salvas no portal são atualizadas automaticamente. Verifique as consultas que você salvou em outro lugar.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountUpn` | string | Nome principal do usuário (UPN) da conta |
| `OnPremSid` | string | SID (identificador de segurança) local da conta |
| `CloudSid` | string | Identificador de segurança de nuvem da conta |
| `GivenName` | string | Nome ou nome de usuário da conta fornecido |
| `Surname` | string | Sobrenome, nome da família ou sobrenome do usuário da conta |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `Department` | string | Nome do departamento ao qual pertence o usuário da conta |
| `JobTitle` | string | Título do trabalho da conta de usuário |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `EmailAddress` | string | Endereço SMTP da conta |
| `SipProxyAddress` | string | Endereço SIP (protocolo de iniciação de sessão) de voz sobre IP (VOIP) da conta |
| `City` | string | Cidade onde o usuário da conta está localizado |
| `Country` | string | País/região onde o usuário da conta está localizado |
| `IsAccountEnabled` | booliano | Indica se a conta está habilitada ou não |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
