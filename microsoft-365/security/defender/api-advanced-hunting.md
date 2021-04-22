---
title: API de busca avançada do Microsoft 365 Defender
description: Saiba como executar consultas de busca avançadas usando a API de busca avançada do Microsoft 365 Defender
keywords: Busca avançada, APIs, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c988a609a329c8f7f8988314e56aae942beebac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932888"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API de busca avançada do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

[A busca avançada](advanced-hunting-overview.md) é uma [](advanced-hunting-query-language.md) ferramenta de busca de ameaças que usa consultas especialmente construídas para examinar os últimos 30 dias de dados de eventos no Microsoft 365 Defender. Você pode usar consultas avançadas de busca para inspecionar atividades incomuns, detectar possíveis ameaças e até mesmo responder a ataques. A API de busca avançada permite que você consulte programaticamente dados de eventos.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

As condições a seguir se relacionam a todas as consultas.

1. As consultas exploram e retornam dados dos últimos 30 dias.
2. Os resultados podem retornar até 100.000 linhas.
3. Você pode fazer até 15 chamadas por minuto por locatário.
4. Você tem 10 minutos de tempo de execução por hora por locatário.
5. Você tem quatro horas totais de tempo de execução por dia por locatário.
6. Se uma única solicitação for executado por mais de 10 minutos, ela passará o tempo e retornará um erro.
7. Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou pelo tempo de `429` execução alocado. Leia o corpo da resposta para entender o limite atingido. 

> [!NOTE]
> Todas as cotas listadas acima (por exemplo, 15 chamadas por minuto) são por tamanho de locatário. Essas cotas são mínimas.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar a API de busca avançada. Para saber mais, incluindo como escolher permissões, consulte [Access the Microsoft 365 Defender Protection APIs](api-access.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
-|-|-
Aplicativo | AdvancedHunting.Read.All | Executar consultas avançadas
Delegada (conta corporativa ou de estudante) | AdvancedHunting.Read | Executar consultas avançadas

>[!Note]
> Ao obter um token usando credenciais de usuário:
>
>- O usuário precisa ter a função AD 'Exibir Dados'
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

No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo | Descrição
-|-|-
Consulta | Texto | A consulta a ser executado. **Observação: obrigatório**

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará `200 OK` e um _objeto QueryResponse_ no corpo da resposta.

O objeto response contém três propriedades de nível superior:

1. Estatísticas - Um dicionário de estatísticas de desempenho de consulta.
2. Esquema - O esquema da resposta, uma lista de Name-Type pares para cada coluna.
3. Resultados - Uma lista de eventos de busca avançada.

## <a name="example"></a>Exemplo

No exemplo a seguir, um usuário envia a consulta abaixo e recebe um objeto de resposta da API contendo `Stats` `Schema` , e `Results` .

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
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Compreender códigos de erro](api-error-codes.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
