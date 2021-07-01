---
title: Obter API de usuários de logon de máquina
description: Saiba como usar a API Obter usuários de logon do computador para recuperar uma coleção de usuários conectados em um dispositivo no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivo, fazer logoff, usuários
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229018"
---
# <a name="get-machine-logon-users-api"></a>Obter API de usuários de logon de máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Recupera uma coleção de usuários conectados em um dispositivo específico.

## <a name="limitations"></a>Limitações
1. Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.
2. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |Permissão|Nome de exibição de permissão
:---|:---|:---
Aplicativo |User.Read.All |'Ler perfis de usuário'
Delegada (conta corporativa ou de estudante) | User.Read.All | 'Ler perfis de usuário'

> [!NOTE]
> Ao obter um token usando credenciais de usuário:
>
> - O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados". Para obter mais informações, consulte [Create and manage roles](user-roles.md)).
> - A resposta incluirá usuários somente se o dispositivo estiver visível para o usuário, com base nas configurações do grupo de dispositivos. Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).

## <a name="http-request"></a>Solicitação HTTP

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | String | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

Vazio

## <a name="response"></a>Resposta

Se bem-sucedido e o dispositivo existir - 200 OK com a [lista](user.md) de entidades do usuário no corpo. Se o dispositivo não foi encontrado - 404 Não Encontrado.

## <a name="example"></a>Exemplo

### <a name="request"></a>Solicitação

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a>Resposta

Veja a seguir um exemplo da resposta.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
