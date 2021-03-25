---
title: Métodos e propriedades de software
description: Recupera os principais alertas recentes.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187022"
---
# <a name="software-resource-type"></a>Tipo de recurso de software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

Método |Tipo de retorno |Descrição
:---|:---|:---
[Listar software](get-software.md) | Coleção Software | Listar o inventário de software organizacional.
[Obter software por ID](get-software-by-id.md) | Software | Obter um software específico por sua ID de software.
[Listar distribuição de versão de software](get-software-ver-distribution.md)| Coleção Distribution | Listar distribuição de versão de software por ID de software.
[Listar máquinas por software](get-machines-by-software.md)| Coleção MachineRef | Recupere uma lista de dispositivos associados à ID de software.
[Listar vulnerabilidades por software](get-vuln-by-software.md) | [Coleção Vulnerability](vulnerability.md) | Recupere uma lista de vulnerabilidades associadas à ID do software.
[Obter KBs ausentes](get-missing-kbs-software.md) | Coleção KB | Obter uma lista de KBs ausentes associados à ID de software

## <a name="properties"></a>Propriedades

Propriedade |   Tipo   |   Descrição
:---|:---|:---
id | Cadeia de caracteres | Software ID
Nome | Cadeia de caracteres | Nome do software
Fornecedor | Cadeia de caracteres | Nome do fornecedor de software
Pontos fracos | Longo | Número de vulnerabilidades descobertas
publicExploit | Booleano | A exploração pública existe para algumas das vulnerabilidades
activeAlert | Booleano | Alerta ativo está associado a este software
exposedMachines | Longo | Número de dispositivos expostos
impactScore | Duplo | Impacto da pontuação de exposição deste software
