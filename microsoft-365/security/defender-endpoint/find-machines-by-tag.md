---
title: Encontrar dispositivos por API de marca
description: Encontre todos os dispositivos que contenham a marca specifc
keywords: apis, apis com suporte, obter, dispositivo, encontrar, encontrar dispositivo, por marca, marca
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771160"
---
# <a name="find-devices-by-tag-api"></a>Encontrar dispositivos por API de marca

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Encontre [máquinas](machine.md) por [marca](machine-tags.md).
<br>```startswith``` a consulta é suportada. 

## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Machine.Read.All |  'Ler todos os perfis de máquina'
Aplicativo |   Machine.ReadWrite.All | 'Ler e gravar todas as informações do computador'
Delegado (conta corporativa ou de estudante) | Machine.Read | 'Ler informações do computador'
Delegado (conta corporativa ou de estudante) | Machine.ReadWrite | 'Informações de máquina de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
> - A resposta incluirá apenas dispositivos aos que o usuário tem acesso com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)
> - O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)
> - A resposta incluirá apenas dispositivos aos que o usuário tem acesso com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.

## <a name="request-uri-parameters"></a>Solicitar parâmetros URI

Nome | Tipo | Descrição
:---|:---|:---
tag | Cadeia de caracteres | O nome da marca. **Obrigatório**.
useStartsWithFilter | Booliano | Quando definida como true, a pesquisa encontrará todos os dispositivos com o nome da marca que começa com a marca determinada na consulta. O padão é falso. **Opcional**.

## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se bem-sucedido - 200 OK com a lista dos máquinas no corpo da resposta.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```