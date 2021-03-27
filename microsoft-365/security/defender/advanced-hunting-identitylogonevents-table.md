---
title: Tabela IdentityLogonEvents no esquema de busca avançado
description: Saiba mais sobre eventos de autenticação registrados pelo Active Directory na tabela IdentityLogonEvents do esquema de busca avançado
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2d6904d47e58a7cf7a1b7fce5083da43c9a01a76
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382502"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançado contém informações sobre atividades de autenticação feitas por meio do Active Directory local capturado pelo Microsoft Defender para Identidade e atividades de autenticação relacionadas aos serviços online da Microsoft capturados pelo `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

>[!NOTE]
>Esta tabela aborda as atividades de logon do Azure Active Directory (AD) controladas pelo Cloud App Security, especificamente atividades de autenticação e logon interativos usando ActiveSync e outros protocolos herdados. Os logons não interativos que não estão disponíveis nesta tabela podem ser exibidos no log de auditoria do Azure AD. [Saiba mais sobre como conectar o Cloud App Security ao Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `LogonType` | cadeia de caracteres | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** - O usuário interage fisicamente com o computador usando o teclado local e a tela<br><br> - **Logons interativos remotos (RDP)** - O usuário interage com o computador remotamente usando Área de Trabalho Remota, Serviços de Terminal, Assistência Remota ou outros clientes RDP<br><br> - **Rede** - Sessão iniciada quando o computador é acessado usando PsExec ou quando os recursos compartilhados no computador, como impressoras e pastas compartilhadas, são acessados<br><br> - **Batch** - Sessão iniciada por tarefas agendadas<br><br> - **Serviço** - Sessão iniciada pelos serviços à medida que eles iniciam |
| `Protocol` | cadeia de caracteres | Protocolo de rede usado |
| `FailureReason` | cadeia de caracteres | Informações explicando por que a ação gravada falhou |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `Port` | cadeia de caracteres | Porta TCP usada durante a comunicação |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationPort` | cadeia de caracteres | Porta de destino de comunicações de rede relacionadas |
| `TargetDeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação gravada foi aplicada |
| `TargetAccountDisplayName` | cadeia de caracteres | Nome de exibição da conta à que a ação gravada foi aplicada |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | cadeia de caracteres | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)