---
title: API de busca avançada do Microsoft 365 Defender
description: Saiba como executar consultas de busca avançada usando a API de busca avançada do Microsoft 365 Defender
keywords: Busca avançada, APIs, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932077"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API de busca avançada do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Proteção contra Ameaças da Microsoft

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

[A busca](advanced-hunting-overview.md) avançada é uma [](advanced-hunting-query-language.md) ferramenta de busca de ameaças que usa consultas especialmente construídas para examinar os últimos 30 dias de dados de eventos no Microsoft 365 Defender. Você pode usar consultas de busca avançadas para inspecionar atividades incomuns, detectar possíveis ameaças e até mesmo responder a ataques. A API de busca avançada permite que você consulte programaticamente os dados de eventos.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

As condições a seguir se relacionam a todas as consultas.

1. As consultas exploram e retornam dados dos últimos 30 dias.
2. Os resultados podem retornar até 100.000 linhas.
3. Você pode fazer até 10 chamadas por minuto por locatário.
4. Você tem 10 minutos de tempo de execução por hora por locatário.
5. Você tem quatro horas totais de dias de tempo de execução por locatário.
6. Se uma única solicitação for executado por mais de 10 minutos, o tempo esgota e retornará um erro.
7. Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou por tempo `429` de execução alocado. O corpo da resposta incluirá o tempo até que a cota alcançada seja redefinida.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar a API de busca avançada. Para saber mais, incluindo como escolher permissões, confira Acessar as APIs do [Microsoft 365 Defender Protection](api-access.md)

Tipo de permissão | Permissão | Nome de exibição da permissão
-|-|-
Aplicativo | AdvancedHunting.Read.All | Executar consultas avançadas
Delegado (conta corporativa ou de estudante) | AdvancedHunting.Read | Executar consultas avançadas

>[!Note]
> Ao obter um token usando credenciais de usuário:
>
>- O usuário precisa ter a função do AD "Exibir Dados"
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.

## <a name="http-request"></a>Solicitação HTTP

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Cabeçalho | Valor
-|-
Autorização | {token} de portador **Observação: obrigatório**
Content-Type | application/json

## <a name="request-body"></a>Corpo da solicitação

No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo | Descrição
-|-|-
Consulta | Texto | A consulta a ser executado. **Observação: obrigatório**

## <a name="response"></a>Resposta

Se bem-sucedido, este método retornará `200 OK` e um _objeto QueryResponse_ no corpo da resposta.

O objeto response contém três propriedades de nível superior:

1. Estatísticas - Um dicionário de estatísticas de desempenho da consulta.
2. Esquema - O esquema da resposta, uma lista de Name-Type pares de cada coluna.
3. Resultados - Uma lista de eventos avançados de busca.

## <a name="example"></a>Exemplo

No exemplo a seguir, um usuário envia a consulta abaixo e recebe um objeto de resposta de API `Stats` que contém , e `Schema` `Results` .

### <a name="query"></a>Consulta

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Objeto Response

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

## <a name="related-articles"></a>Artigos relacionados

- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Saiba mais sobre limites e licenciamento da API](api-terms.md)
- [Noções sobre códigos de erro](api-error-codes.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
