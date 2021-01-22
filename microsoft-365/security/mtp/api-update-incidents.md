---
title: Atualizar a API de incidentes
description: Saiba como atualizar incidentes usando a API do Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929065"
---
# <a name="update-incidents-api"></a>Atualizar a API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Descrição da API

Atualiza as propriedades do incidente existente. As propriedades atualizáveis ```status``` são: ```determination``` , , e ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cotas, alocação de recursos e outras restrições

1. Você pode fazer até 50 chamadas por minuto ou 1500 chamadas por hora antes de atingir o limite de limite.
2. Você só poderá definir `determination` a propriedade se estiver definida como `classification` TruePositive.

Se sua solicitação for acelerada, ela retornará um código `429` de resposta. O corpo da resposta indicará a hora em que você poderá começar a fazer novas chamadas.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, confira [Acessar as APIs do Microsoft 365 Defender.](api-access.md)

Tipo de permissão | Permissão | Nome de exibição da permissão
-|-|-
Aplicativo | Incident.ReadWrite.All | Ler e gravar todos os incidentes
Delegado (conta corporativa ou de estudante) | Incident.ReadWrite | Ler e gravar incidentes

> [!NOTE]
> Ao obter um token usando credenciais de usuário, o usuário precisa ter permissão para atualizar o incidente no portal.

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

No corpo da solicitação, fornece os valores para os campos que devem ser atualizados. Propriedades existentes que não estão incluídas no corpo da solicitação manterão seus valores, a menos que tenham que ser recalculadas devido a alterações nos valores relacionados. Para melhor desempenho, você deve omitir valores existentes que não foram alterados.

Propriedade | Tipo | Descrição
-|-|-
status | Enum | Especifica o status atual do alerta. Os valores possíveis ```Active``` são: ```Resolved``` , e ```Redirected``` .
assignedTo | string | Proprietário do incidente.
classificação | Enum | Especificação do alerta. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do alerta. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
categorias | string List | Lista de marcas de incidente.

## <a name="response"></a>Resposta

Se bem-sucedido, este método retorna `200 OK` . O corpo da resposta conterá a entidade de incidente com propriedades atualizadas. Se um incidente com a ID especificada não for encontrado, o método `404 Not Found` retornará.

## <a name="example"></a>Exemplo

**Solicitação**

Veja um exemplo da solicitação.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Resposta**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Artigos relacionados

- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Saiba mais sobre limites e licenciamento da API](api-terms.md)
- [Noções sobre códigos de erro](api-error-codes.md)
- [APIs de Incidente](api-incident.md)
- [Listar incidentes](api-list-incidents.md)
- [Visão geral dos incidentes](incidents-overview.md)
