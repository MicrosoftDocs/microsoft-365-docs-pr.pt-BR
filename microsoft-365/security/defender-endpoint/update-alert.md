---
title: Atualizar a API da entidade de alerta
description: Saiba como atualizar um alerta do Microsoft Defender ATP usando essa API. Você pode atualizar as propriedades status, determinação, classificação e assignedTo.
keywords: apis, api gráfica, apis com suporte, obter, alerta, informações, id
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
ms.technology: mde
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199304"
---
# <a name="update-alert"></a>Atualizar alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Atualiza as propriedades do [Alerta existente.](alerts.md)
<br>O envio **do comentário** está disponível com ou sem a atualização de propriedades.
<br>As propriedades atualizáveis são: ```status``` ```determination``` , e ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Limitações
1. Você pode atualizar os alertas disponíveis na API. Confira [Listar Alertas](get-alerts.md) para obter mais informações.
2. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Alerts.ReadWrite.All |  'Ler e gravar todos os alertas'
Delegada (conta corporativa ou de estudante) | Alert.ReadWrite | 'Alertas de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)
>- O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, fornece os valores dos campos relevantes que devem ser atualizados.
<br>Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade. 
<br>Para melhor desempenho, você não deve incluir valores existentes que não mudaram.

Propriedade | Tipo | Descrição
:---|:---|:---
status | Cadeia de caracteres | Especifica o status atual do alerta. Os valores da propriedade são: 'New', 'InProgress' e 'Resolved'.
assignedTo | Cadeia de caracteres | Proprietário do alerta
classificação | String | Especifica a especificação do alerta. Os valores da propriedade são: 'Unknown', 'FalsePositive', 'TruePositive'. 
determinação | Cadeia de caracteres | Especifica a determinação do alerta. Os valores da propriedade são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | String | Comentário a ser adicionado ao alerta.

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e a entidade [de](alerts.md) alerta no corpo da resposta com as propriedades atualizadas. Se o alerta com a id especificada não foi encontrado - 404 Não Encontrado.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
