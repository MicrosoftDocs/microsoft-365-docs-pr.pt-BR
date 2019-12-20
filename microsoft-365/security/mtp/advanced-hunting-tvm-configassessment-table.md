---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre os eventos de avaliação de segurança de Gerenciamento de Vulnerabilidades e Ameaças na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançada. Esses eventos fornecem informações do computador, bem como informações de conformidade, impacto e detalhes da configuração de segurança.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de ameaças e vulnerabilidades, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d03b278fbf029b08b476f20292315807a3f5e32a
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808616"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.|
| `Timestamp` | datetime | Data e hora em que o registro foi gerado |
| `ConfigurationId` | string | Identificador exclusivo para uma configuração específica |
| `ConfigurationCategory` | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança |
| `ConfigurationSubcategory` | string | Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos. |
| `ConfigurationImpact` | string | Impacto avaliado da configuração na classificação total (1-10) |
| `IsCompliant` | booliano | Indica se a configuração ou política está configurada corretamente |

## <a name="related-topics"></a>Tópicos relacionados

- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral do Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
