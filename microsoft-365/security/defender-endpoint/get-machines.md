---
title: API de máquinas de lista
description: Saiba como usar a API de máquinas de lista para recuperar uma coleção de máquinas que se comunicaram com a nuvem do Microsoft Defender ATP.
keywords: apis, api gráfica, apis com suporte, obter, dispositivos
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200372"
---
# <a name="list-machines-api"></a>API de máquinas de lista

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API
Recupera uma coleção de [máquinas](machine.md) que se comunicaram com o Microsoft Defender para nuvem do Ponto de Extremidade.
<br>Oferece suporte [a consultas OData V4.](https://www.odata.org/documentation/)
<br>A consulta OData é suportada `$filter` em: `computerDnsName` , , , e `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .
<br>Consulte exemplos em [Consultas OData com o Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Limitações
1. Você pode obter dispositivos vistos pela última vez de acordo com o período de retenção configurado.
2. O tamanho máximo da página é 10.000.
3. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora. 


## <a name="permissions"></a>Permissões

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Machine.Read.All |  'Ler todos os perfis de máquina'
Aplicativo |   Machine.ReadWrite.All | 'Ler e gravar todas as informações do computador'
Delegada (conta corporativa ou de estudante) | Machine.Read | 'Ler informações do computador'
Delegada (conta corporativa ou de estudante) | Machine.ReadWrite | 'Informações de máquina de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)
>- A resposta incluirá apenas dispositivos aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se houver êxito e houver máquinas - 200 OK com a lista de [entidades](machine.md) do computador no corpo. Se nenhum aparelho recente - 404 Não Encontrado.


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**Response**

Veja a seguir um exemplo da resposta.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Tópicos relacionados
- [Consultas OData com o Microsoft Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)
