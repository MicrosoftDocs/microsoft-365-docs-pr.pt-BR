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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719399"
---
# <a name="update-incidents-api"></a>Atualizar a API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Descrição da API

Atualiza as propriedades de um incidente existente. As propriedades atualizáveis são: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` e ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cotas, alocação de recursos e outras restrições

1. Você pode fazer até 50 chamadas por minuto ou 1500 por hora, antes de atingir o limite de limitação.
2. Você só pode definir a `determination` propriedade se `classification` estiver definida como TruePositive.

Se sua solicitação for limitada, ela retornará um código de `429` resposta. O corpo da resposta indicará o horário em que você pode começar a fazer novas chamadas.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar esta API. Para saber mais, incluindo como escolher permissões, consulte [Access The Microsoft 365 defender APIs](api-access.md).

Tipo de permissão | Permissão | Nome para exibição da permissão
-|-|-
Aplicativo | Incident. ReadWrite. All | Ler e gravar todos os incidentes
Delegada (conta corporativa ou de estudante) | Incident. ReadWrite | Ler e gravar incidentes

> [!NOTE]
> Ao obter um token usando as credenciais do usuário, o usuário precisa ter permissão para atualizar o incidente no Portal.

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

No corpo da solicitação, forneça os valores para os campos que devem ser atualizados. As propriedades existentes que não estão incluídas no corpo da solicitação manterão seus valores, a menos que tenham que ser recalculados devido a alterações nos valores relacionados. Para obter o melhor desempenho, você deve omitir os valores existentes que não foram alterados.

Propriedade | Tipo | Descrição
-|-|-
status | Enum | Especifica o status atual do alerta. Os valores possíveis são: ```Active``` , ```Resolved``` , e ```Redirected``` .
assignedTo | string | Proprietário do incidente.
classificação | Enum | Especificação do alerta. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do alerta. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cadeia de caracteres | Lista de marcas de incidente.

## <a name="response"></a>Resposta

Se bem-sucedido, este método retorna `200 OK` . O corpo da resposta conterá a entidade de incidente com propriedades atualizadas. Se um incidente com a ID especificada não for encontrado, o método retornará `404 Not Found` .

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

- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Entender códigos de erro](api-error-codes.md)
- [APIs de Incidente](api-incident.md)
- [Listar incidentes](api-list-incidents.md)
- [Visão geral dos incidentes](incidents-overview.md)
