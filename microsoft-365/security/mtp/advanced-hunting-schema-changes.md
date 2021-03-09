---
title: Nomenisar alterações no esquema de busca avançada do Microsoft 365 Defender
description: Controlar e revisar as alterações de nomenis e colunas no esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados, alterações de nomentar, renomear, Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: 948c8bb5c1e6b67f6de355bc532c6b14d5a83933
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551867"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Esquema de busca avançado - Alterações de nomenis

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

O [esquema de busca avançado](advanced-hunting-schema-tables.md) é atualizado regularmente para adicionar novas tabelas e colunas. Em alguns casos, os nomes de colunas existentes são renomeados ou substituídos para melhorar a experiência do usuário. Consulte este artigo para revisar as alterações de nomeniso que podem afetar suas consultas.

As alterações de nomenisagem são aplicadas automaticamente a consultas salvas no centro de segurança, incluindo consultas usadas por regras de detecção personalizadas. Você não precisa atualizar essas consultas manualmente. No entanto, você precisará atualizar as seguintes consultas:
- Consultas que são executados usando a API
- Consultas salvas em outro lugar fora do centro de segurança

## <a name="december-2020"></a>Dezembro de 2020

| Nome da tabela | Nome da coluna original | Novo nome da coluna | Motivo da alteração
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Comentários do cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Comentários do cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Comentários do cliente |

## <a name="january-2021"></a>Janeiro de 2021

| Nome da coluna | Nome do valor original | Novo nome de valor | Motivo da alteração
|--|--|--|--|
| `DetectionSource` | MCAS |    Segurança no aplicativo na nuvem da Microsoft | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivírus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  TI personalizada | Rebranding |
| `DetectionSource` | OfficeATP | Obter o Microsoft Defender para Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    O que é o Microsoft Defender para Identidade? | Rebranding |
| `DetectionSource` | CustomDetection   | Detecção personalizada | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Investigação automatizada | Rebranding |
| `DetectionSource` | ThreatExperts | Especialistas em ameaças da Microsoft | Rebranding |
| `DetectionSource` | TI de terceiros | Sensores de terceiros | Rebranding |
| `ServiceSource` | O Microsoft Defender ATP| Microsoft Defender para Ponto de Extremidade | Rebranding |
|`ServiceSource` |Proteção contra Ameaças da Microsoft   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Obter o Microsoft Defender para Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |O que é o Microsoft Defender para Identidade? | Rebranding |

`DetectionSource`está disponível na tabela [AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`está disponível nas tabelas [AlertEvidence e](advanced-hunting-alertevidence-table.md) [AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Fevereiro de 2021

1. Nas tabelas [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) e [EmailEvents,](advanced-hunting-emailevents-table.md) as colunas e foram `MalwareFilterVerdict` `PhishFilterVerdict` substituídas pela `ThreatTypes` coluna. As `MalwareDetectionMethod` `PhishDetectionMethod` colunas e também foram substituídas pela `DetectionMethods` coluna. Esse fluxo permite que forneçamos mais informações nas novas colunas. O mapeamento é fornecido abaixo.

| Nome da tabela | Nome da coluna original | Novo nome da coluna | Motivo da alteração
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Incluir mais métodos de detecção |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Incluir mais tipos de ameaça |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Incluir mais métodos de detecção |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Incluir mais tipos de ameaça |


2. Nas `EmailAttachmentInfo` `EmailEvents` tabelas e, a `ThreatNames` coluna foi adicionada para dar mais informações sobre a ameaça de email. Esta coluna contém valores como Spam ou Phish.

3. Na tabela [DeviceInfo,](advanced-hunting-deviceinfo-table.md) a coluna foi substituída pela coluna `DeviceObjectId` com base nos comentários do `AadDeviceId` cliente.

4. Na tabela [DeviceEvents,](advanced-hunting-deviceevents-table.md) vários nomes ActionType foram modificados para refletir melhor a descrição da ação. Detalhes das alterações podem ser encontrados abaixo.

| Nome da tabela | Nome actionType original | Novo nome ActionType | Motivo da alteração
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Comentários do cliente |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Comentários do cliente |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Comentários do cliente |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Comentários do cliente |






## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)