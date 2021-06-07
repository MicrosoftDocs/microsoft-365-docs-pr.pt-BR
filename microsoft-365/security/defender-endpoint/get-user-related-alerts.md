---
title: Obter API de alertas relacionados ao usuário
description: Recupere uma coleção de alertas relacionados a uma determinada ID de usuário usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, usuário, relacionado, alertas
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769924"
---
# <a name="get-user-related-alerts-api"></a>Obter API de alertas relacionados ao usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API
Recupera uma coleção de alertas relacionados a uma determinada ID de usuário.


## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Alert.Read.All |    'Ler todos os alertas'
Aplicativo |   Alert.ReadWrite.All |   'Ler e gravar todos os alertas'
Delegado (conta corporativa ou de estudante) | Alert.Read | 'Alertas de leitura'
Delegado (conta corporativa ou de estudante) | Alert.ReadWrite | 'Alertas de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados". Para obter mais informações, consulte [Create and manage roles](user-roles.md).
>- A resposta incluirá apenas alertas, associados a dispositivos, aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/users/{id}/alerts
```

**A ID não é o UPN completo, mas apenas o nome de usuário. (por exemplo, para recuperar alertas para user1@contoso.com /api/users/user1/alerts)**

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se bem-sucedido e o usuário existir - 200 OK. Se o usuário não existir - 404 Não Encontrado. 


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
