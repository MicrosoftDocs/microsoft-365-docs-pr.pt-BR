---
title: Usando soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigação automatizada, integração, relatório personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Saiba como integrar a investigação e a resposta automatizadas com uma solução de relatório personalizada ou de terceiros.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 08502516ae03dc7c6e7b58aa77939723e7532ef0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308915"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="e5bbb-104">Usar a API de atividade de gerenciamento para soluções de relatórios personalizadas ou de terceiros</span><span class="sxs-lookup"><span data-stu-id="e5bbb-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e5bbb-105">Com [o Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), você obtém [informações detalhadas sobre investigações automatizadas](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="e5bbb-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="e5bbb-106">No entanto, algumas organizações também usam uma solução de relatório personalizada ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="e5bbb-107">Se sua organização quiser integrar as informações sobre investigações automatizadas a essa solução, você poderá usar a API da atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="e5bbb-108">Use os seguintes recursos para configurar isso:</span><span class="sxs-lookup"><span data-stu-id="e5bbb-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="e5bbb-109">Recurso</span><span class="sxs-lookup"><span data-stu-id="e5bbb-109">Resource</span></span>|<span data-ttu-id="e5bbb-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5bbb-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="e5bbb-111">Visão geral das APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="e5bbb-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="e5bbb-112">A API de atividade de gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="e5bbb-113">Introdução às APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="e5bbb-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="e5bbb-114">A API de gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para que seu aplicativo acesse os dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="e5bbb-115">Siga as etapas deste artigo para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="e5bbb-116">Referência da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="e5bbb-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="e5bbb-117">Você pode usar a API de atividade de gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 e do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="e5bbb-118">Leia este artigo para saber mais sobre como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="e5bbb-119">Esquema da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="e5bbb-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="e5bbb-120">Obtenha uma visão geral do [esquema comum](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e do [Office 365 ATP e o esquema de resposta](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para conhecer os tipos específicos de dados disponíveis por meio da API de atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5bbb-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="e5bbb-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="e5bbb-121">See also</span></span>

- [<span data-ttu-id="e5bbb-122">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e5bbb-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="e5bbb-123">Investigação e resposta automatizadas no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e5bbb-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
