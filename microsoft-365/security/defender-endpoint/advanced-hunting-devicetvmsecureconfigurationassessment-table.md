---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre & eventos de avaliação de segurança do Gerenciamento de Vulnerabilidades na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançado. Esses eventos fornecem informações do dispositivo, bem como detalhes de configuração de segurança, impacto e informações de conformidade.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054097"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](next-gen-threat-and-vuln-mgt.md). Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `OSPlatform` | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.|
| `Timestamp` | datetime |Data e hora em que o registro foi gerado |
| `ConfigurationId` | string | Identificador exclusivo para uma configuração específica |
| `ConfigurationCategory` | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança |
| `ConfigurationSubcategory` | string |Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos. |
| `ConfigurationImpact` | string | Impacto avaliado da configuração na classificação total (1-10) |
| `IsCompliant` | booliano | Indica se a configuração ou política está configurada corretamente |
| `IsApplicable` | booliano | Indica se a configuração ou a política se aplica ao dispositivo |
| `Context` | cadeia de caracteres | Informações contextuais adicionais sobre a configuração ou a política |
| `IsExpectedUserImpactCompliant` | booliano | Indica se haverá impacto do usuário se a configuração ou a política for aplicada |

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
- [Visão geral do Gerenciamento de Vulnerabilidades e Ameaças](next-gen-threat-and-vuln-mgt.md)