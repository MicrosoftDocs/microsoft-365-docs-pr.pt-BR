---
title: Listar dispositivos por recomendação
description: Recupera uma lista de dispositivos associados à recomendação de segurança.
keywords: apis, api gráfica, apis com suporte, obter, recomendação de segurança para dispositivos vulneráveis, Gerenciamento de Ameaças e Vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades api
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
ms.openlocfilehash: a321a3aec9bbd0e7e405b82b7cbd56cf214694ca
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845186"
---
# <a name="list-devices-by-recommendation"></a>Listar dispositivos por recomendação

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera uma lista de dispositivos associados à recomendação de segurança.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   SecurityRecommendation.Read.All |   'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | SecurityRecommendation.Read |  'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK com a lista de dispositivos associados à recomendação de segurança.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

**Response**

Veja a seguir um exemplo da resposta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciamento de vulnerabilidades baseadas em & risco](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Recomendação & segurança de vulnerabilidade](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
