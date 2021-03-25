---
title: API de entidades de alerta de Atualização em Lote
description: Saiba como atualizar alertas do Microsoft Defender para Ponto de Extremidade em um lote usando essa API. Você pode atualizar as propriedades status, determinação, classificação e assignedTo.
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166299"
---
# <a name="batch-update-alerts"></a>Alertas de atualização em lotes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Atualiza as propriedades de um lote de [alertas existentes.](alerts.md)
<br>O envio **do comentário** está disponível com ou sem a atualização de propriedades.
<br>As propriedades atualizáveis são: `status` `determination` , e `classification` `assignedTo` .


## <a name="limitations"></a>Limitações
1. Você pode atualizar alertas que estão disponíveis na API. Confira [Listar Alertas](get-alerts.md) para obter mais informações.
2. Limitações de taxa para essa API são 10 chamadas por minuto e 500 chamadas por hora.


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
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, fornece as IDs dos alertas a serem atualizados e os valores dos campos relevantes que você deseja atualizar para esses alertas.
<br>Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade. 
<br>Para obter um melhor desempenho, não inclua valores existentes que não foram alterados.

Propriedade | Tipo | Descrição
:---|:---|:---
alertIds | Cadeia de &lt; caracteres de lista&gt;| Uma lista das IDs dos alertas a serem atualizados. **Required**
status | Cadeia de caracteres | Especifica o status atualizado dos alertas especificados. Os valores da propriedade são: 'New', 'InProgress' e 'Resolved'.
assignedTo | Cadeia de caracteres | Proprietário dos alertas especificados
classificação | String | Especifica a especificação dos alertas especificados. Os valores da propriedade são: 'Unknown', 'FalsePositive', 'TruePositive'. 
determinação | Cadeia de caracteres | Especifica a determinação dos alertas especificados. Os valores da propriedade são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | String | Comentário a ser adicionado aos alertas especificados.

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK, com um corpo de resposta vazio.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
