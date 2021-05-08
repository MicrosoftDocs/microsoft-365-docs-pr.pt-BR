---
title: Soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, investigação automatizada, integração, relatório personalizado
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275007"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="58f75-104">Soluções de relatórios personalizadas ou de terceiros para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="58f75-105">Com [o Microsoft Defender para Office 365](defender-for-office-365.md), você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="58f75-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="58f75-106">No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="58f75-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="58f75-107">Se a sua organização quiser integrar informações sobre [investigações automatizadas](office-365-air.md) com essa solução, você pode usar a API Office 365 Atividade de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="58f75-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="58f75-108">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="58f75-108">**Applies to**</span></span>
- [<span data-ttu-id="58f75-109">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="58f75-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58f75-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="58f75-111">Com [o Microsoft Defender para Office 365](defender-for-office-365.md), você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="58f75-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="58f75-112">No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="58f75-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="58f75-113">Se a sua organização quiser integrar informações sobre investigações automatizadas com essa solução, você pode usar a API Office 365 Atividade de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="58f75-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="58f75-114">Recurso</span><span class="sxs-lookup"><span data-stu-id="58f75-114">Resource</span></span>|<span data-ttu-id="58f75-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="58f75-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="58f75-116">Visão geral das APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="58f75-117">A API Office 365 de Atividade de Gerenciamento fornece informações sobre várias ações e eventos de usuários, administradores, sistemas e políticas de Microsoft 365 e Azure Active Directory de atividades.</span><span class="sxs-lookup"><span data-stu-id="58f75-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="58f75-118">Introdução às APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="58f75-119">A OFFICE 365 de Gerenciamento usa o Azure AD para fornecer serviços de autenticação para seu aplicativo acessar Microsoft 365 dados.</span><span class="sxs-lookup"><span data-stu-id="58f75-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="58f75-120">Siga as etapas deste artigo para configurar isso.</span><span class="sxs-lookup"><span data-stu-id="58f75-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="58f75-121">Referência da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="58f75-122">Você pode usar Office 365 API de Atividade de Gerenciamento para recuperar informações sobre ações e eventos de usuários, administradores, sistemas e políticas de logs de atividades do Microsoft 365 e do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="58f75-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="58f75-123">Leia este artigo para saber mais sobre como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="58f75-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="58f75-124">Esquema da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="58f75-125">Obter uma visão [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) geral do esquema Comum e do Defender para Office 365 e investigação de ameaças e [esquema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) de resposta para saber mais sobre tipos específicos de dados disponíveis por meio da API de Atividade de Gerenciamento Office 365.</span><span class="sxs-lookup"><span data-stu-id="58f75-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="58f75-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="58f75-126">See also</span></span>

- [<span data-ttu-id="58f75-127">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="58f75-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="58f75-128">Investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58f75-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
