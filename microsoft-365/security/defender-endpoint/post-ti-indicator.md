---
title: Api de Indicador de Envio ou Atualização
description: Saiba como usar a API Enviar ou Atualizar Indicador para enviar ou atualizar uma nova entidade Indicator no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, enviar, ti, indicador, atualização
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771700"
---
# <a name="submit-or-update-indicator-api"></a>Api de Indicador de Envio ou Atualização

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API
Envia ou atualiza a nova [entidade Indicator.](ti-indicator.md)
<br>A notação CIDR para IPs não é suportada.

## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.
2. Há um limite de 15.000 indicadores ativos por locatário. 


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Ti.ReadWrite |  'Indicadores de leitura e gravação'
Aplicativo |   Ti.ReadWrite.All |  'Ler e gravar Todos os Indicadores'
Delegado (conta corporativa ou de estudante) |    Ti.ReadWrite |  'Indicadores de leitura e gravação'


## <a name="http-request"></a>Solicitação HTTP
```
POST https://api.securitycenter.microsoft.com/api/indicators
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
indicatorValue | Cadeia de caracteres | Identidade da entidade [Indicator.](ti-indicator.md) **Required**
indicatorType | Enum | Tipo do indicador. Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url". **Required**
ação | Enum | A ação que será tomada se o indicador for descoberto na organização. Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed". **Required**
aplicação | Cadeia de caracteres | O aplicativo associado ao indicador. **Opcional**
title | Cadeia de caracteres | Título de alerta de indicador. **Required**
description | Cadeia de caracteres | Descrição do indicador. **Required**
expirationTime | DateTimeOffset | O tempo de expiração do indicador. **Opcional**
severity | Enum | A gravidade do indicador. os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto". **Opcional**
recommendedActions | Cadeia de caracteres | Ações recomendadas do alerta de ti. **Opcional**
rbacGroupNames | Cadeia de caracteres | Lista separada por vírgulas de nomes de grupo do RBAC aos que o indicador seria aplicado. **Opcional**


## <a name="response"></a>Resposta
- Se tiver êxito, este método retornará 200 - código de resposta OK e a entidade [Indicator](ti-indicator.md) criada/atualizada no corpo da resposta.
- Se não tiver êxito: este método retornará 400 - Solicitação Ruim. A solicitação incorreta geralmente indica o corpo incorreto.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Tópicos relacionados
- [Gerenciar indicadores](manage-indicators.md)
