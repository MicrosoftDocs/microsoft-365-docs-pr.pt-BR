---
title: Tipo de recurso do computador
description: Saiba mais sobre os métodos e propriedades do tipo de recurso Machine no Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, obter, máquinas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7b95fc487a8ee3e82e0f215b34aa564e063534af
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772072"
---
# <a name="machine-resource-type"></a>Tipo de recurso do computador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

Método|Tipo de retorno |Descrição
:---|:---|:---
[Listar computadores](get-machines.md) | [coleção machine](machine.md) | Listar o conjunto [de](machine.md) entidades do computador na organização.
[Obter máquina](get-machine-by-id.md) | [machine](machine.md) | Obter uma [máquina](machine.md) por sua identidade.
[Obter usuários conectados](get-machine-log-on-users.md) | Coleção [usuário](user.md) | Obter o conjunto de [Usuários](user.md) conectado ao [computador](machine.md).
[Obter alertas relacionados](get-machine-related-alerts.md) | conjunto [alerta](alerts.md)  | Obter o conjunto de [entidades](alerts.md) de alerta que foram criadas no [computador](machine.md).
[Obter o software instalado](get-installed-software.md) | [coleção de software](software.md) | Recupera um conjunto de softwares instalados relacionados a uma determinada ID de máquina.
[Obter vulnerabilidades descobertas](get-discovered-vulnerabilities.md) | [conjunto de vulnerabilidades](vulnerability.md) | Recupera uma coleção de vulnerabilidades descobertas relacionadas a uma determinada ID do computador.
[Obter recomendações de segurança](get-security-recommendations.md) | [coleção recommendation](recommendation.md) | Recupera uma coleção de recomendações de segurança relacionadas a uma determinada ID do computador.
[Adicionar ou Remover marcas de computador](add-or-remove-machine-tags.md) | [machine](machine.md) | Adicionar ou Remover marca a um computador específico.
[Localizar os computadores por IP](find-machines-by-ip.md) | [coleção machine](machine.md) | Encontre máquinas vistas com IP.
[Localizar os computadores por marca](find-machines-by-tag.md) | [coleção machine](machine.md) | Encontre máquinas por [Marca](machine-tags.md).
[Obter KBs ausentes](get-missing-kbs-machine.md) | Coleção KB | Obter uma lista de KBs ausentes associados à ID do computador
[Definir valor do dispositivo](set-device-value.md)| [coleção machine](machine.md) | De definir [o valor de um dispositivo](tvm-assign-device-value.md).

## <a name="properties"></a>Propriedades

Propriedade |   Tipo   |   Descrição
:---|:---|:---
id | Cadeia de caracteres | identidade do [computador.](machine.md)
computerDnsName | Cadeia de caracteres | [nome](machine.md) totalmente qualificado da máquina.
firstSeen | DateTimeOffset | Primeira data e hora em que [o computador](machine.md) foi observado pelo Microsoft Defender para Ponto de Extremidade.
lastSeen | DateTimeOffset |Hora e data do último relatório de dispositivo completo recebido. Um dispositivo normalmente envia um relatório completo a cada 24 horas.
osPlatform | Cadeia de caracteres | Plataforma do sistema operacional.
osProcessor | Cadeia de caracteres | Processador do sistema operacional. Use a propriedade osArchitecture.
versão | String | Versão do sistema operacional.
osBuild | Long anulado | Número de com build do sistema operacional.
lastIpAddress | Cadeia de caracteres | Último IP na NIC local no [computador](machine.md).
lastExternalIpAddress | Cadeia de caracteres | Último IP pelo qual o [computador acessou](machine.md) a Internet.
healthStatus | Enum | [status](machine.md) de saúde da máquina. Os valores possíveis são: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" e "Unknown". 
rbacGroupName | Cadeia de caracteres | Nome do grupo de máquinas.
riskScore | Núm anulado | Pontuação de risco avaliada pelo Microsoft Defender para Ponto de Extremidade. Os valores possíveis são: 'None', 'Informational', 'Low', 'Medium' e 'High'.
exposureScore | Núm anulado | [Pontuação de exposição](tvm-exposure-score.md) avaliada pelo Microsoft Defender para Ponto de Extremidade. Os valores possíveis são: 'None', 'Low', 'Medium' e 'High'.
aadDeviceId | Guid de representação anulada | ID do dispositivo AAD (quando [o computador](machine.md) está ingressado no AAD).
machineTags | Coleção de cadeias de caracteres | Conjunto de [marcas de](machine.md) máquina.
exposureLevel | Núm anulado | Nível de exposição conforme avaliado pelo Microsoft Defender para Ponto de Extremidade. Os valores possíveis são: 'None', 'Low', 'Medium' e 'High'.
deviceValue | Núm anulado | O [valor do dispositivo](tvm-assign-device-value.md). Os valores possíveis são: 'Normal', 'Baixo' e 'Alto'.
ipAddresses | Coleção IpAddress | Conjunto de ***objetos IpAddress.*** Consulte [Obter API de máquinas](get-machines.md).
osArchitecture | Cadeia de caracteres | Arquitetura do sistema operacional. Os valores possíveis são: "32 bits", "64 bits". Use essa propriedade em vez de osProcessor.


