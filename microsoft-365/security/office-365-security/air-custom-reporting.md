---
title: Soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigação automatizada, integração, relatório personalizado
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
description: Saiba como integrar investigação e resposta automatizadas com uma solução de relatórios personalizada ou de terceiros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142964"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="10b6f-104">Soluções de relatórios personalizadas ou de terceiros para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="10b6f-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="10b6f-105">Com [o Microsoft Defender para Office 365,](office-365-atp.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="10b6f-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="10b6f-106">No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="10b6f-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="10b6f-107">Se sua organização deseja integrar informações sobre [investigações automatizadas](office-365-air.md) com essa solução, você pode usar a API da Atividade de Gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="10b6f-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="10b6f-108">Recursos para configurar a integração</span><span class="sxs-lookup"><span data-stu-id="10b6f-108">Resources to configure integration</span></span>

|<span data-ttu-id="10b6f-109">Recurso</span><span class="sxs-lookup"><span data-stu-id="10b6f-109">Resource</span></span>|<span data-ttu-id="10b6f-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="10b6f-110">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="10b6f-111">Visão geral das APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="10b6f-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="10b6f-112">A API da Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuários, administradores, sistemas e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10b6f-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="10b6f-113">Introdução às APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="10b6f-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="10b6f-114">A API de Gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para que seu aplicativo acesse os dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10b6f-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="10b6f-115">Siga as etapas neste artigo para configurar isso.</span><span class="sxs-lookup"><span data-stu-id="10b6f-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="10b6f-116">Referência da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="10b6f-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="10b6f-117">Você pode usar a API da Atividade de Gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuários, administradores, sistemas e políticas dos logs de atividades do Microsoft 365 e do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10b6f-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="10b6f-118">Leia este artigo para saber mais sobre como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="10b6f-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="10b6f-119">Esquema da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="10b6f-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="10b6f-120">Obter uma visão [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) geral do esquema Comum e do [Defender para Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e esquema de investigação e resposta de ameaças para saber mais sobre tipos específicos de dados disponíveis por meio da API da Atividade de Gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="10b6f-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="10b6f-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="10b6f-121">See also</span></span>

- [<span data-ttu-id="10b6f-122">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="10b6f-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="10b6f-123">Investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10b6f-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
