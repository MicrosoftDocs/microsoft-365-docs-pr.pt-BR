---
title: APIs de busca avançada
description: Saiba como executar consultas de busca avançada usando a API de proteção contra ameaças da Microsoft
keywords: Caça avançada, APIs, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9e92a0328d2e7fb9cfe7461241dd866081926876
ms.sourcegitcommit: 62a8c226422eac9c085cc886b4836b037f95ef6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47825369"
---
# <a name="advanced-hunting-apis"></a>APIs de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>Limitações
1. Você só pode executar uma consulta nos dados dos últimos 30 dias.
2. Os resultados incluirão um máximo de 100.000 linhas.
3. O número de execuções é limitado por locatário: até 10 chamadas por minuto, 10 minutos de tempo de execução a cada hora e 4 horas de tempo de execução por dia.
4. O tempo máximo de execução de uma única solicitação é de 10 minutos.
5. 429 a resposta representará um limite de cota de alcance por número de solicitações ou por CPU. O corpo da resposta 429 também indicará o tempo até que a cota seja renovada. 


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar esta API. Para saber mais, incluindo como escolher permissões, confira [acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)

Tipo de permissão |   Permissão  |   Nome para exibição da permissão
:---|:---|:---
Aplicativo |   AdvancedHunting. Read. All |  ' Executar consultas avançadas '
Delegado (conta corporativa ou de estudante) | AdvancedHunting. Read | ' Executar consultas avançadas '

>[!Note]
> Ao obter um token usando as credenciais do usuário:
>- O usuário precisa ter a função de AD ' exibir dados '
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.

## <a name="http-request"></a>Solicitação HTTP
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Cabeçalho | Valor 
:---|:---
Autorização | Portador {token}. **Obrigatório**.
Content-Type    | application/json

## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, forneça um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo    | Descrição
:---|:---|:---
Consulta | Texto |  A consulta a ser executada. **Obrigatório**.

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e o objeto _QueryResponse_ no corpo da resposta. <br><br>

O objeto Response é dividido como 3 partes (Propriedades):<br>
1) ```Stats``` – Estatísticas de desempenho da consulta.<br>
2) ```Schema``` – O esquema da resposta, uma lista de pares de tipo de nome para cada coluna. <br>
3) ```Results``` – Uma lista de eventos de busca avançados.

## <a name="example"></a>Exemplo

Solicitação

Este é um exemplo da solicitação.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Resposta

Veja a seguir um exemplo da resposta.


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>Tópico relacionado
- [Acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)
