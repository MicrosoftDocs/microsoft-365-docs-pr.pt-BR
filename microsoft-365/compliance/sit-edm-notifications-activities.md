---
title: Criar notificações para atividades de correspondência exata de dados
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
description: Aprenda como criar notificações para atividades de correspondência exata de dados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341671"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Criar notificações para atividades de correspondência exata de dados

Ao [criar tipos de informações confidenciais personalizadas com correspondência exata de dados (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), uma série de atividades são criadas no [log de auditoria](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log). Você pode usar o cmdlet do PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) para criar notificações que o informam quando estas atividades ocorrem:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>Pré-requisitos

Você deve usar uma das seguintes contas:

- um administrador global
- administrador de conformidade
- Administrador do Exchange Online

Para saber mais sobre permissões DLP, confira [Permissões](data-loss-prevention-policies.md#permissions).

A classificação baseada em EDM está incluída nestas assinaturas:

- Office 365 E5
- Microsoft 365 E5
- Conformidade do Microsoft 365 E5
- Proteção e governança de informações do Microsoft E5/A5

Para saber mais sobre licenciamento DLP, consulte [Diretrizes de licenciamento do Microsoft 365 de conformidade e segurança](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Configurar as notificações para a atividades de EDM

1. Conectar ao [PowerShell do Centro de Conformidade e Segurança](/powershell/exchange/connect-to-scc-powershell).

2. Execute o cmdlet `New-ProtectionAlert` usando a atividade para a qual você deseja criar a notificação.  Por exemplo, se você quiser ser notificado quando a ação **UploadDataCompleted** ocorrer, execute:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    para o **UploadDataFailed** você pode executar:
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>Artigos relacionados

- [Criar tipos de informações confidenciais personalizadas com combinação exata de dados (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)