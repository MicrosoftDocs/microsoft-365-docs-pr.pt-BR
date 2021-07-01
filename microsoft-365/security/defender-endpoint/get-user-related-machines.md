---
title: Obter API de máquinas relacionadas ao usuário
description: Saiba como usar a API obter máquinas relacionadas ao usuário para recuperar uma coleção de dispositivos relacionados a uma ID de usuário no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, usuário, alertas relacionados ao usuário
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229450"
---
# <a name="get-user-related-machines-api"></a>Obter API de máquinas relacionadas ao usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API
Recupera uma coleção de dispositivos relacionados a uma determinada ID de usuário.

## <a name="limitations"></a>Limitações

Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |Permissão|Nome de exibição de permissão
:---|:---|:---
Aplicativo |Machine.Read.All|'Ler todos os perfis de máquina'
Aplicativo |Machine.ReadWrite.All |'Ler e gravar todas as informações do computador'
Delegada (conta corporativa ou de estudante) | Machine.Read | 'Ler informações do computador'
Delegada (conta corporativa ou de estudante) | Machine.ReadWrite | 'Informações de máquina de leitura e gravação'

> [!NOTE]
> Ao obter um token usando credenciais de usuário:
>
> - O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados". Para obter mais informações, consulte [Create and manage roles](user-roles.md))
> - A resposta incluirá apenas dispositivos que o usuário pode acessar, com base nas configurações do grupo de dispositivos. Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).

## <a name="http-request"></a>Solicitação HTTP

```http
GET /api/users/{id}/machines
```

**A ID não é o UPN completo, mas apenas o nome de usuário. (por exemplo, para recuperar máquinas para user1@contoso.com /api/users/user1/machines)**

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | String | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

Vazio

## <a name="response"></a>Resposta

Se bem-sucedido e o usuário existir - 200 OK com a lista de [entidades](machine.md) do computador no corpo. Se o usuário não existir - 404 Não Encontrado.

## <a name="example"></a>Exemplo

### <a name="request"></a>Solicitação

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
