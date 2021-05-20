---
title: Tabela IdentityLogonEvents no esquema avançado de caça
description: Saiba mais sobre eventos de autenticação gravados pelo Active Directory na tabela IdentityLogonEvents do esquema avançado de caça
keywords: caça avançada, caça de ameaças, caça de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identidades
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
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572748"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A `IdentityLogonEvents` tabela no esquema avançado de [caça](advanced-hunting-overview.md) contém informações sobre atividades de autenticação feitas através de seu Active Directory on-premises capturado pelo Microsoft Defender para atividades de identidade e autenticação relacionadas aos serviços on-line da Microsoft capturados por Microsoft Cloud App Security. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos `ActionType` (valores) suportados por uma tabela, use a referência de esquema incorporada disponível no centro de segurança.

>[!NOTE]
>Esta tabela abrange Azure Active Directory (Azure AD) atividades de logon rastreadas por Cloud App Security, especificamente atividades interativas de login e autenticação usando o ActiveSync e outros protocolos legados. Os logons não interativos que não estão disponíveis nesta tabela podem ser visualizados no registro de auditoria do Azure AD. [Saiba mais sobre como conectar Cloud App Security ao Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que desencadeou o evento. Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `LogonType` | cadeia de caracteres | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** - O usuário interage fisicamente com a máquina usando o teclado e a tela locais<br><br> - **Logons interativos remotos (RDP)** - O usuário interage remotamente com a máquina usando desktop remoto, serviços de terminal, assistência remota ou outros clientes RDP<br><br> - **Rede** - Sessão iniciada quando a máquina é acessada usando PsExec ou quando recursos compartilhados na máquina, como impressoras e pastas compartilhadas, são acessados<br><br> - **Lote** - Sessão iniciada por tarefas agendadas<br><br> - **Serviço** - Sessão iniciada pelos serviços à medida que eles começam |
| `Protocol` | cadeia de caracteres | Protocolo de rede usado |
| `FailureReason` | cadeia de caracteres | Informações explicando por que a ação gravada falhou |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountSid` | cadeia de caracteres | Identificador de segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo para a conta no Azure AD |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido na agenda de endereços. Tipicamente uma combinação de um dado ou primeiro nome, uma iniciação do meio e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto final e usado durante comunicações de rede relacionadas |
| `Port` | cadeia de caracteres | Porta TCP usada durante a comunicação |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo executando o aplicativo do servidor que processou a ação gravada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo executando o aplicativo do servidor que processou a ação gravada |
| `DestinationPort` | cadeia de caracteres | Porta de destino de comunicações de rede relacionadas |
| `TargetDeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo a que a ação gravada foi aplicada |
| `TargetAccountDisplayName` | cadeia de caracteres | Nome de exibição da conta a que a ação gravada foi aplicada |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | cadeia de caracteres | Provedor de serviços de Internet (ISP) associado ao endereço IP de ponto final |
| `ReportId` | long | Identificador exclusivo para o evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)