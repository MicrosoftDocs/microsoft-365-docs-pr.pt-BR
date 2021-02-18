---
title: Integração siEM com o Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com o Microsoft Defender para Office 365 e eventos de ameaças relacionados na API de Gerenciamento de Atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290388"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="9703c-103">Integração siEM com o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9703c-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9703c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9703c-104">**Applies to**</span></span>
- [<span data-ttu-id="9703c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9703c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9703c-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9703c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9703c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9703c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9703c-108">Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM), você poderá integrar o Microsoft Defender para Office 365 ao seu servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="9703c-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="9703c-109">Você pode configurar essa integração usando a API de Gerenciamento de Atividades do [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="9703c-109">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="9703c-110">A integração SIEM permite exibir informações, como malware ou phishing detectados pelo Microsoft Defender para Office 365, nos relatórios do servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="9703c-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="9703c-111">Para ver um exemplo de integração do SIEM com o Microsoft Defender para Office 365, confira o blog da Tech Community: Melhore a eficácia do seu SOC com o Defender para Office 365 e a API de Gerenciamento do [O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="9703c-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="9703c-112">Para saber mais sobre as APIs de Gerenciamento do Office 365, confira a visão geral das APIs de Gerenciamento do [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="9703c-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="9703c-113">Como funciona a integração SIEM</span><span class="sxs-lookup"><span data-stu-id="9703c-113">How SIEM integration works</span></span>

<span data-ttu-id="9703c-114">A API de Gerenciamento de Atividades do Office 365 recupera informações sobre ações e eventos de usuários, administradores, sistemas e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9703c-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="9703c-115">Se sua organização tiver o Microsoft Defender para Office 365 Plano 1 ou 2 ou o Office 365 E5, você poderá usar o esquema do [Microsoft Defender para Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="9703c-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="9703c-116">Recentemente, os eventos dos recursos automatizados de investigação e resposta no [Microsoft Defender para Office 365 Plano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) foram adicionados à API da Atividade de Gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9703c-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="9703c-117">Além de incluir dados sobre detalhes da investigação básica, como ID, nome e status, a API também contém informações de alto nível sobre ações e entidades de investigação.</span><span class="sxs-lookup"><span data-stu-id="9703c-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="9703c-118">O servidor SIEM ou outro sistema semelhante pesquisa a carga de trabalho **audit.general** para acessar eventos de detecção.</span><span class="sxs-lookup"><span data-stu-id="9703c-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="9703c-119">Para saber mais, confira Começar a trabalhar com APIs de Gerenciamento [do Office 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="9703c-119">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="9703c-120">Enumeração: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="9703c-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="9703c-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="9703c-121">AuditLogRecordType</span></span>

<span data-ttu-id="9703c-122">A tabela a seguir resume os valores **de AuditLogRecordType** que são relevantes para eventos do Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="9703c-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="9703c-123">Valor</span><span class="sxs-lookup"><span data-stu-id="9703c-123">Value</span></span>|<span data-ttu-id="9703c-124">Nome do membro</span><span class="sxs-lookup"><span data-stu-id="9703c-124">Member name</span></span>|<span data-ttu-id="9703c-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="9703c-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="9703c-126">28</span><span class="sxs-lookup"><span data-stu-id="9703c-126">28</span></span>|<span data-ttu-id="9703c-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="9703c-127">ThreatIntelligence</span></span>|<span data-ttu-id="9703c-128">Eventos de phishing e malware da Proteção do Exchange Online e do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="9703c-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="9703c-129">41</span><span class="sxs-lookup"><span data-stu-id="9703c-129">41</span></span>|<span data-ttu-id="9703c-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="9703c-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="9703c-131">Eventos de tempo de bloqueio e bloqueio de Links seguros do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="9703c-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="9703c-132">47</span><span class="sxs-lookup"><span data-stu-id="9703c-132">47</span></span>|<span data-ttu-id="9703c-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="9703c-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="9703c-134">Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="9703c-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="9703c-135">64</span><span class="sxs-lookup"><span data-stu-id="9703c-135">64</span></span>|<span data-ttu-id="9703c-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="9703c-136">AirInvestigation</span></span>|<span data-ttu-id="9703c-137">Eventos automatizados de investigação e resposta, como detalhes de investigação e artefatos relevantes, do Microsoft Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="9703c-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="9703c-138">Você deve ser um administrador global ou ter a função de administrador de segurança atribuída ao Centro de Conformidade e Segurança & para configurar a integração SIEM com o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="9703c-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="9703c-139">O log de auditoria deve estar ligado para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9703c-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="9703c-140">Para obter ajuda com isso, consulte Ativar ou desativar a pesquisa [de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="9703c-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9703c-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="9703c-141">See also</span></span>

[<span data-ttu-id="9703c-142">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="9703c-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="9703c-143">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="9703c-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

