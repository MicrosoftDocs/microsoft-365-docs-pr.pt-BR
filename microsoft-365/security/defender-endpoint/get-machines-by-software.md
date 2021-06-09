---
title: Listar dispositivos por software
description: Recupere uma lista de dispositivos que têm esse software instalado.
keywords: apis, api gráfica, apis com suporte, obter, listar dispositivos, lista de dispositivos, listar dispositivos por software, Api de tvm do Microsoft Defender para Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845373"
---
# <a name="list-devices-by-software"></a>Listar dispositivos por software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupere uma lista de referências de dispositivo que tenha esse software instalado.

## <a name="permissions"></a>Permissões
Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo | Software.Read.All | 'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'
Delegado (conta corporativa ou de estudante) | Software.Read | 'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'

## <a name="http-request"></a>Solicitação HTTP
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Nome        | Tipo | Descrição
|:--------------|:-------|:--------------|
| Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação
Vazio

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e uma lista de dispositivos com o software instalado no corpo. 


## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

**Response**

Veja a seguir um exemplo da resposta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciamento de vulnerabilidades baseadas em & risco](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventário & software de vulnerabilidade](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
