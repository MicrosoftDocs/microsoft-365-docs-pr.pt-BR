---
title: Listar pontuação de exposição por grupo de dispositivos
description: Recupera uma lista de pontuações de exposição por grupo de dispositivos.
keywords: apis, api gráfica, apis com suporte, obter, pontuação de exposição, grupo de dispositivos, pontuação de exposição do grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 71daccdbcb223ac48d80721bf0a296d9c1a7c98c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770092"
---
# <a name="list-exposure-score-by-device-group"></a>Listar pontuação de exposição por grupo de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera uma coleção de alertas relacionados a um determinado endereço de domínio.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo | Score.Read.All | 'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | Score.Read | 'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Nome        | Tipo | Descrição
|:--------------|:-------|:--------------|
| Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

Vazio

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200 OK, com uma lista de pontuação de exposição por dados do grupo de dispositivos no corpo da resposta.

## <a name="example"></a>Exemplo

### <a name="request"></a>Solicitação

Este é um exemplo da solicitação.

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a>Resposta

Veja a seguir um exemplo da resposta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciamento de vulnerabilidades baseadas em & risco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Classificação & de exposição de vulnerabilidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
