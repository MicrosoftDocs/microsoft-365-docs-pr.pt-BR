---
title: Tabela DeviceInfo no esquema de busca avançado
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações de dispositivo na tabela DeviceInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, deviceinfo, dispositivo, sistema operacional, plataforma, usuários, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054111"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo sua versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md) Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `ClientVersion` | cadeia de caracteres | Versão do agente de ponto de extremidade ou sensor em execução no dispositivo |
| `PublicIP` | cadeia de caracteres | Endereço IP público usado pelo dispositivo interno para se conectar ao serviço Defender para Ponto de Extremidade. Esse pode ser o endereço IP do próprio dispositivo, um dispositivo NAT ou um proxy |
| `OSArchitecture` | cadeia de caracteres | Arquitetura do sistema operacional em execução no dispositivo |
| `OSPlatform` | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7 |
| `OSBuild` | cadeia de caracteres | Versão de com build do sistema operacional em execução no dispositivo |
| `IsAzureADJoined` | booliano | Indicador booleano de se o dispositivo está ingressado no Azure Active Directory |
| `LoggedOnUsers` | cadeia de caracteres | Lista de todos os usuários que estão conectados no dispositivo no momento do evento no formato de matriz JSON |
| `RegistryDeviceTag` | cadeia de caracteres | Marca de dispositivo adicionada por meio do Registro |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `OSVersion` | cadeia de caracteres | Versão do sistema operacional em execução no dispositivo |
| `MachineGroup` | cadeia de caracteres | Grupo de máquinas do computador. Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
