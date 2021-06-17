---
title: Atualizar a API da entidade do computador
description: Saiba como atualizar marcas de máquina usando essa API. Você pode atualizar as marcas e as propriedades devicevalue.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985538"
---
# <a name="update-machine"></a>Atualizar máquina 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Atualiza as propriedades do [Machine existente.](machine.md)
<br>As propriedades atualizáveis são: ```machineTags``` e ```deviceValue``` .


## <a name="limitations"></a>Limitações
1. Você pode atualizar os máquinas que estão disponíveis na API. 
2. A máquina de atualização apenas anexa marcas à coleção de marcas. Se as marcas existirem, elas devem ser incluídas na coleção de marcas no corpo.
3. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Machine.ReadWrite.All | 'Ler e gravar informações do computador para todos os computador'
Delegado (conta corporativa ou de estudante) | Machine.ReadWrite | 'Informações de máquina de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: "Investigação de alertas". Para obter mais informações, consulte [Create and manage roles](user-roles.md).
>- O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos. Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).

## <a name="http-request"></a>Solicitação HTTP
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
No corpo da solicitação, fornece os valores dos campos relevantes que devem ser atualizados.
<br>Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade. 
<br>Para melhor desempenho, você não deve incluir valores existentes que não mudaram.

Propriedade | Tipo | Descrição
:---|:---|:---
machineTags | Conjunto de cadeias de caracteres | Conjunto de [marcas de](machine.md) máquina.
deviceValue | Núm anulado | O [valor do dispositivo](tvm-assign-device-value.md). Os valores possíveis são: 'Normal', 'Baixo' e 'Alto'.

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e a entidade [do](machine.md) computador no corpo da resposta com as propriedades atualizadas. Se a coleção de marcas de máquina no corpo não conter marcas de máquina existentes - 400 Entrada Inválida e uma mensagem informando a marca/s ausente.
Se o computador com a ID especificada não for encontrado - 404 Não Encontrado.


## <a name="example"></a>Exemplo

**Solicitação**

Veja um exemplo da solicitação.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
