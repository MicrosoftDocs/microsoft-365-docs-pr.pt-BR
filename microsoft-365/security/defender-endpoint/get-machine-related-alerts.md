---
title: Obter API de alertas relacionados ao computador
description: Saiba como usar a API Obter alertas relacionados ao computador para recuperar todos os alertas relacionados a um dispositivo específico no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivos, relacionados, alertas
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199246"
---
# <a name="get-machine-related-alerts--api"></a>Obter API de alertas relacionados ao computador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API
Recupera todos [os Alertas](alerts.md) relacionados a um dispositivo específico.


## <a name="limitations"></a>Limitações
1. Você pode consultar os dispositivos atualizados pela última vez de acordo com o período de retenção configurado.
2. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Alert.Read.All |    'Ler todos os alertas'
Aplicativo |   Alert.ReadWrite.All |   'Ler e gravar todos os alertas'
Delegada (conta corporativa ou de estudante) | Alert.Read | 'Alertas de leitura'
Delegada (conta corporativa ou de estudante) | Alert.ReadWrite | 'Alertas de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)
>- O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e [gerenciar grupos de dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se houver êxito e o dispositivo existir - 200 OK com a [lista](alerts.md) de entidades de alerta no corpo. Se o dispositivo não foi encontrado - 404 Não Encontrado.
