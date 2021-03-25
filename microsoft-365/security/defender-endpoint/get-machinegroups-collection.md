---
title: Obter API da coleção de grupos de máquinas RBAC
description: Saiba como usar a API da coleção Get KB para recuperar uma coleção de grupos de dispositivos RBAC na Proteção Avançada contra Ameaças do Microsoft Defender.
keywords: apis, api gráfica, apis com suporte, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166288"
---
# <a name="get-kb-collection-api"></a>Obter API de coleção KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Recupera uma coleção de grupos de dispositivos RBAC.

## <a name="permissions"></a>Permissões
O usuário precisa de permissões de leitura.

## <a name="http-request"></a>Solicitação HTTP
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Cabeçalho | Valor 
:---|:---
Autorização | Portador {token}. **Obrigatório**.
Tipo de conteúdo | application/json

## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se bem-sucedido - 200 OK.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Response**

Veja a seguir um exemplo da resposta.
A id de campo contém **id** do grupo de dispositivos e igual ao campo **rbacGroupId** em informações de dispositivos. O **campo desagrupado** só é verdadeiro para um grupo para todos os dispositivos que não foram atribuídos a nenhum grupo. Esse grupo, como de costume, tem o nome "UnassignedGroup".

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
