---
title: Obter API de estatísticas de domínio
description: Saiba como usar a API Obter estatísticas de domínio para recuperar as estatísticas sobre o domínio determinado no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, domínio, dispositivos relacionados ao domínio
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
ms.openlocfilehash: d2edc5d429d124412134b466753b65506d2dd7a9
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772180"
---
# <a name="get-domain-statistics-api"></a>Obter API de estatísticas de domínio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Recupera as estatísticas no domínio determinado.


## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   URL. Read.All |  'URLs de leitura'
Delegado (conta corporativa ou de estudante) | URL. Read.All | 'URLs de leitura'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Cabeçalho | Valor 
:---|:---
Autorização | Portador {token}. **Obrigatório**.

## <a name="request-uri-parameters"></a>Solicitar parâmetros URI

Nome | Tipo | Descrição
:---|:---|:---
lookBackHours | Int32 | Define as horas que pesquisamos de volta para obter as estatísticas. O padrão é 30 dias. **Opcional**.

## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se bem-sucedido e o domínio existir - 200 OK, com o objeto statistics no corpo da resposta. Se o domínio não existir - 404 Não Encontrado.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**Response**

Veja a seguir um exemplo da resposta.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
