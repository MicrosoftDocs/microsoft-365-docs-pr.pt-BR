---
title: Métodos e propriedades da recomendação
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771592"
---
# <a name="recommendation-resource-type"></a>Tipo de recurso de recomendação

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos
Método |Tipo de retorno |Descrição
:---|:---|:---
[Listar todas as recomendações](get-all-recommendations.md) | Coleção Recommendation | Recupera uma lista de todas as recomendações de segurança que afetam a organização
[Obter recomendação por ID](get-recommendation-by-id.md) | Recomendação | Recupera uma recomendação de segurança por sua ID
[Obter software de recomendação](get-recommendation-software.md)| [Software](software.md) | Recupera uma recomendação de segurança relacionada a um software específico
[Obter dispositivos de recomendação](get-recommendation-machines.md)|Coleção MachineRef | Recupera uma lista de dispositivos associados à recomendação de segurança
[Obter vulnerabilidades de recomendação](get-recommendation-vulnerabilities.md) | [Coleção Vulnerability](vulnerability.md) | Recupera uma lista de vulnerabilidades associadas à recomendação de segurança


## <a name="properties"></a>Propriedades
Propriedade |   Tipo   |   Descrição
:---|:---|:---
id | Cadeia de caracteres | ID de recomendação
productName | Cadeia de caracteres | Nome de software relacionado  
recommendationName | Cadeia de caracteres | Nome da recomendação
Pontos fracos | Longo | Número de vulnerabilidades descobertas
Fornecedor | Cadeia de caracteres | Nome do fornecedor relacionado
recommendedVersion | Cadeia de caracteres | Versão recomendada
recommendationCategory | Cadeia de caracteres | Categoria de recomendação. Os valores possíveis são: "Accounts", "Application", "Network", "OS", "SecurityStack
subCategory | Cadeia de caracteres | Sub-categoria de recomendação
severityScore | Duplo | Impacto potencial da configuração para a Pontuação Segura da Microsoft para Dispositivos da organização (1-10)
publicExploit | Boolean | Exploração pública está disponível 
activeAlert | Boolean | Alerta ativo está associado a essa recomendação
associatedThreats | Coleção String | O relatório de análise de ameaças está associado a essa recomendação
remediationType | Cadeia de caracteres | Tipo de correção. Os valores possíveis são: "ConfigurationChange","Update","Upgrade","Uninstall"
Status | Enum | Status de exceção de recomendação. Os valores possíveis são: "Active" e "Exception"
configScoreImpact | Duplo | Impacto da Pontuação Segura da Microsoft para Dispositivos
exposureImpacte | Duplo | Impacto da pontuação de exposição
totalMachineCount | Longo | Número de dispositivos instalados
exposedMachinesCount | Longo | Número de dispositivos instalados expostos a vulnerabilidades
nonProductivityImpactedAssets | Longo | Número de dispositivos que não são afetados  
relatedComponent | Cadeia de caracteres |  Componente de software relacionado
