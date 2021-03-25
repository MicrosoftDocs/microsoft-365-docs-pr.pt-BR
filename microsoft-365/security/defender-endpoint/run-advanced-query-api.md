---
title: API de Busca Avançada
ms.reviewer: ''
description: Aprenda a usar a API de busca avançada para executar consultas avançadas no Microsoft Defender para Ponto de Extremidade. Saiba mais sobre limitações e consulte um exemplo.
keywords: apis, apis com suporte, busca avançada, consulta
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
ms.technology: mde
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200192"
---
# <a name="advanced-hunting-api"></a>API de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Limitações
1. Você só pode executar uma consulta em dados dos últimos 30 dias.
2. Os resultados incluirão no máximo 100.000 linhas.
3. O número de execuções é limitado por locatário:
   - Chamadas de API: até 45 chamadas por minuto.
   - Tempo de execução: 10 minutos de tempo de execução a cada hora e 3 horas de tempo de execução por dia.
4. O tempo máximo de execução de uma única solicitação é de 10 minutos.
5. A resposta 429 representará atingir o limite de cota por número de solicitações ou por CPU. Leia o corpo da resposta para entender qual limite foi atingido. 

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   AdvancedQuery.Read.All |    'Executar consultas avançadas'
Delegada (conta corporativa ou de estudante) | AdvancedQuery.Read | 'Executar consultas avançadas'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter a função de AD "Exibir Dados"
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Cabeçalho | Valor 
:---|:---
Autorização | Portador {token}. **Obrigatório**.
Content-Type    | application/json

## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo    | Descrição
:---|:---|:---
Consulta | Texto |  A consulta a ser executado. **Obrigatório**.

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e _o objeto QueryResponse_ no corpo da resposta.


## <a name="example"></a>Exemplo

Solicitação

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

Resposta

Veja a seguir um exemplo da resposta.

>[!NOTE]
>O objeto de resposta mostrado aqui pode ser truncado para brevidade. Todas as propriedades serão retornadas de uma chamada real.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a>Tópicos relacionados
- [Introdução às APIs do Microsoft Defender para Endpoint](apis-intro.md)
- [Busca Avançada do Portal](advanced-hunting-query-language.md)
- [Busca Avançada usando o PowerShell](run-advanced-query-sample-powershell.md)
