---
title: Função DeviceFromIP () em busca avançada no Microsoft 365 defender
description: Saiba como usar a função DeviceFromIP () para obter os dispositivos aos quais foram atribuídos um endereço IP específico
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, dispositivo, devicefromIP, função, enriquecimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741100"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Use a `DeviceFromIP()` função nas suas consultas de [busca avançada](advanced-hunting-overview.md) para obter rapidamente a lista de dispositivos que foram atribuídos a um determinado endereço IP em um determinado momento. 

Essa função retorna uma tabela com as seguintes colunas:

| Coluna | Tipo de dados | Descrição |
|------------|-------------|-------------|
| `IP` | string | Endereço IP  |
| `DeviceId` | string | Identificador exclusivo do dispositivo no serviço |


## <a name="syntax"></a>Sintaxe

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumentos

Essa função é chamada como parte de uma consulta.

- **x**— o primeiro parâmetro normalmente já é uma coluna na consulta. Nesse caso, é a coluna chamada `IP` , o endereço IP para o qual você deseja ver uma lista de dispositivos que foram atribuídos a ele. Deve ser um endereço IP local. Não há suporte para endereços IP externos.
- **y**— um segundo parâmetro opcional é o `Timestamp` , que instrui a função a obter os dispositivos atribuídos mais recentes de uma hora específica. Se não for especificado, a função retornará os registros mais recentes disponíveis.

## <a name="example"></a>Exemplo


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Obter os dispositivos mais recentes que foram atribuídos a endereços IP específicos

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
