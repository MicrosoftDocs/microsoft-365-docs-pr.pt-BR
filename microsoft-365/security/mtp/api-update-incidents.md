---
title: Atualizar a API de incidentes
description: Saiba como atualizar incidentes usando a API do Microsoft 365 defender
keywords: atualização, API, incidente
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844831"
---
# <a name="update-incidents-api"></a>Atualizar a API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descrição da API
Atualiza as propriedades de um incidente existente.
<br>As propriedades atualizáveis são: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` e ```tags``` .


## <a name="limitations"></a>Limitações
1. As limitações de taxa para esta API são de 50 chamadas por minuto e 1500 chamadas por hora.
2. Você pode definir ```determination``` somente se a classificação for definida como TruePositive.


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar esta API. Para saber mais, incluindo como escolher permissões, consulte [Access The Microsoft 365 defender APIs](api-access.md).

Tipo de permissão |   Permissão  |   Nome para exibição da permissão
:---|:---|:---
Aplicativo |   Incident. ReadWrite. All |    ' Ler e gravar todos os incidentes '
Delegada (conta corporativa ou de estudante) | Incident. ReadWrite | ' Ler e gravar incidentes '

>[!NOTE]
> Ao obter um token usando as credenciais do usuário:
>- O usuário precisa ter permissão para atualizar o incidente no Portal.


## <a name="http-request"></a>Solicitação HTTP

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | String | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, forneça os valores para os campos relevantes que devem ser atualizados.
<br>Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade. 
<br>Para obter um melhor desempenho, você não deve incluir valores existentes que não foram alterados.

Propriedade | Tipo | Descrição
:---|:---|:---
status | Enum | Especifica o status atual do alerta. Os valores possíveis são ```Active``` : ```Resolved``` e ```Redirected``` .
assignedTo | string | Proprietário do incidente.
classificação | Enum | Especificação do alerta. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do alerta. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
categorias | Lista de cadeia de caracteres | Lista de marcas de incidente.



## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e a entidade de incidente no corpo da resposta com as propriedades atualizadas. Se o incidente com a ID especificada não for encontrado-404 não encontrado.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Tópico relacionado
- [APIs de Incidente](api-incident.md)
- [Listar incidentes](api-list-incidents.md)
