---
title: Métodos e propriedades de pontuação
description: Recupera a pontuação de exposição da sua organização, a pontuação segura do dispositivo e a pontuação de exposição por grupo de dispositivos
keywords: apis, api gráfica, apis com suporte, pontuação, pontuação de exposição, pontuação segura do dispositivo, pontuação de exposição por grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500950"
---
# <a name="score-resource-type"></a>Tipo de recurso score

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

Método |Tipo de retorno |Descrição
:---|:---|:---
[Obter pontuação de exposição](get-exposure-score.md) | [Pontuação](score.md) | Obter a pontuação de exposição organizacional.
[Obter pontuação segura do dispositivo](get-device-secure-score.md) | [Pontuação](score.md) | Obter a pontuação segura do dispositivo organizacional.
[Listar pontuação de exposição por grupo de dispositivos](get-machine-group-exposure-score.md)| [Pontuação](score.md) | Listar pontuações por grupo de dispositivos.

## <a name="properties"></a>Propriedades

Propriedade |  Tipo    |   Descrição
:---|:---|:---
Pontuação | Duplo | A pontuação atual.
Time | DateTime | A data e a hora em que a chamada para essa API foi feita.
RbacGroupName | Cadeia de caracteres | O nome do grupo de dispositivos.
