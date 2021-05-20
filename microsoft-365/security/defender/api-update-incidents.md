---
title: Atualizar API de incidentes
description: Saiba como atualizar incidentes usando Microsoft 365 API do Defender
keywords: update, api, incident
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
# <a name="update-incident-api"></a>Atualizar API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

## <a name="api-description"></a>Descrição da API

Atualiza as propriedades do incidente existente. As propriedades atualizáveis são: ```status``` , , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cotas, alocação de recursos e outras restrições

1. Você pode fazer até 50 chamadas por minuto ou 1500 chamadas por hora antes de atingir o limite de limite de limite.
2. Você só pode definir `determination` a propriedade se estiver definida como `classification` TruePositive.

Se sua solicitação for acelerada, ela retornará um `429` código de resposta. O corpo da resposta indicará a hora em que você pode começar a fazer novas chamadas.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Access the Microsoft 365 Defender APIs](api-access.md).

Tipo de permissão | Permissão | Nome de exibição de permissão
-|-|-
Aplicativo | Incident.ReadWrite.All | Ler e gravar todos os incidentes
Delegada (conta corporativa ou de estudante) | Incident.ReadWrite | Incidentes de leitura e gravação

> [!NOTE]
> Ao obter um token usando credenciais de usuário, o usuário precisa ter permissão para atualizar o incidente no portal.

## <a name="http-request"></a>Solicitação HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
-|-|-
Autorização | String | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

No corpo da solicitação, fornece os valores para os campos que devem ser atualizados. As propriedades existentes que não estão incluídas no corpo da solicitação manterão seus valores, a menos que elas tenham que ser recalculadas devido a alterações nos valores relacionados. Para melhor desempenho, você deve omitir valores existentes que não foram alterados.

Propriedade | Tipo | Descrição
-|-|-
status | Enum | Especifica o status atual do incidente. Os valores possíveis são: ```Active``` ```Resolved``` , e ```Redirected``` .
assignedTo | cadeia de caracteres | Proprietário do incidente.
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | string List | Lista de marcas de incidente.
comment | string | Comentário a ser adicionado ao incidente.

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará `200 OK` . O corpo da resposta conterá a entidade de incidente com propriedades atualizadas. Se um incidente com a ID especificada não for encontrado, o método retornará `404 Not Found` .

## <a name="example"></a>Exemplo

**Solicitação**

Veja um exemplo da solicitação.

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

- [Acessar as APIs Microsoft 365 Defender](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Compreender códigos de erro](api-error-codes.md)
- [APIs de Incidente](api-incident.md)
- [Listar incidentes](api-list-incidents.md)
- [Visão geral dos incidentes](incidents-overview.md)
