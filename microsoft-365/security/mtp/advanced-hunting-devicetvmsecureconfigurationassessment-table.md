---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre os eventos de avaliação de segurança na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançada. Esses eventos & gerenciamento de vulnerabilidades fornecem informações do dispositivo, bem como detalhes da configuração de segurança, impacto e informações de conformidade.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades do &, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931093"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.|
| `Timestamp` | datetime | Data e hora em que o registro foi gerado |
| `ConfigurationId` | string | Identificador exclusivo para uma configuração específica |
| `ConfigurationCategory` | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança |
| `ConfigurationSubcategory` | string | Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos. |
| `ConfigurationImpact` | string | Impacto avaliado da configuração na classificação total (1-10) |
| `IsCompliant` | booliano | Indica se a configuração ou política está configurada corretamente |
| `IsApplicable` | booliano | Indica se a configuração ou a política se aplica ao dispositivo |
| `Context` | string | Informações contextuais adicionais sobre a configuração ou a política |
| `IsExpectedUserImpactCompliant` | booliano | Indica se haverá impacto ao usuário se a configuração ou a política for aplicada |

## <a name="related-topics"></a>Tópicos relacionados

- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral do Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
