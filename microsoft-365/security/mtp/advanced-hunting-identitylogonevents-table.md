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
ms.openlocfilehash: aec5bf5dfe29dd55bf5e5df471126db46fdfcb4c
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648822"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `IdentityLogonEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as atividades de autenticação realizadas pelo Active Directory local capturado pelo Azure ATP e atividades de autenticação relacionadas aos serviços online da Microsoft capturadas pelo Microsoft Cloud app Security. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!NOTE]
>Esta tabela aborda as atividades de logon do Azure Active Directory (AD) rastreadas pela segurança do aplicativo de nuvem, especificamente entradas interativas e atividades de autenticação usando o ActiveSync e outros protocolos herdados. Os logons não interativos que não estão disponíveis nesta tabela podem ser exibidos no log de auditoria do Azure AD. [Saiba mais sobre como conectar o Cloud app Security ao Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `LogonType` | cadeia de caracteres | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** -o usuário interage fisicamente com o computador usando o teclado e a tela locais<br><br> - **Logons interativos (RDP) remotos** -o usuário interage com o computador remotamente usando a área de trabalho remota, serviços de terminal, assistência remota ou outros clientes RDP<br><br> - **Rede** -sessão iniciada quando a máquina é acessada usando o PsExec ou quando recursos compartilhados na máquina, como impressoras e pastas compartilhadas, são acessados<br><br> - Sessão **em lote** iniciada por tarefas agendadas<br><br> - **Serviço** -sessão iniciada pelos serviços à medida que eles são iniciados |
| `Application` | cadeia de caracteres | Aplicativo que executou a ação gravada |
| `Protocol` | cadeia de caracteres | Protocolo de rede usado |
| `FailureReason` | cadeia de caracteres | Informações explicando por que a ação gravada falhou |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountSid` | cadeia de caracteres | Identificador de segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada |
| `TargetDeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada |
| `TargetAccountDisplayName` | cadeia de caracteres | Nome para exibição da conta à qual a ação registrada foi aplicada |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | cadeia de caracteres | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procurar por dispositivos, emails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)