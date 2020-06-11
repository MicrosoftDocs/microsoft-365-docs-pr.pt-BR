---
title: Monitorar e responder a incidentes de privacidade de dados em sua organização
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Use as políticas de auditoria e de alerta e as solicitações de entidades de dados para monitorar e responder a incidentes de dados pessoais.
ms.openlocfilehash: 5760bb40eb26e2ff0636ea9604cc7c45b7d0ca63
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695062"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="e1177-103">Monitorar e responder a incidentes de privacidade de dados em sua organização</span><span class="sxs-lookup"><span data-stu-id="e1177-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="e1177-104">Os recursos do Microsoft 365 estão disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você opera os recursos relacionados.</span><span class="sxs-lookup"><span data-stu-id="e1177-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="e1177-105">Ter processos, procedimentos e outras documentações para cada um deles também pode ser importante para demonstrar conformidade com órgãos regulamentares.</span><span class="sxs-lookup"><span data-stu-id="e1177-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="e1177-106">Entre eles:</span><span class="sxs-lookup"><span data-stu-id="e1177-106">These include:</span></span> 

- <span data-ttu-id="e1177-107">Políticas de auditoria e alertas</span><span class="sxs-lookup"><span data-stu-id="e1177-107">Auditing and alert policies</span></span>
- <span data-ttu-id="e1177-108">Solicitações de entidades de dados (incluindo pesquisa de conteúdo e descoberta eletrônica)</span><span class="sxs-lookup"><span data-stu-id="e1177-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="e1177-109">Ferramentas e relatórios adicionais investigativos</span><span class="sxs-lookup"><span data-stu-id="e1177-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="e1177-110">Regulamentações de privacidade de dados que afetam o uso de ferramentas de monitoramento e resposta</span><span class="sxs-lookup"><span data-stu-id="e1177-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="e1177-111">Aqui está uma lista de exemplos de regulamentos de privacidade de dados que podem se relacionar aos controles de governança de informações:</span><span class="sxs-lookup"><span data-stu-id="e1177-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="e1177-112">LGPD artigo 46</span><span class="sxs-lookup"><span data-stu-id="e1177-112">LGPD Article 46</span></span>
- <span data-ttu-id="e1177-113">LGPD artigo 48</span><span class="sxs-lookup"><span data-stu-id="e1177-113">LGPD Article 48</span></span>
- <span data-ttu-id="e1177-114">RGPD artigo (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="e1177-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="e1177-115">Artigo RGPD (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="e1177-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="e1177-116">HIPAA-ALTA TECNOLOGIA (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="e1177-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="e1177-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="e1177-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="e1177-118">HIPAA-ALTA TECNOLOGIA (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="e1177-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="e1177-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="e1177-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="e1177-120">HIPAA-ALTA TECNOLOGIA (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="e1177-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="e1177-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="e1177-121">164.312(b))</span></span>
- <span data-ttu-id="e1177-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="e1177-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="e1177-123">Para obter mais informações, consulte [avaliar riscos de privacidade de dados e identificar informações confidenciais](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="e1177-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="e1177-124">Os regulamentos de privacidade de dados geralmente chamam os seguintes itens para monitoramento e resposta:</span><span class="sxs-lookup"><span data-stu-id="e1177-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="e1177-125">Auditoria, alerta e emissão de relatórios para atividades relacionadas ao armazenamento, compartilhamento e processamento de dados pessoais</span><span class="sxs-lookup"><span data-stu-id="e1177-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="e1177-126">A capacidade de responder a uma solicitação de entidades de dados (DSR) e, em alguns casos, executar investigação e outras medidas administrativas para cumprir essas solicitações.</span><span class="sxs-lookup"><span data-stu-id="e1177-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="e1177-127">Sua organização também pode desejar realizar atividades de monitoramento e resposta para outros fins, como outras necessidades de conformidade ou por motivos de negócios.</span><span class="sxs-lookup"><span data-stu-id="e1177-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="e1177-128">O estabelecimento do esquema de monitoramento e resposta para privacidade de dados deve ser feito como parte do planejamento, da implementação e do gerenciamento de resposta e monitoramento geral.</span><span class="sxs-lookup"><span data-stu-id="e1177-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="e1177-129">Para ajudá-lo a começar a usar um esquema de monitoramento e resposta no Microsoft 365 for Data Privacy Regulations, este artigo lista recursos úteis no Microsoft 365 para responder a perguntas como:</span><span class="sxs-lookup"><span data-stu-id="e1177-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="e1177-130">Que espécie de monitoramento de dia a dia, técnicas investigativas e de relatórios estão disponíveis para os diferentes tipos de dados e fontes?</span><span class="sxs-lookup"><span data-stu-id="e1177-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="e1177-131">Quais mecanismos serão necessários para lidar com as solicitações de entidades de dados (DSRs) e quaisquer ações corretivas, como anonimato, redação e exclusão.</span><span class="sxs-lookup"><span data-stu-id="e1177-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="e1177-132">Auditoria e políticas de alerta no centro de conformidade e segurança</span><span class="sxs-lookup"><span data-stu-id="e1177-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="e1177-133">Consulte estes artigos para configurar auditorias, auditoria avançada e políticas de alerta:</span><span class="sxs-lookup"><span data-stu-id="e1177-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="e1177-134">Auditoria unificada</span><span class="sxs-lookup"><span data-stu-id="e1177-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="e1177-135">Auditoria de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="e1177-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="e1177-136">Auditoria avançada</span><span class="sxs-lookup"><span data-stu-id="e1177-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="e1177-137">Políticas de alerta</span><span class="sxs-lookup"><span data-stu-id="e1177-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="e1177-138">Solicitações de entidades de dados para o RGPD e o CCPA</span><span class="sxs-lookup"><span data-stu-id="e1177-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="e1177-139">Consulte [solicitações de entidades de dados para o rgpd e o CCPA](../compliance/gdpr-dsr-office365.md) para obter informações sobre como responder a um DSR no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1177-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="e1177-140">Gerenciar usuários excluídos no Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="e1177-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="e1177-141">Para o Microsoft Stream, quando um usuário é excluído do Azure Active Directory (Azure AD), se o nome tiver sido associado a um vídeo de fluxo Postado antes desse ponto, o endereço de email permanecerá associado ao vídeo.</span><span class="sxs-lookup"><span data-stu-id="e1177-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="e1177-142">Consulte [Manage Deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) para removê-lo.</span><span class="sxs-lookup"><span data-stu-id="e1177-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="e1177-143">Ferramentas adicionais investigativas</span><span class="sxs-lookup"><span data-stu-id="e1177-143">Additional investigative tools</span></span>

<span data-ttu-id="e1177-144">Aqui estão duas ferramentas adicionais que podem ser úteis para monitorar, investigar e corrigir incidentes relacionados à privacidade de dados em sua organização:</span><span class="sxs-lookup"><span data-stu-id="e1177-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="e1177-145">[Gerenciamento de risco do insider no microsoft 365](../compliance/insider-risk-management.md), um recurso do centro de administração de conformidade da Microsoft para ajudar a minimizar o risco interno, permitindo que você detecte, investigue e execute ações sobre atividades arriscadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e1177-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="e1177-146">[Investigações de dados no microsoft 365](../compliance/overview-data-investigations.md), um recurso do centro de administração de conformidade da Microsoft para pesquisar dados confidenciais, maliciosos ou incorretos no Microsoft 365 e, em seguida, investigue o que aconteceu em tomar as ações apropriadas para corrigir o incidente.</span><span class="sxs-lookup"><span data-stu-id="e1177-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
