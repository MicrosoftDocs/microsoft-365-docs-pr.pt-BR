---
title: Obter pontuação de exposição
description: Recupera a pontuação de exposição organizacional.
keywords: apis, api gráfica, apis com suporte, obter, pontuação de exposição, pontuação de exposição organizacional
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845385"
---
# <a name="get-exposure-score"></a>Obter pontuação de exposição

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Recupera a pontuação de exposição organizacional.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
:---|:---|:---
Aplicativo | Score.Read.All | 'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | Score.Read | 'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP

```
GET /api/exposureScore
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

Vazio

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200 OK, com os dados de exposição no corpo da resposta.

## <a name="example"></a>Exemplo

### <a name="request"></a>Solicitação

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>Resposta

Veja a seguir um exemplo da resposta.

>[!NOTE]
>A lista de respostas mostrada aqui pode ser truncada para brevidade. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a>Confira também

- [Gerenciamento de vulnerabilidades baseadas em & risco](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Classificação & de exposição de vulnerabilidade](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
