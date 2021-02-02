---
title: Alterações de nomeação no esquema de busca avançada do Microsoft 365 Defender
description: Acompanhar e revisar as tabelas e colunas de alterações de nomeação no esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados, alterações de nomeação, renomear, Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066864"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Esquema de busca avançada - Alterações de nomeação

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

O [esquema de busca avançada é](advanced-hunting-schema-tables.md) atualizado regularmente para adicionar novas tabelas e colunas. Em alguns casos, os nomes de colunas existentes são renomeados ou substituídos para melhorar a experiência do usuário. Consulte este artigo para revisar as alterações de nomeação que podem afetar suas consultas.

As alterações de nomeação são aplicadas automaticamente às consultas salvas no centro de segurança, incluindo consultas usadas por regras de detecção personalizadas. Você não precisa atualizar essas consultas manualmente. No entanto, você precisará atualizar as seguintes consultas:
- Consultas que são executados usando a API
- Consultas salvas em outro lugar fora da central de segurança

## <a name="december-2020"></a>Dezembro de 2020

| Nome da tabela | Nome da coluna original | Novo nome de coluna | Motivo da alteração
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Comentários dos clientes |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Comentários dos clientes |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Comentários dos clientes |

## <a name="january-2021"></a>Janeiro de 2021

| Nome da coluna | Nome do valor original | Nome do novo valor | Motivo da alteração
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivírus | Renomear |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Renomear |
| `DetectionSource` | CustomerTI |  TI personalizada | Renomear |
| `DetectionSource` | OfficeATP | Microsoft Defender para Office 365 | Renomear |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Renomear |
| `DetectionSource` | AzureATP |    Microsoft Defender para Identidade? | Renomear |
| `DetectionSource` | CustomDetection   | Detecção personalizada | Renomear |
| `DetectionSource` | AutomatedInvestigation |Investigação automatizada | Rebranding |
| `DetectionSource` | ThreatExperts | Especialistas em ameaças da Microsoft | Rebranding |
| `DetectionSource` | TI de terceiros | Sensores de terceiros | Rebranding |
| `ServiceSource` | O Microsoft Defender ATP| Proteção Avançada contra Ameaças do Microsoft Defender | Rebranding |
|`ServiceSource` |Proteção contra Ameaças da Microsoft   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender para Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender para Identidade? | Rebranding |

`DetectionSource`está disponível na [tabela AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`está disponível nas [tabelas AlertEvidence](advanced-hunting-alertevidence-table.md) e [AlertInfo.](advanced-hunting-alertinfo-table.md) 
## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)