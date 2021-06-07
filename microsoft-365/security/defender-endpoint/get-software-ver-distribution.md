---
title: Listar distribuição das versões do software
description: Recupera uma lista da distribuição de versão de software da sua organização
keywords: apis, api gráfica, apis com suporte, obter, distribuição de versão de software, api de tvm do Microsoft Defender para Endpoint
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
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772116"
---
# <a name="list-software-version-distribution"></a>Listar distribuição das versões do software 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera uma lista da distribuição de versão de software da sua organização. 

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo | Software.Read.All | 'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | Software.Read | 'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Nome        | Tipo | Descrição
|:--------------|:-------|:--------------|
| Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK com uma lista de dados de distribuições de software no corpo. 


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**Response**

Veja a seguir um exemplo da resposta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciamento de vulnerabilidades baseadas em & risco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventário & software de vulnerabilidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
