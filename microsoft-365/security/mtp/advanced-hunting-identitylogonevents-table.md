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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 176f131ad020d001b72b97332d54be71feef5548
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847411"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

A `IdentityLogonEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as atividades de autenticação feitas por meio de seu Active Directory local capturado pelo Microsoft defender para as atividades de identidade e autenticação relacionadas aos serviços online da Microsoft capturadas pelo Microsoft Cloud app Security. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

>[!NOTE]
>Esta tabela aborda as atividades de logon do Azure Active Directory (AD) rastreadas pela segurança do aplicativo de nuvem, especificamente entradas interativas e atividades de autenticação usando o ActiveSync e outros protocolos herdados. Os logons não interativos que não estão disponíveis nesta tabela podem ser exibidos no log de auditoria do Azure AD. [Saiba mais sobre como conectar o Cloud app Security ao Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes |
| `LogonType` | string | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** -o usuário interage fisicamente com o computador usando o teclado e a tela locais<br><br> - **Logons interativos (RDP) remotos** -o usuário interage com o computador remotamente usando a área de trabalho remota, serviços de terminal, assistência remota ou outros clientes RDP<br><br> - **Rede** -sessão iniciada quando a máquina é acessada usando o PsExec ou quando recursos compartilhados na máquina, como impressoras e pastas compartilhadas, são acessados<br><br> - Sessão **em lote** iniciada por tarefas agendadas<br><br> - **Serviço** -sessão iniciada pelos serviços à medida que eles são iniciados |
| `Application` | string | Aplicativo que executou a ação gravada |
| `Protocol` | string | Protocolo de rede usado |
| `FailureReason` | string | Informações explicando por que a ação gravada falhou |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome principal do usuário (UPN) da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | string | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `DeviceType` | string | Tipo de dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `DestinationDeviceName` | string | Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada |
| `DestinationIPAddress` | string | Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada |
| `TargetDeviceName` | string | FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada |
| `TargetAccountDisplayName` | string | Nome para exibição da conta à qual a ação registrada foi aplicada |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | string | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
