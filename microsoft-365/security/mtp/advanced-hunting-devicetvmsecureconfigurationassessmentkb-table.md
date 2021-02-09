---
title: Tabela DeviceTvmSecureConfigurationAssessmentKB no esquema de busca avançada
description: Saiba mais sobre as várias configurações seguras avaliadas pelo Gerenciamento de Vulnerabilidades e Ameaças na tabela DeviceTvmSecureConfigurationAssessmentKB do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades do &, TVM, gerenciamento de dispositivos, configuração de segurança, estrutura MITRE ATT&CK, base de conhecimento, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cf4204767843b9a9e0b0bbfecc2d3fc50db531fc
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145446"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A tabela `DeviceTvmSecureConfigurationAssessmentKB` no esquema de busca avançada contém informações sobre as diversas configurações seguras — por exemplo, se um dispositivo possui atualizações automáticas ativadas, verificado pela [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Também inclui informações de risco, benchmarks relacionados do setor e técnicas e táticas aplicáveis do MITRE ATT & CK. Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `ConfigurationId` | string | Identificador exclusivo para uma configuração específica |
| `ConfigurationImpact` | string | Impacto avaliado da configuração na classificação total (1-10) |
| `ConfigurationName` | string | Exibir o nome da configuração |
| `ConfigurationDescription` | string | Descrição da configuração |
| `RiskDescription` | string | Descrição do risco associado |
| `ConfigurationCategory` | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança|
| `ConfigurationSubcategory` | string |Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos. |
| `ConfigurationBenchmarks` | string | Lista de benchmarks da indústria recomendando a mesma configuração ou configuração similar |
| `Tags` | string | Rótulos que representam vários atributos usados para identificar ou categorizar uma configuração de segurança |
| `RemediationOptions` | string | Ações recomendadas para reduzir ou resolver quaisquer riscos associados |

## <a name="related-topics"></a>Tópicos relacionados

- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral do Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
