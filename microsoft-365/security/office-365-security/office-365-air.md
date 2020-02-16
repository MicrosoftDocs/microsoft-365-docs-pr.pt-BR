---
title: Investigar e responder automaticamente a ameças no Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
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
description: Comece a usar os recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d45141ce671a4615cb4fd550e36bc7215cd38d51
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088310"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="20328-104">Investigar e responder automaticamente a ameças no Office 365</span><span class="sxs-lookup"><span data-stu-id="20328-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="20328-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="20328-105">Overview</span></span>

<span data-ttu-id="20328-106">Dependendo da sua assinatura, a [proteção avançada contra ameaças do Office 365](office-365-atp.md) pode incluir recursos de investigação e resposta automatizados que podem economizar tempo e esforço da equipe de operações de segurança em lidar com alertas e ameaças.</span><span class="sxs-lookup"><span data-stu-id="20328-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="20328-107">Para começar a usar os recursos de investigação e resposta automatizados no Office 365, use este artigo.</span><span class="sxs-lookup"><span data-stu-id="20328-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="20328-108">Para obter uma visão geral de como ele funciona, consulte [investigação e resposta automatizadas no Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="20328-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="20328-109">Você tem o Microsoft 365 E5 ou Microsoft 365 E3 juntamente com Proteção contra Identidade e Ameaças?</span><span class="sxs-lookup"><span data-stu-id="20328-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="20328-110">Considere a possibilidade de experimentar a [investigação e a resposta automatizadas (Air) na proteção contra ameaças da Microsoft](../mtp/mtp-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="20328-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="20328-111">Com recursos de investigação e resposta automatizados, quando determinados alertas são acionados, um ou mais guias de segurança são iniciados e o processo de investigação automatizado é iniciado.</span><span class="sxs-lookup"><span data-stu-id="20328-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="20328-112">Durante e após um processo de investigação automatizado, a equipe de segurança pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="20328-112">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="20328-113">Exibir os detalhes de uma investigação</span><span class="sxs-lookup"><span data-stu-id="20328-113">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="20328-114">Revisar e aprovar ações como resultado de uma investigação</span><span class="sxs-lookup"><span data-stu-id="20328-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="20328-115">Exibir detalhes sobre um alerta relacionado a uma investigação</span><span class="sxs-lookup"><span data-stu-id="20328-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="20328-116">Para executar as tarefas descritas neste artigo, você deve ter as permissões apropriadas atribuídas.</span><span class="sxs-lookup"><span data-stu-id="20328-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="20328-117">Confira [as permissões necessárias para usar os recursos de ar](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="20328-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="20328-118">Exibir detalhes de uma investigação</span><span class="sxs-lookup"><span data-stu-id="20328-118">View details of an investigation</span></span>

1. <span data-ttu-id="20328-119">Vá para [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="20328-119">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="20328-120">Isso leva você para o centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="20328-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="20328-121">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="20328-121">Do one of the following:</span></span>

    - <span data-ttu-id="20328-122">Vá para o**painel**de **Gerenciamento** > de ameaças.</span><span class="sxs-lookup"><span data-stu-id="20328-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="20328-123">Isso leva você para o [painel de segurança](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="20328-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="20328-124">Os widgets do AIR aparecem na parte superior do [painel de segurança](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="20328-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="20328-125">Selecione um widget, como o **Resumo de investigações**.</span><span class="sxs-lookup"><span data-stu-id="20328-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="20328-126">Vá para \*\*\*\* > **investigações**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="20328-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="20328-127">Qualquer um dos métodos o leva a uma lista de investigações.</span><span class="sxs-lookup"><span data-stu-id="20328-127">Either method takes you to a list of investigations.</span></span>

    ![Página de investigação principal para AIR](../../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="20328-129">Na lista de investigações, selecione um item na coluna **ID** .</span><span class="sxs-lookup"><span data-stu-id="20328-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="20328-130">Isso abre a página detalhes da investigação, começando com o gráfico de investigação no modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="20328-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Página de gráfico de investigação aérea](../../media/air-investigationgraphpage.png)

4. <span data-ttu-id="20328-132">Use as várias guias para saber mais sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="20328-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="20328-133">Revisar e aprovar ações</span><span class="sxs-lookup"><span data-stu-id="20328-133">Review and approve actions</span></span>

<span data-ttu-id="20328-134">No Office 365, as investigações automatizadas normalmente resultam em uma ou mais ações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="20328-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="20328-135">No entanto, nenhuma ação será executada até que sejam aprovadas pela equipe de operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="20328-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="20328-136">Use o procedimento a seguir para revisar e aprovar ações.</span><span class="sxs-lookup"><span data-stu-id="20328-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="20328-137">Vá para [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="20328-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="20328-138">Vá para \*\*\*\* > **investigações**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="20328-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="20328-139">Na lista de investigações, selecione um item na coluna **ID** .</span><span class="sxs-lookup"><span data-stu-id="20328-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="20328-140">No modo de exibição detalhes da investigação, selecione a guia **ações** . Todas as ações que estão com aprovação pendente são listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="20328-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="20328-141">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="20328-141">Select an item in the list.</span></span>

5. <span data-ttu-id="20328-142">Selecione **aprovar** para executar a ação recomendada (ou **rejeitar** para fechar a investigação sem executar a ação).</span><span class="sxs-lookup"><span data-stu-id="20328-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="20328-143">Exibir detalhes sobre um alerta relacionado a uma investigação</span><span class="sxs-lookup"><span data-stu-id="20328-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="20328-144">Determinados tipos de alertas disparam investigação automatizada no Office 365.</span><span class="sxs-lookup"><span data-stu-id="20328-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="20328-145">Para saber mais, confira [alertas](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="20328-145">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="20328-146">Use o procedimento a seguir para exibir detalhes sobre um alerta que está associado a uma investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="20328-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="20328-147">Vá para [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="20328-147">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="20328-148">Isso leva você para o centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="20328-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="20328-149">Vá para \*\*\*\* > **investigações**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="20328-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="20328-150">Na lista de investigações, selecione um item na coluna **ID** .</span><span class="sxs-lookup"><span data-stu-id="20328-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="20328-151">Com detalhes de uma investigação aberta, selecione a guia **alertas** . Todos os alertas que dispararam a investigação estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="20328-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="20328-152">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="20328-152">Select an item in the list.</span></span> <span data-ttu-id="20328-153">Um submenu abre, com detalhes sobre o alerta e links para informações adicionais e ações.</span><span class="sxs-lookup"><span data-stu-id="20328-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="20328-154">Revise as informações no submenu e, dependendo do alerta específico, execute uma ação, como **resolver**, **suprimir**ou **notificar os usuários**.</span><span class="sxs-lookup"><span data-stu-id="20328-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="20328-155">**Resolver** é equivalente a fechar um alerta</span><span class="sxs-lookup"><span data-stu-id="20328-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="20328-156">**Supressão** faz com que uma política não acione alertas por um período de tempo especificado</span><span class="sxs-lookup"><span data-stu-id="20328-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="20328-157">**Notificar os usuários sobre** o início de um email com os endereços de email dos usuários já inseridos e permite que sua equipe de operações de segurança digite uma mensagem para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="20328-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="20328-158">(Isso é semelhante ao envio de uma mensagem para destinatários usando o [Explorador de ameaças](threat-explorer.md).)</span><span class="sxs-lookup"><span data-stu-id="20328-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="20328-159">Usar a API de atividade de gerenciamento do Office 365 para soluções de relatórios personalizados ou de terceiros</span><span class="sxs-lookup"><span data-stu-id="20328-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="20328-160">Se sua organização estiver usando uma solução de relatórios personalizada ou de terceiros, você poderá exibir informações sobre investigações automatizadas nessa solução usando a API da atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="20328-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="20328-161">Use os seguintes recursos para configurar isso:</span><span class="sxs-lookup"><span data-stu-id="20328-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="20328-162">Resource</span><span class="sxs-lookup"><span data-stu-id="20328-162">Resource</span></span>  |<span data-ttu-id="20328-163">Descrição</span><span class="sxs-lookup"><span data-stu-id="20328-163">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="20328-164">Visão geral das APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="20328-164">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="20328-165">A API da Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="20328-165">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="20328-166">Introdução às APIs de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="20328-166">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="20328-167">A API de gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para que seu aplicativo acesse os dados do Office 365.</span><span class="sxs-lookup"><span data-stu-id="20328-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="20328-168">Siga as etapas deste artigo para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="20328-168">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="20328-169">Referência da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="20328-169">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="20328-170">Você pode usar a API de atividade de gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="20328-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="20328-171">Leia este artigo para saber mais sobre como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="20328-171">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="20328-172">Esquema da API da Atividade de Gerenciamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="20328-172">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="20328-173">Obtenha uma visão geral do [esquema comum](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e do [Office 365 ATP e o esquema de resposta](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para conhecer os tipos específicos de dados disponíveis por meio da API de atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="20328-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="20328-174">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="20328-174">Next steps</span></span>

- [<span data-ttu-id="20328-175">Descubra como obter o AIR e ver as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="20328-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="20328-176">Saiba mais sobre os alertas</span><span class="sxs-lookup"><span data-stu-id="20328-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="20328-177">Encontre e investigue manualmente emails mal-intencionados que foram entregues no Office 365</span><span class="sxs-lookup"><span data-stu-id="20328-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="20328-178">Saiba mais sobre o AIR no Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="20328-178">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="20328-179">Visite o mapa do Microsoft 365 para ver o que está chegando em breve e distribuir</span><span class="sxs-lookup"><span data-stu-id="20328-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
