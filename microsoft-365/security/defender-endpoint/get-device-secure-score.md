---
title: Obter pontuação segura do dispositivo
description: Recupera a pontuação segura do dispositivo organizacional.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
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
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772300"
---
# <a name="get-device-secure-score"></a>Obter pontuação segura do dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Recupera a [pontuação segura da Microsoft para dispositivos.](tvm-microsoft-secure-score-devices.md) Uma pontuação segura da Microsoft mais alta para dispositivos significa que seus pontos de extremidade são mais resilientes contra ataques de ameaças de segurança cibernética. 

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Score.Read.Alll |   'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | Score.Read | 'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP

```
GET /api/configurationScore
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

Vazio

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200 OK, com os dados de pontuação segura do dispositivo no corpo da resposta.

## <a name="example"></a>Exemplo

### <a name="request"></a>Solicitação

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a>Resposta

Veja a seguir um exemplo da resposta.

>[!NOTE]
>A lista de respostas mostrada aqui pode ser truncada para brevidade. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>Confira também

- [Consultas OData com o Microsoft Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)
