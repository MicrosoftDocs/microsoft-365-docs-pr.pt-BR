---
title: Atualizar a API incidente
description: Saiba como atualizar incidentes usando Microsoft 365 API do Defender
keywords: atualização, api, incidente
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571776"
---
# <a name="update-incident-api"></a>Atualizar a API incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

## <a name="api-description"></a>Descrição da API

Atualiza as propriedades do incidente existente. As propriedades de updatable são: ```status``` , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cotas, alocação de recursos e outras restrições

1. Você pode fazer até 50 chamadas por minuto ou 1500 chamadas por hora antes de atingir o limite de estrangulamento.
2. Você só pode definir a `determination` propriedade se estiver definida como `classification` TruePositive.

Se sua solicitação for estrangulada, ela retornará um `429` código de resposta. O corpo de resposta indicará o momento em que você pode começar a fazer novas chamadas.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar esta API. Para saber mais, incluindo como escolher permissões, consulte [Acessar as APIs Microsoft 365 Defender](api-access.md).

Tipo de permissão | Permissão | Nome de exibição de permissão
-|-|-
Aplicativo | Incidente.ReadWrite.Todos | Leia e escreva todos os incidentes
Delegado (conta corporativa ou de estudante) | Incidente.ReadWrite | Leia e escreva incidentes

> [!NOTE]
> Ao obter um token usando credenciais do usuário, o usuário precisa ter permissão para atualizar o incidente no portal.

## <a name="http-request"></a>Solicitação HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
-|-|-
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

No órgão de solicitação, forneça os valores para os campos que devem ser atualizados. As propriedades existentes que não estão incluídas no órgão de solicitação manterão seus valores, a menos que tenham que ser recalculadas devido a alterações nos valores relacionados. Para obter melhor desempenho, você deve omitir valores existentes que não mudaram.

Propriedade | Tipo | Descrição
-|-|-
status | Enum | Especifica o estado atual do incidente. Os valores possíveis são: ```Active``` ```Resolved``` , , e ```Redirected``` .
assignedTo | cadeia de caracteres | O dono do incidente.
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | lista de strings | Lista de etiquetas de incidente.
comment | string | Comentário a ser adicionado ao incidente.

## <a name="response"></a>Resposta

Se for bem sucedido, este método retorna `200 OK` . O corpo de resposta conterá a entidade incidente com propriedades atualizadas. Se um incidente com a ID especificada não foi encontrado, o método retorna `404 Not Found` .

## <a name="example"></a>Exemplo

**Solicitação**

Aqui está um exemplo do pedido.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Response**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Artigos relacionados

- [Acesse as APIs do Microsoft 365 Defender](api-access.md)
- [Conheça os limites e licenciamento da API](api-terms.md)
- [Entenda códigos de erro](api-error-codes.md)
- [APIs de Incidente](api-incident.md)
- [Listar incidentes](api-list-incidents.md)
- [Visão geral dos incidentes](incidents-overview.md)
