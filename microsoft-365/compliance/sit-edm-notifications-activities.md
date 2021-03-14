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
ms.openlocfilehash: a537cffe253fa20cf6838ddf3fd9a51ec440fe76
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766686"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="f5719-103">Criar notificações para atividades de correspondência exata de dados (pré-visualização)</span><span class="sxs-lookup"><span data-stu-id="f5719-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="f5719-104">Ao [criar tipos de informações confidenciais personalizadas com correspondência exata de dados (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), uma série de atividades são criadas no [log de auditoria](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="f5719-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="f5719-105">Você pode usar o cmdlet do PowerShell [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) para criar notificações que o informam quando estas atividades ocorrem:</span><span class="sxs-lookup"><span data-stu-id="f5719-105">You can use the [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="f5719-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="f5719-106">CreateSchema</span></span>
- <span data-ttu-id="f5719-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="f5719-107">EditSchema</span></span>
- <span data-ttu-id="f5719-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="f5719-108">RemoveSchema</span></span>
- <span data-ttu-id="f5719-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="f5719-109">UploadDataFailed</span></span>
- <span data-ttu-id="f5719-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="f5719-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="f5719-111">A capacidade de criar notificações para atividades de EDM está disponível apenas para as nuvens de World Wide e de GCC.</span><span class="sxs-lookup"><span data-stu-id="f5719-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f5719-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f5719-112">Pre-requisites</span></span>

<span data-ttu-id="f5719-113">Você deve usar uma das seguintes contas:</span><span class="sxs-lookup"><span data-stu-id="f5719-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="f5719-114">um administrador global</span><span class="sxs-lookup"><span data-stu-id="f5719-114">a global admin</span></span>
- <span data-ttu-id="f5719-115">administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="f5719-115">compliance administrator</span></span>
- <span data-ttu-id="f5719-116">Administrador do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f5719-116">Exchange Online administrator</span></span>

<span data-ttu-id="f5719-117">Para saber mais sobre permissões DLP, confira [Permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="f5719-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="f5719-118">A classificação baseada em EDM está incluída nestas assinaturas</span><span class="sxs-lookup"><span data-stu-id="f5719-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="f5719-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f5719-119">Office 365 E5</span></span>
- <span data-ttu-id="f5719-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f5719-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="f5719-121">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f5719-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="f5719-122">Proteção e governança de informações do Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="f5719-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="f5719-123">Para saber mais sobre o licenciamento DLP, confira [Diretrizes de licenciamento do Microsoft 365 de conformidade e segurança](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="f5719-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="f5719-124">Configurar notificações para atividades de EDM</span><span class="sxs-lookup"><span data-stu-id="f5719-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="f5719-125">Conectar-se ao PowerShell do [Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="f5719-125">Connect to the [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="f5719-126">Execute o cmdlet `New-ProtectionAlert` usando a atividade para a qual você deseja criar a notificação.</span><span class="sxs-lookup"><span data-stu-id="f5719-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="f5719-127">Por exemplo, execute se você quiser ser notificado quando a ação **UploadDataCompleted** ocorrer,</span><span class="sxs-lookup"><span data-stu-id="f5719-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="f5719-128">você pode executar para o **UploadDataFailed**</span><span class="sxs-lookup"><span data-stu-id="f5719-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="f5719-129">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="f5719-129">Related articles</span></span>

- [<span data-ttu-id="f5719-130">Criar tipos de informações confidenciais personalizadas com combinação exata de dados (EDM)</span><span class="sxs-lookup"><span data-stu-id="f5719-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="f5719-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="f5719-131">New-ProtectionAlert</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) 