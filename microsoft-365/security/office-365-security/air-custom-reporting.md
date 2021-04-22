---
title: Soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, investigação automatizada, integração, relatório personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba como integrar a investigação e a resposta automatizadas a uma solução de relatórios personalizada ou de terceiros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a7ccc0f07691c5183b9cb7a6e5b3f512f35f76b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935396"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="2ee02-104">Soluções de relatórios personalizadas ou de terceiros para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2ee02-105">Com [o Microsoft Defender para Office 365,](defender-for-office-365.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="2ee02-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="2ee02-106">No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2ee02-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="2ee02-107">Se sua organização quiser integrar informações sobre [investigações automatizadas](office-365-air.md) com essa solução, você pode usar a API de Atividade de Gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ee02-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="2ee02-108">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="2ee02-108">**Applies to**</span></span>
- [<span data-ttu-id="2ee02-109">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2ee02-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ee02-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2ee02-111">Com [o Microsoft Defender para Office 365,](defender-for-office-365.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="2ee02-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="2ee02-112">No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2ee02-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="2ee02-113">Se sua organização quiser integrar informações sobre investigações automatizadas com essa solução, você pode usar a API de Atividade de Gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ee02-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="2ee02-114">Recurso</span><span class="sxs-lookup"><span data-stu-id="2ee02-114">Resource</span></span>|<span data-ttu-id="2ee02-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ee02-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="2ee02-116">Visão geral das APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="2ee02-117">A API de Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuários, administradores, sistemas e políticas do Microsoft 365 e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ee02-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="2ee02-118">Introdução às APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="2ee02-119">A API de Gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para seu aplicativo acessar dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ee02-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="2ee02-120">Siga as etapas deste artigo para configurar isso.</span><span class="sxs-lookup"><span data-stu-id="2ee02-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="2ee02-121">Referência da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="2ee02-122">Você pode usar a API de Atividade de Gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuário, administrador, sistema e política dos logs de atividades do Microsoft 365 e do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2ee02-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="2ee02-123">Leia este artigo para saber mais sobre como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="2ee02-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="2ee02-124">Esquema da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="2ee02-125">Obter uma visão [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) geral do esquema Comum e do [Defender for Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e do esquema de investigação e resposta contra ameaças para saber mais sobre tipos específicos de dados disponíveis por meio da API de Atividade de Gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ee02-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="2ee02-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ee02-126">See also</span></span>

- [<span data-ttu-id="2ee02-127">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2ee02-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2ee02-128">Investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ee02-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
