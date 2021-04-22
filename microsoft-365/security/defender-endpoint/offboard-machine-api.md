---
title: API de máquina de offboard
description: Saiba como usar uma API para offboard de um dispositivo do Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, coletar pacote de investigação
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
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934172"
---
# <a name="offboard-machine-api"></a>API de máquina de offboard

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Dispositivo offboard do Defender para Ponto de Extremidade.


## <a name="limitations"></a>Limitações
 - Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> Essa API é suportada no Windows 10, versão 1703 e posterior, ou no Windows Server 2019 e posterior. Essa API não tem suporte em dispositivos MacOS ou Linux.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Machine.Offboard |  'Máquina de offboard'
Delegada (conta corporativa ou de estudante) |    Machine.Offboard |  'Máquina de offboard'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa de função de AD 'Administrador Global'
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
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

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
