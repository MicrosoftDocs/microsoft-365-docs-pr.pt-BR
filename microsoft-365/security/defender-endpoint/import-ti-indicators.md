---
title: Importar API de indicadores
description: Saiba como usar o lote de importação da API de indicador no Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, enviar, ti, indicador, atualização
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198240"
---
# <a name="import-indicators-api"></a>Importar API de indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Envia ou atualiza o lote de entidades [Indicator.](ti-indicator.md)
<br>A notação CIDR para IPs não é suportada.

## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 30 chamadas por minuto.
2. Há um limite de 15.000 Indicadores [ativos](ti-indicator.md) por locatário. 
3. O tamanho máximo de lote para uma chamada de API é 500.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Ti.ReadWrite |  'Indicadores de leitura e gravação'
Aplicativo |   Ti.ReadWrite.All |  'Ler e gravar Todos os Indicadores'
Delegado (conta corporativa ou de estudante) |    Ti.ReadWrite |  'Indicadores de leitura e gravação'


## <a name="http-request"></a>Solicitação HTTP
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | string | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo    | Descrição
:---|:---|:---
Indicadores | Indicador de<[de lista](ti-indicator.md)> | Lista de [indicadores](ti-indicator.md). **Required**


## <a name="response"></a>Resposta
- Se tiver êxito, este método retornará 200 - código de resposta OK com uma lista de resultados de importação por indicador, consulte o exemplo abaixo.
- Se não tiver êxito: este método retornará 400 - Solicitação Ruim. A solicitação incorreta geralmente indica o corpo incorreto.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

**Response**

Veja a seguir um exemplo da resposta.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>Tópicos relacionados
- [Gerenciar indicadores](manage-indicators.md)
