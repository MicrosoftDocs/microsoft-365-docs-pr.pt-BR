---
title: Definir API de valor do dispositivo
description: Saiba como especificar o valor de um dispositivo usando uma API do Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, marcas, marcas de máquina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33692ddf62153c0a6aa8f84568d69803af113bc6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185558"
---
# <a name="set-device-value-api"></a>Definir API de valor do dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API

De definir o valor do dispositivo de um [Computador específico.](machine.md)<br>
Confira [atribuir valores de dispositivo](tvm-assign-device-value.md) para obter mais informações.

## <a name="limitations"></a>Limitações

1. Você pode postar em dispositivos vistos pela última vez de acordo com o período de retenção configurado.

2. Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.


## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |    Permissão    |    Nome de exibição de permissão
:---|:---|:---
Aplicativo |    Machine.ReadWrite.All |    'Ler e gravar todas as informações do computador'
Delegada (conta corporativa ou de estudante) | Machine.ReadWrite | 'Informações de máquina de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>
>- O usuário precisa ter pelo menos a seguinte permissão de função: "Gerenciar configuração de segurança". Para obter mais (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)
>- O usuário precisa ter acesso ao computador, com base nas configurações do grupo de máquinas (Consulte Criar e gerenciar grupos [de máquinas](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | string | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:

Parâmetro |    Tipo    | Descrição
:---|:---|:---
DeviceValue |    Enum |    Valor do dispositivo. Os valores permitidos são: 'Normal', 'Baixo' e 'Alto'. **Obrigatório**.

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200 - Código de resposta ok e o Computador atualizado no corpo da resposta.

## <a name="example"></a>Exemplo

**Solicitação**

Aqui está um exemplo de uma solicitação que adiciona a marca de máquina.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
