---
title: Tabela DeviceInfo no esquema de busca avançado
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, máquina, sistema operacional, plataforma, usuários
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
ms.openlocfilehash: 53948f3d470fb85ddfda8dbcf5b64024755ca50e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461605"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo a versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ClientVersion` | string | Versão do agente de ponto de extremidade ou sensor em execução no computador |
| `PublicIP` | string | Endereço IP público usado pelo computador interno para se conectar ao serviço Microsoft Defender para Ponto de Extremidade. Esse pode ser o endereço IP do próprio computador, um dispositivo NAT ou um proxy |
| `OSArchitecture` | string | Arquitetura do sistema operacional em execução no computador. |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7 |
| `OSBuild` | string | Versão de com build do sistema operacional em execução no computador |
| `IsAzureADJoined` | booliano | Indicador booleano de se o computador está ingressado no Azure Active Directory |
| `AadObjectId` | string | Identificador exclusivo do dispositivo no Azure AD |
| `LoggedOnUsers` | string | Lista de todos os usuários que estão conectados no computador no momento do evento no formato de matriz JSON |
| `RegistryDeviceTag` | string | Marca de máquina adicionada por meio do Registro |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
|`AdditionalFields` | string | Informações adicionais sobre o evento no formato de matriz JSON |
| `OSVersion` | string | Versão do sistema operacional em execução no computador. |
| `MachineGroup` | string | Grupo de máquinas do computador. Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador |

A `DeviceInfo` tabela fornece informações do dispositivo com base em pulsações, que são relatórios periódicos ou sinais de um dispositivo. A cada quinze minutos, o dispositivo envia uma pulsação parcial que contém atributos que mudam com frequência, como `LoggedOnUsers` . Uma vez por dia, uma pulsação completa que contém os atributos do dispositivo é enviada.

Você pode usar a seguinte consulta de exemplo para obter o estado mais recente de um dispositivo:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
