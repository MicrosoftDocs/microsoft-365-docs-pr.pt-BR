---
title: Isolar a API do computador
description: Saiba como usar a API isolar máquina para isolar um dispositivo de acessar rede externa no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, isolar dispositivo
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
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772108"
---
# <a name="isolate-machine-api"></a>Isolar a API do computador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Isola um dispositivo de acessar a rede externa.


## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Machine.Isolate |   'Isolar máquina'
Delegado (conta corporativa ou de estudante) | Machine.Isolate |  'Isolar máquina'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)


## <a name="http-request"></a>Solicitação HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | string | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:

Parâmetro | Tipo    | Descrição
:---|:---|:---
Comentário |   String |    Comentário para associar à ação. **Obrigatório**.
IsolationType   | Cadeia de caracteres |  Tipo de isolamento. Os valores permitidos são: 'Completo' ou 'Seletivo'.

**IsolationType** controla o tipo de isolamento a ser feito e pode ser um dos seguintes:
- Full – Isolamento total
- Seletiva – Restringir apenas o conjunto limitado de aplicativos de acessar a rede (consulte Isolar dispositivos [da rede](respond-machine-alerts.md#isolate-devices-from-the-network) para obter mais detalhes)


## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Para liberar um dispositivo de isolamento, consulte [Release device from isolation](unisolate-machine.md).
