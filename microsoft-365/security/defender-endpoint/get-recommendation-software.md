---
title: Obter recomendação por software
description: Recupera uma recomendação de segurança relacionada a um software específico.
keywords: apis, api gráfica, apis com suporte, obter, recomendação de segurança, recomendação de segurança para software, Gerenciamento de Ameaças e Vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 68bc53f2ae0b44567530cc1dd733c9dd37d380ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769576"
---
# <a name="get-recommendation-by-software"></a>Obter recomendação por software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Recupera uma recomendação de segurança relacionada a um software específico.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   SecurityRecommendation.Read.All |   'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | SecurityRecommendation.Read |  'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK com o software associado às recomendações de segurança no corpo.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

**Response**

Veja a seguir um exemplo da resposta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciamento de vulnerabilidades baseadas em & risco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Recomendação & segurança de vulnerabilidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
