---
title: Tabela DeviceInfo no esquema de busca avançado
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, máquina, sistema operacional, plataforma, usuários
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689104"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender
- Microsoft Defender para Ponto de Extremidade



A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo a versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ClientVersion` | cadeia de caracteres | Versão do agente de ponto de extremidade ou sensor em execução no computador |
| `PublicIP` | cadeia de caracteres | Endereço IP público usado pelo computador interno para se conectar ao serviço Microsoft Defender para Ponto de Extremidade. Esse pode ser o endereço IP do próprio computador, um dispositivo NAT ou um proxy |
| `OSArchitecture` | string | Arquitetura do sistema operacional em execução no computador. |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como Windows 10 e Windows 7 |
| `OSBuild` | cadeia de caracteres | Versão de com build do sistema operacional em execução no computador |
| `IsAzureADJoined` | booliano | Indicador booleano de se o computador está ingressado no Azure Active Directory |
| `AadObjectId` | cadeia de caracteres | Identificador exclusivo do dispositivo no Azure AD |
| `LoggedOnUsers` | cadeia de caracteres | Lista de todos os usuários que estão conectados no computador no momento do evento no formato de matriz JSON |
| `RegistryDeviceTag` | cadeia de caracteres | Marca de máquina adicionada por meio do Registro |
| `OSVersion` | string | Versão do sistema operacional em execução no computador. |
| `MachineGroup` | string | Grupo de máquinas do computador. Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `OnboardingStatus` | cadeia de caracteres | Indica se o dispositivo está atualmente conectado ou não ao Microsoft Defender Para Ponto de Extremidade ou se o dispositivo não tem suporte |
|`AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |
|`DeviceCategory` | cadeia de caracteres | Classificação mais ampla que grupos determinados tipos de dispositivo nas seguintes categorias: Ponto de Extremidade, Dispositivo de rede, IoT, Desconhecido |
|`DeviceType` | cadeia de caracteres | Tipo de dispositivo com base na finalidade e funcionalidade, como dispositivo de rede, estação de trabalho, servidor, celular, console de jogos ou impressora |
|`DeviceSubType` | cadeia de caracteres | Modificador adicional para determinados tipos de dispositivos, por exemplo, um dispositivo móvel pode ser um tablet ou um smartphone |
|`Model` | cadeia de caracteres | Nome do modelo ou número do produto do fornecedor ou fabricante |
|`Vendor` | cadeia de caracteres | Nome do fornecedor ou fabricante do produto |
|`OSDistribution` | cadeia de caracteres | Distribuição da plataforma do sistema operacional, como Ubuntu ou RedHat para plataformas Linux |
|`OSVersionInfo` | cadeia de caracteres | Informações adicionais sobre a versão do sistema operacional, como o nome popular, o nome do código ou o número da versão |
|`MergedDeviceIds` | cadeia de caracteres | IDs de dispositivo anteriores que foram atribuídas ao mesmo dispositivo |
|`MergedToDeviceId` | cadeia de caracteres | A ID de dispositivo mais recente atribuída a um dispositivo |

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
