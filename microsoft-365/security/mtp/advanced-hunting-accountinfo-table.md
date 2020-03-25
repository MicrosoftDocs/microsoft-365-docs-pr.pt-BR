---
title: Tabela AccountInfo no esquema de busca avançada
description: Saiba mais sobre as informações da conta de usuário na tabela AccountInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidência, arquivo, endereço IP, dispositivo, máquina, usuário, conta
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929523"
---
# <a name="accountinfo"></a>AccountInfo

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `AccountInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre contas de usuário obtidas de vários serviços, incluindo o Active Directory do Azure. Use essa referência para criar consultas que retornam informações dessa tabela.

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
| `SipProxyAddress` | string | Voice of IP (VOIP) endereço de protocolo de início de sessão (SIP) da conta |
| `City` | string | Cidade onde o usuário da conta está localizado |
| `Country` | string | País/região onde o usuário da conta está localizado |
| `IsAccountEnabled` | booliano | Indica se a conta está habilitada ou não |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
