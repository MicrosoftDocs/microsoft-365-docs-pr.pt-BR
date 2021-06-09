---
title: Obter recomendação por ID
description: Recupera uma recomendação de segurança por sua ID.
keywords: apis, api gráfica, apis com suporte, obter, recomendação de segurança, recomendação de segurança por ID, Gerenciamento de Ameaças e Vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades api
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
ms.openlocfilehash: 66eb9c838e351a75ff68f40e9179cfeeb9bf9d4e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845181"
---
# <a name="get-recommendation-by-id"></a>Obter recomendação por ID

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Recupera uma recomendação de segurança por sua ID.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   SecurityRecommendation.Read.All |   'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | SecurityRecommendation.Read |  'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK com as recomendações de segurança no corpo.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

**Response**

Veja a seguir um exemplo da resposta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciamento de vulnerabilidades baseadas em & risco](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Recomendação & segurança de vulnerabilidade](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
