---
title: Função DeviceFromIP() em busca avançada do Microsoft 365 Defender
description: Saiba como usar a função DeviceFromIP() para obter os dispositivos que foram atribuídos a um endereço IP específico
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, dispositivo, devicefromIP, função, enriquecimento
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
ms.openlocfilehash: d2996021a84186adc6656927dbdc910db4d037de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053217"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Use a função em suas consultas de busca avançadas para obter rapidamente a lista de dispositivos que foram atribuídos a um determinado endereço IP em `DeviceFromIP()` um determinado ponto no tempo. [](advanced-hunting-overview.md) 

Esta função retorna uma tabela com as seguintes colunas:

| Coluna | Tipo de dados | Descrição |
|------------|-------------|-------------|
| `IP` | string | Endereço IP  |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço |


## <a name="syntax"></a>Sintaxe

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumentos

Essa função é invocada como parte de uma consulta.

- **x**— o primeiro parâmetro normalmente já é uma coluna na consulta. Nesse caso, é a coluna denominada , o endereço IP para o qual você deseja ver uma lista de dispositivos que foram `IP` atribuídos a ela. Deve ser um endereço IP local. Não há suporte para endereços IP externos.
- **y**— Um segundo parâmetro opcional é o , que instrui a função a obter os dispositivos atribuídos mais recentes `Timestamp` de uma hora específica. Se não for especificada, a função retornará os registros disponíveis mais recentes.

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
