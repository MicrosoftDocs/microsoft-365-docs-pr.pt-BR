---
title: Integração do SIEM com o Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com o Microsoft defender para Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 93ff1606130c60ceb46087d28bb26f9a6d27d330
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615655"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="f7e49-103">Integração do SIEM com o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f7e49-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f7e49-104">Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM), você poderá integrar o Microsoft defender para Office 365 com seu servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="f7e49-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="f7e49-105">Você pode configurar essa integração usando a API de [Gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="f7e49-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="f7e49-106">A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pelo Microsoft defender para Office 365, em seus relatórios do SIEM Server.</span><span class="sxs-lookup"><span data-stu-id="f7e49-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="f7e49-107">Para ver um exemplo de integração do SIEM com o Microsoft defender para Office 365, consulte [blog da comunidade técnica: aprimore a eficácia do seu SoC com o defender para Office 365 e a API de gerenciamento do O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="f7e49-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="f7e49-108">Para saber mais sobre as APIs de gerenciamento do Office 365, confira [visão geral das APIs de gerenciamento do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="f7e49-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="f7e49-109">Como funciona a integração do SIEM</span><span class="sxs-lookup"><span data-stu-id="f7e49-109">How SIEM integration works</span></span>

<span data-ttu-id="f7e49-110">A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7e49-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="f7e49-111">Se sua organização tiver o Microsoft defender para Office 365 plano 1 ou 2 ou o Office 365 e5, você poderá usar o [esquema do Microsoft defender para office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="f7e49-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="f7e49-112">Recentemente, eventos de investigação automatizada e recursos de resposta no [Microsoft defender para Office 365 plano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) foram adicionados à API da atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7e49-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="f7e49-113">Além de incluir dados sobre detalhes principais de investigação, como ID, nome e status, a API também contém informações de alto nível sobre ações de investigação e entidades.</span><span class="sxs-lookup"><span data-stu-id="f7e49-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="f7e49-114">O servidor SIEM ou outro sistema semelhante pesquisa a **auditoria.** a carga de trabalho geral para acessar eventos de detecção.</span><span class="sxs-lookup"><span data-stu-id="f7e49-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="f7e49-115">Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="f7e49-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="f7e49-116">Enumeração: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="f7e49-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="f7e49-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="f7e49-117">AuditLogRecordType</span></span>

<span data-ttu-id="f7e49-118">A tabela a seguir resume os valores de **AuditLogRecordType** que são relevantes para eventos do Microsoft defender for Office 365:</span><span class="sxs-lookup"><span data-stu-id="f7e49-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="f7e49-119">Valor</span><span class="sxs-lookup"><span data-stu-id="f7e49-119">Value</span></span>|<span data-ttu-id="f7e49-120">Nome do membro</span><span class="sxs-lookup"><span data-stu-id="f7e49-120">Member name</span></span>|<span data-ttu-id="f7e49-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7e49-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="f7e49-122">28</span><span class="sxs-lookup"><span data-stu-id="f7e49-122">28</span></span>|<span data-ttu-id="f7e49-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="f7e49-123">ThreatIntelligence</span></span>|<span data-ttu-id="f7e49-124">Eventos de phishing e malware da proteção do Exchange Online e do Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7e49-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="f7e49-125">41</span><span class="sxs-lookup"><span data-stu-id="f7e49-125">41</span></span>|<span data-ttu-id="f7e49-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="f7e49-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="f7e49-127">Links seguros de tempo de bloqueio e substituição de eventos do Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7e49-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="f7e49-128">47</span><span class="sxs-lookup"><span data-stu-id="f7e49-128">47</span></span>|<span data-ttu-id="f7e49-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="f7e49-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="f7e49-130">Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7e49-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="f7e49-131">64</span><span class="sxs-lookup"><span data-stu-id="f7e49-131">64</span></span>|<span data-ttu-id="f7e49-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="f7e49-132">AirInvestigation</span></span>|<span data-ttu-id="f7e49-133">Eventos de investigação e resposta automatizados, como detalhes de investigação e artefatos relevantes, do Microsoft defender para Office 365 plano 2.</span><span class="sxs-lookup"><span data-stu-id="f7e49-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="f7e49-134">Você deve ser um administrador global ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com o Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7e49-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="f7e49-135">O log de auditoria deve estar ativado para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7e49-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="f7e49-136">Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="f7e49-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7e49-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="f7e49-137">See also</span></span>

[<span data-ttu-id="f7e49-138">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="f7e49-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="f7e49-139">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="f7e49-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

