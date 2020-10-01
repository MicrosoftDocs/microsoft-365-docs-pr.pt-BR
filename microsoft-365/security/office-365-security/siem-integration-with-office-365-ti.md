---
title: Integração do SIEM com proteção avançada contra ameaças
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
description: Integre o servidor SIEM da sua organização com a proteção avançada contra ameaças do Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327160"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="26587-103">Integração do SIEM com proteção avançada contra ameaças</span><span class="sxs-lookup"><span data-stu-id="26587-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="26587-104">Se sua organização estiver usando um servidor de gerenciamento de incidentes e eventos de segurança (SIEM), você poderá integrar a proteção avançada contra ameaças do Office 365 (Office 365 ATP) com seu servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="26587-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="26587-105">Você pode configurar essa integração usando a API de [Gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="26587-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="26587-106">A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pelo Office 365 ATP, em seus relatórios do SIEM Server.</span><span class="sxs-lookup"><span data-stu-id="26587-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="26587-107">Para ver um exemplo de integração do SIEM com o Office 365 ATP, consulte [blog da comunidade técnica: aprimore a eficácia do seu SoC com o Office 365 ATP e a API de gerenciamento do O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="26587-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="26587-108">Para saber mais sobre as APIs de gerenciamento do Office 365, confira [visão geral das APIs de gerenciamento do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="26587-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="26587-109">Como funciona a integração do SIEM</span><span class="sxs-lookup"><span data-stu-id="26587-109">How SIEM integration works</span></span>

<span data-ttu-id="26587-110">A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory da sua organização.</span><span class="sxs-lookup"><span data-stu-id="26587-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="26587-111">Se sua organização tiver o plano de ATP 1 ou 2 do Office 365 ou o Office 365 e5, você poderá usar o [esquema ATP do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="26587-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="26587-112">Recentemente, eventos de investigação automatizada e recursos de resposta no [office 365 ATP plano 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) foram adicionados à API da atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="26587-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="26587-113">Além de incluir dados sobre detalhes principais de investigação, como ID, nome e status, a API também contém informações de alto nível sobre ações de investigação e entidades.</span><span class="sxs-lookup"><span data-stu-id="26587-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="26587-114">O servidor SIEM ou outro sistema semelhante pesquisa a **auditoria.** a carga de trabalho geral para acessar eventos de detecção.</span><span class="sxs-lookup"><span data-stu-id="26587-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="26587-115">Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="26587-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="26587-116">Enumeração: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="26587-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="26587-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="26587-117">AuditLogRecordType</span></span>

<span data-ttu-id="26587-118">A tabela a seguir resume os valores de **AuditLogRecordType** que são relevantes para eventos de ATP do Office 365:</span><span class="sxs-lookup"><span data-stu-id="26587-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="26587-119">Valor</span><span class="sxs-lookup"><span data-stu-id="26587-119">Value</span></span>|<span data-ttu-id="26587-120">Nome do membro</span><span class="sxs-lookup"><span data-stu-id="26587-120">Member name</span></span>|<span data-ttu-id="26587-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="26587-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="26587-122">28</span><span class="sxs-lookup"><span data-stu-id="26587-122">28</span></span>|<span data-ttu-id="26587-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="26587-123">ThreatIntelligence</span></span>|<span data-ttu-id="26587-124">Eventos de phishing e malware de proteção do Exchange Online e do Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="26587-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="26587-125">41</span><span class="sxs-lookup"><span data-stu-id="26587-125">41</span></span>|<span data-ttu-id="26587-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="26587-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="26587-127">Links seguros de tempo de bloqueio e substituição de bloqueio de eventos do Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="26587-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="26587-128">47</span><span class="sxs-lookup"><span data-stu-id="26587-128">47</span></span>|<span data-ttu-id="26587-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="26587-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="26587-130">Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="26587-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="26587-131">64</span><span class="sxs-lookup"><span data-stu-id="26587-131">64</span></span>|<span data-ttu-id="26587-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="26587-132">AirInvestigation</span></span>|<span data-ttu-id="26587-133">Eventos de investigação e resposta automatizados, como detalhes de investigação e artefatos relevantes, do plano de ATP 2 do Office 365.</span><span class="sxs-lookup"><span data-stu-id="26587-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="26587-134">Você deve ser um administrador global ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com a proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="26587-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="26587-135">O log de auditoria deve estar ativado para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26587-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="26587-136">Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="26587-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26587-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="26587-137">See also</span></span>

[<span data-ttu-id="26587-138">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="26587-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="26587-139">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="26587-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


