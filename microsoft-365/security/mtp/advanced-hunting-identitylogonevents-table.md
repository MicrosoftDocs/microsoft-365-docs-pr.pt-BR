---
title: Tabela IdentityLogonEvents no esquema de busca avançada
description: Saiba mais sobre os eventos de autenticação registrados pelo Active Directory na tabela IdentityLogonEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identidades
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
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929917"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre atividades de autenticação feitas por meio do Active Directory local capturado pelo Microsoft Defender para atividades de identidade e autenticação relacionadas aos serviços online da Microsoft capturados pelo `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>Esta tabela abrange as atividades de logon do Azure Active Directory (AD) controladas pelo Cloud App Security, especificamente atividades interativas de autenticação e logon usando o ActiveSync e outros protocolos herdados. Os logons não interativos que não estão disponíveis nesta tabela podem ser exibidos no log de auditoria do Azure AD. [Saiba mais sobre como conectar o Cloud App Security ao Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal para](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) obter detalhes |
| `LogonType` | string | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** - o usuário interage fisicamente com o computador usando o teclado local e a tela<br><br> - **Logons interativos remotos (RDP)** – o usuário interage com o computador remotamente usando a Área de Trabalho Remota, Serviços de Terminal, Assistência Remota ou outros clientes RDP<br><br> - **Rede** - Sessão iniciada quando o computador é acessado usando PsExec ou quando os recursos compartilhados no computador, como impressoras e pastas compartilhadas, são acessados<br><br> - **Lote** - Sessão iniciada por tarefas agendadas<br><br> - **Serviço** - Sessão iniciada pelos serviços ao iniciar |
| `Application` | string | Aplicativo que realizou a ação gravada |
| `Protocol` | string | Protocolo de rede usado |
| `FailureReason` | string | Informações explicando por que a ação gravada falhou |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome UPN da conta |
| `AccountSid` | string | Sid (Identificador de Segurança) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome. |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo |
| `DeviceType` | string | Tipo de dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `DestinationDeviceName` | string | Nome do dispositivo que executa o aplicativo servidor que processou a ação gravada |
| `DestinationIPAddress` | string | Endereço IP do dispositivo que executa o aplicativo servidor que processou a ação gravada |
| `TargetDeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo ao qual a ação gravada foi aplicada |
| `TargetAccountDisplayName` | string | Nome de exibição da conta à que a ação gravada foi aplicada |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | string | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
