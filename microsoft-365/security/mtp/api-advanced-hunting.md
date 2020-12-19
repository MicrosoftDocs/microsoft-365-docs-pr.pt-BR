---
title: API de busca avançada do Microsoft 365 defender
description: Saiba como executar consultas de busca avançada usando a API de busca avançada do Microsoft 365 defender
keywords: Caça avançada, APIs, API, MTP, M365 defender, Microsoft 365 defender
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719375"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API de busca avançada do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Proteção contra Ameaças da Microsoft

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

A [busca avançada](advanced-hunting-overview.md) é uma ferramenta de busca de ameaças que usa [consultas especialmente construídas](advanced-hunting-query-language.md) para examinar os últimos 30 dias de dados de evento no Microsoft 365 defender. Você pode usar consultas de busca avançada para inspecionar atividades anormais, detectar possíveis ameaças e até mesmo responder a ataques. A API de busca avançada permite que você consulte programaticamente dados de eventos.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

As condições a seguir se relacionam a todas as consultas.

1. As consultas exploram e retornam dados dos últimos 30 dias.
2. Os resultados podem retornar até 100.000 linhas.
3. Você pode fazer até 10 chamadas por minuto por locatário.
4. Você tem 10 minutos de tempo de execução por hora por locatário.
5. Você tem quatro horas de tempo de execução por locatário.
6. Se uma única solicitação for executada por mais de 10 minutos, o tempo limite expirará e retornará um erro.
7. Um `429` código de resposta http indica que você atingiu uma cota, seja pelo número de solicitações enviadas ou pelo tempo de execução alocado. O corpo da resposta incluirá o tempo até que a cota que você atingiu seja redefinida.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar a API de busca avançada. Para saber mais, incluindo como escolher permissões, confira [acessar as APIs de proteção do Microsoft 365 defender](api-access.md)

Tipo de permissão | Permissão | Nome para exibição da permissão
-|-|-
Aplicativo | AdvancedHunting. Read. All | Executar consultas avançadas
Delegada (conta corporativa ou de estudante) | AdvancedHunting. Read | Executar consultas avançadas

>[!Note]
> Ao obter um token usando as credenciais do usuário:
>
>- O usuário precisa ter a função de AD ' exibir dados '
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.

## <a name="http-request"></a>Solicitação HTTP

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Cabeçalho | Valor
-|-
Autorização | Portador {token} **Observação: obrigatório**
Content-Type | application/json

## <a name="request-body"></a>Corpo da solicitação

No corpo da solicitação, forneça um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo | Descrição
-|-|-
Consulta | Texto | A consulta a ser executada. **Observação: obrigatório**

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará `200 OK` e um objeto _QueryResponse_ no corpo da resposta.

O objeto Response contém três propriedades de nível superior:

1. Stats-um dicionário de estatísticas de desempenho da consulta.
2. Schema-o esquema da resposta, uma lista de pares de Name-Type de cada coluna.
3. Resultados-uma lista de eventos de busca avançados.

## <a name="example"></a>Exemplo

No exemplo a seguir, um usuário envia a consulta abaixo e recebe um objeto de resposta da API contendo `Stats` , `Schema` e `Results` .

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

- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Entender códigos de erro](api-error-codes.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
