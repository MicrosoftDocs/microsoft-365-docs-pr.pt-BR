---
title: Tabela IdentityLogonEvents no esquema de busca avançada
description: Saiba mais sobre eventos de autenticação registrados pelo Active Directory na tabela IdentityLogonEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identidades
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
ms.openlocfilehash: 2116d8f6f1006f5acf9d468006fa07a04e13087b
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046023"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `IdentityLogonEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as atividades de autenticação realizadas pelo Active Directory local capturado pelo Azure ATP e atividades de autenticação relacionadas aos serviços online da Microsoft capturadas pelo Microsoft Cloud app Security. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento |
| `LogonType` | string | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** -o usuário interage fisicamente com o computador usando o teclado e a tela locais<br><br> - **Logons interativos (RDP) remotos** -o usuário interage com o computador remotamente usando a área de trabalho remota, serviços de terminal, assistência remota ou outros clientes RDP<br><br> - **Rede** -sessão iniciada quando a máquina é acessada usando o PsExec ou quando recursos compartilhados na máquina, como impressoras e pastas compartilhadas, são acessados<br><br> - Sessão **em lote** iniciada por tarefas agendadas<br><br> - **Serviço** -sessão iniciada pelos serviços à medida que eles são iniciados |
| `Application` | string | Aplicativo que executou a ação gravada |
| `Protocol` | string | Protocolo usado durante a comunicação |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome principal do usuário (UPN) da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | string | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
