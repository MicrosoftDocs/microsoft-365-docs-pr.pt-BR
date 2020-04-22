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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com a proteção avançada contra ameaças do Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.openlocfilehash: 770e2348c4e5729531118fb4a014a72c352a0dd1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638291"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="e78de-103">Integração do SIEM com proteção avançada contra ameaças</span><span class="sxs-lookup"><span data-stu-id="e78de-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="e78de-104">Se sua organização estiver usando um servidor de gerenciamento de incidentes e eventos de segurança (SIEM), você poderá integrar a proteção avançada contra ameaças do Office 365 ao seu servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="e78de-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="e78de-105">A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pela proteção avançada do Office 365, em seus relatórios do SIEM Server.</span><span class="sxs-lookup"><span data-stu-id="e78de-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="e78de-106">Para configurar a integração do SIEM, use a [API de gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="e78de-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="e78de-107">A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 para empresas e do Azure Active Directory da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e78de-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="e78de-108">O [esquema de proteção avançada contra ameaças do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funciona com a proteção avançada contra ameaças, portanto, se sua organização tiver o plano de proteção avançada contra ameaças do Office 365 ou o plano 2 ou o Office 365 e5, você ainda poderá usar essa mesma API para sua integração com o Siem Server.</span><span class="sxs-lookup"><span data-stu-id="e78de-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="e78de-109">Como parte de nossas atualizações recentes, também adicionamos eventos de investigação automatizada e recursos de resposta no Office 365 ATP plano 2 dentro da API de atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="e78de-110">Além de incluir dados sobre detalhes principais de investigação, como ID, nome e status, ele também contém informações de alto nível sobre ações de investigação e entidades.</span><span class="sxs-lookup"><span data-stu-id="e78de-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="e78de-111">O servidor SIEM ou outro sistema semelhante deve sondar a **auditoria.** carga de trabalho geral para acessar eventos de detecção.</span><span class="sxs-lookup"><span data-stu-id="e78de-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="e78de-112">Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="e78de-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="e78de-113">Além disso, os seguintes valores de **AuditLogRecordType** são relevantes para eventos de ATP do Office 365:</span><span class="sxs-lookup"><span data-stu-id="e78de-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="e78de-114">Enumeração: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="e78de-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="e78de-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="e78de-115">AuditLogRecordType</span></span>

|<span data-ttu-id="e78de-116">Valor</span><span class="sxs-lookup"><span data-stu-id="e78de-116">Value</span></span>|<span data-ttu-id="e78de-117">Nome do membro</span><span class="sxs-lookup"><span data-stu-id="e78de-117">Member name</span></span>|<span data-ttu-id="e78de-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="e78de-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e78de-119">28</span><span class="sxs-lookup"><span data-stu-id="e78de-119">28</span></span>|<span data-ttu-id="e78de-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="e78de-120">ThreatIntelligence</span></span>|<span data-ttu-id="e78de-121">Eventos de phishing e malware da Proteção do Exchange Online e da Proteção Avançada contra Ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="e78de-122">41</span><span class="sxs-lookup"><span data-stu-id="e78de-122">41</span></span>|<span data-ttu-id="e78de-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="e78de-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="e78de-124">Links seguros de ATP os eventos de tempo de bloqueio e substituição de bloqueio da proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="e78de-125">47</span><span class="sxs-lookup"><span data-stu-id="e78de-125">47</span></span>|<span data-ttu-id="e78de-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="e78de-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="e78de-127">Eventos de phishing e malware para arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams da proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="e78de-128">64</span><span class="sxs-lookup"><span data-stu-id="e78de-128">64</span></span>|<span data-ttu-id="e78de-129">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="e78de-129">AirInvestigation</span></span>|<span data-ttu-id="e78de-130">Eventos de investigação e resposta automatizados, como detalhes de investigação e artefatos relevantes do plano de proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="e78de-131">Você deve ser um administrador global ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com a proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="e78de-132">O log de auditoria deve estar ativado para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e78de-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="e78de-133">Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="e78de-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e78de-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e78de-134">Related topics</span></span>

[<span data-ttu-id="e78de-135">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="e78de-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="e78de-136">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="e78de-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="e78de-137">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="e78de-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="e78de-138">Relatórios inteligentes e insights no centro de &amp; conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="e78de-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="e78de-139">Permissões no centro de &amp; conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="e78de-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
