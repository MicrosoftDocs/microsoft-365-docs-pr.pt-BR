---
title: Criar notificações para atividades de correspondência exata de dados (pré-visualização)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda a criar notificações para atividades de correspondência exata de dados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919357"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a>Criar notificações para atividades de correspondência exata de dados (pré-visualização)

Ao [criar tipos de informações confidenciais personalizadas com correspondência exata de dados (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), uma série de atividades são criadas no [log de auditoria](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log). Você pode usar o cmdlet do PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) para criar notificações que o informam quando estas atividades ocorrem:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
> A capacidade de criar notificações para atividades de EDM está disponível apenas para as nuvens de World Wide e de GCC.

## <a name="pre-requisites"></a>Pré-requisitos

Você deve usar uma das seguintes contas:

- um administrador global
- administrador de conformidade
- Administrador do Exchange Online

Para saber mais sobre permissões DLP, confira [Permissões](data-loss-prevention-policies.md#permissions).

A classificação baseada em EDM está incluída nestas assinaturas

- Office 365 E5
- Microsoft 365 E5
- Conformidade do Microsoft 365 E5
- Proteção e governança de informações do Microsoft E5/A5

Para saber mais sobre o licenciamento DLP, confira [Diretrizes de licenciamento do Microsoft 365 de conformidade e segurança](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="configure-notifications-for-edm-activities"></a>Configurar notificações para atividades de EDM

1. Conectar-se ao PowerShell do [Centro de Conformidade e Segurança](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps) 

2. Execute o cmdlet `New-ProtectionAlert` usando a atividade para a qual você deseja criar a notificação.  Por exemplo, execute se você quiser ser notificado quando a ação **UploadDataCompleted** ocorrer,

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

você pode executar para o **UploadDataFailed**

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Artigos relacionados

- [Criar tipos de informações confidenciais personalizadas com combinação exata de dados (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)