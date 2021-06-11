---
title: Cancelar API de ação de máquina
description: Saiba como cancelar uma ação de máquina já lançada
keywords: apis, api gráfica,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879650"
---
#   <a name="cancel-machine-action-api"></a>Cancelar API de ação de máquina 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API

Cancele uma ação de máquina já lançada que ainda não está no estado final (concluída, cancelada, com falha).

## <a name="limitations"></a>Limitações

1.  Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md).

|     Tipo de permissão     |     Permissão     |    Nome de exibição de permissão     |
|-|-|-|
|    <br>Aplicativo    |    <br>Machine.CollectForensic<br>   Machine.Isolate   <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Coletar forenses   <br>Isolar máquina<br>Restringir a execução de código<br>  Máquina de verificação<br>  Máquina de offboard<br>   Parar e quarentena<br>   Executar resposta ao vivo em um computador específico    |
|    <br>Delegada (conta de trabalho ou de estudante)    |    Machine.CollectForensic<br>   Machine.Isolate    <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Coletar forenses<br>   Isolar máquina<br>  Restringir a execução de código<br> Máquina de verificação<br>Máquina de offboard<br> Parar e quarentena<br> Executar resposta ao vivo em um computador específico    |


## <a name="http-request"></a>Solicitação HTTP

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Cabeçalhos de solicitação

| Nome      | Tipo | Descrição                 |
|---------------|----------|---------------------------------|
| Autorização | Cadeia de caracteres   | {token} de portador. Obrigatório.   |
| Content-Type  | string   | application/json. Obrigatório. |

## <a name="request-body"></a>Corpo da solicitação

| Parâmetro | Tipo | Descrição                        |
|---------------|----------|----------------------------------------|
| Comentário       | String   | Comentário para associar à ação de cancelamento.  |

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200, código de resposta Ok com uma entidade Ação de Máquina. Se a entidade de ação do computador com a id especificada não for encontrada - 404 Não Encontrado.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Tópicos relacionados

- [Obter API de ação de máquina](get-machineaction-object.md)