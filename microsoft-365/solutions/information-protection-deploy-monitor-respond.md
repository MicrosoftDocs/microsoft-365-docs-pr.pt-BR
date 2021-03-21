---
title: Monitorar e responder a incidentes de privacidade de dados em sua organização
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use políticas de auditoria e alerta e solicitações de assunto de dados para monitorar e responder a incidentes de dados pessoais.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928419"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="4fdf8-103">Monitorar e responder a incidentes de privacidade de dados em sua organização</span><span class="sxs-lookup"><span data-stu-id="4fdf8-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="4fdf8-104">Os recursos do Microsoft 365 estão disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você operacionaliza os recursos relacionados.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="4fdf8-105">Ter processos, procedimentos e outras documentações para cada um deles também pode ser importante para demonstrar a conformidade com os órgãos regulatórios.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="4fdf8-106">Entre eles:</span><span class="sxs-lookup"><span data-stu-id="4fdf8-106">These include:</span></span> 

- <span data-ttu-id="4fdf8-107">Auditoria e políticas de alerta</span><span class="sxs-lookup"><span data-stu-id="4fdf8-107">Auditing and alert policies</span></span>
- <span data-ttu-id="4fdf8-108">Solicitações de assunto de dados (incluindo pesquisa de conteúdo e Descoberta Desdiscovery)</span><span class="sxs-lookup"><span data-stu-id="4fdf8-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="4fdf8-109">Ferramentas de investigação e relatórios adicionais</span><span class="sxs-lookup"><span data-stu-id="4fdf8-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="4fdf8-110">Regulamentos de privacidade de dados que impactam o uso de ferramentas de monitoramento e resposta</span><span class="sxs-lookup"><span data-stu-id="4fdf8-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="4fdf8-111">Aqui está um exemplo de listagem de regulamentos de privacidade de dados que podem estar relacionados aos controles de governança de informações:</span><span class="sxs-lookup"><span data-stu-id="4fdf8-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="4fdf8-112">Artigo 46 do LGPD</span><span class="sxs-lookup"><span data-stu-id="4fdf8-112">LGPD Article 46</span></span>
- <span data-ttu-id="4fdf8-113">Artigo 48 do LGPD</span><span class="sxs-lookup"><span data-stu-id="4fdf8-113">LGPD Article 48</span></span>
- <span data-ttu-id="4fdf8-114">Artigo RGPD (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="4fdf8-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="4fdf8-115">Artigo RGPD (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="4fdf8-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="4fdf8-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="4fdf8-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="4fdf8-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="4fdf8-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="4fdf8-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="4fdf8-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="4fdf8-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="4fdf8-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="4fdf8-121">164.312(b))</span></span>
- <span data-ttu-id="4fdf8-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="4fdf8-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="4fdf8-123">Para obter mais informações, consulte [Avaliar riscos de privacidade de dados e identificar informações confidenciais.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="4fdf8-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="4fdf8-124">Os regulamentos de privacidade de dados geralmente chamam o seguinte para monitoramento e resposta:</span><span class="sxs-lookup"><span data-stu-id="4fdf8-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="4fdf8-125">Auditoria, alerta e relatórios para atividades relacionadas ao armazenamento, compartilhamento e processamento de dados pessoais</span><span class="sxs-lookup"><span data-stu-id="4fdf8-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="4fdf8-126">A capacidade de responder a uma solicitação de assunto de dados (DSR) e, em alguns casos, executar medidas administrativas e investigativas para atender a essas solicitações.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="4fdf8-127">Sua organização também pode desejar realizar atividades de monitoramento e resposta para outros fins, como outras necessidades de conformidade ou por motivos comerciais.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="4fdf8-128">O estabelecimento do seu esquema de monitoramento e resposta para privacidade de dados deve ser feito como parte do planejamento, implementação e gerenciamento geral de monitoramento e resposta.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="4fdf8-129">Para ajudá-lo a começar com um esquema de monitoramento e resposta no Microsoft 365 para regulamentos de privacidade de dados, este artigo lista recursos úteis no Microsoft 365 para responder a perguntas como:</span><span class="sxs-lookup"><span data-stu-id="4fdf8-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="4fdf8-130">Que tipo de monitoramento, investigações e técnicas de relatórios do dia a dia estão disponíveis para os diferentes tipos de dados e fontes?</span><span class="sxs-lookup"><span data-stu-id="4fdf8-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="4fdf8-131">Quais mecanismos serão necessários para lidar com solicitações de assunto de dados (DSRs) e quaisquer ações corretivas, como anonimização, redação e exclusão.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="4fdf8-132">Auditoria e políticas de alerta no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="4fdf8-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="4fdf8-133">Consulte estes artigos para configurar a auditoria, auditoria avançada e políticas de alerta:</span><span class="sxs-lookup"><span data-stu-id="4fdf8-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="4fdf8-134">Auditoria unificada</span><span class="sxs-lookup"><span data-stu-id="4fdf8-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="4fdf8-135">Auditoria de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="4fdf8-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="4fdf8-136">Auditoria avançada</span><span class="sxs-lookup"><span data-stu-id="4fdf8-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="4fdf8-137">Políticas de alerta</span><span class="sxs-lookup"><span data-stu-id="4fdf8-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="4fdf8-138">Solicitações de assunto de dados para o RGPD e o CCPA</span><span class="sxs-lookup"><span data-stu-id="4fdf8-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="4fdf8-139">Consulte [Solicitações de Assunto de Dados para o RGPD](/compliance/regulatory/gdpr-dsr-Office365) e CCPA para obter informações sobre como responder a uma DSR no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="4fdf8-140">Gerenciar usuários excluídos no Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4fdf8-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="4fdf8-141">Para o Microsoft Stream, quando um usuário é excluído do Azure Active Directory (Azure AD), se seu nome foi associado a um vídeo stream postado antes desse ponto, seu endereço de email permanece associado ao vídeo.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="4fdf8-142">Consulte [Gerenciar usuários excluídos do Microsoft Stream para](/stream/managing-deleted-users) removê-lo.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="4fdf8-143">Gerenciamento de riscos insider como uma ferramenta de investigação</span><span class="sxs-lookup"><span data-stu-id="4fdf8-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="4fdf8-144">O gerenciamento de riscos internos no [Microsoft 365](../compliance/insider-risk-management.md) é um recurso do Centro de administração de Conformidade da Microsoft para ajudá-lo a minimizar o risco interno, permitindo que você detecte, investigue e tome medidas sobre atividades arriscadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4fdf8-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>