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
ms.openlocfilehash: da00c43ae9ba5b129129027df16f49ef80b8757d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288162"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="e7bdb-103">Criar notificações para atividades de correspondência exata de dados</span><span class="sxs-lookup"><span data-stu-id="e7bdb-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="e7bdb-104">Ao [criar tipos de informações confidenciais personalizadas com correspondência exata de dados (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), uma série de atividades são criadas no [log de auditoria](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="e7bdb-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="e7bdb-105">Você pode usar o cmdlet do PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) para criar notificações que o informam quando estas atividades ocorrem:</span><span class="sxs-lookup"><span data-stu-id="e7bdb-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="e7bdb-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="e7bdb-106">CreateSchema</span></span>
- <span data-ttu-id="e7bdb-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="e7bdb-107">EditSchema</span></span>
- <span data-ttu-id="e7bdb-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="e7bdb-108">RemoveSchema</span></span>
- <span data-ttu-id="e7bdb-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="e7bdb-109">UploadDataFailed</span></span>
- <span data-ttu-id="e7bdb-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="e7bdb-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="e7bdb-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e7bdb-111">Pre-requisites</span></span>

<span data-ttu-id="e7bdb-112">Você deve usar uma das seguintes contas:</span><span class="sxs-lookup"><span data-stu-id="e7bdb-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="e7bdb-113">um administrador global</span><span class="sxs-lookup"><span data-stu-id="e7bdb-113">a global admin</span></span>
- <span data-ttu-id="e7bdb-114">administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e7bdb-114">compliance administrator</span></span>
- <span data-ttu-id="e7bdb-115">Administrador do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e7bdb-115">Exchange Online administrator</span></span>

<span data-ttu-id="e7bdb-116">Para saber mais sobre permissões DLP, confira [Permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="e7bdb-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="e7bdb-117">A classificação baseada em EDM está incluída nestas assinaturas</span><span class="sxs-lookup"><span data-stu-id="e7bdb-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="e7bdb-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e7bdb-118">Office 365 E5</span></span>
- <span data-ttu-id="e7bdb-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e7bdb-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="e7bdb-120">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e7bdb-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="e7bdb-121">Proteção e governança de informações do Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="e7bdb-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="e7bdb-122">Para saber mais sobre o licenciamento DLP, confira [Diretrizes de licenciamento do Microsoft 365 de conformidade e segurança](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="e7bdb-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="e7bdb-123">Configurar notificações para atividades de EDM</span><span class="sxs-lookup"><span data-stu-id="e7bdb-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="e7bdb-124">Conectar-se ao PowerShell do [Centro de Conformidade e Segurança](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="e7bdb-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)</span></span> 

2. <span data-ttu-id="e7bdb-125">Execute o cmdlet `New-ProtectionAlert` usando a atividade para a qual você deseja criar a notificação.</span><span class="sxs-lookup"><span data-stu-id="e7bdb-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="e7bdb-126">Por exemplo, execute se você quiser ser notificado quando a ação **UploadDataCompleted** ocorrer,</span><span class="sxs-lookup"><span data-stu-id="e7bdb-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="e7bdb-127">você pode executar para o **UploadDataFailed**</span><span class="sxs-lookup"><span data-stu-id="e7bdb-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="e7bdb-128">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7bdb-128">Related articles</span></span>

- [<span data-ttu-id="e7bdb-129">Criar tipos de informações confidenciais personalizadas com combinação exata de dados (EDM)</span><span class="sxs-lookup"><span data-stu-id="e7bdb-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="e7bdb-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="e7bdb-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)