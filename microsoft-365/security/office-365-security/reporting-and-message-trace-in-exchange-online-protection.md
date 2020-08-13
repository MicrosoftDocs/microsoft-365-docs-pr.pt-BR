---
title: Relatórios e rastreamento de mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre relatórios e ferramentas de solução de problemas disponíveis para os administradores do Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: ddf8c021681bb600548b134d678d1e0fb0f29d0c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652796"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="58d47-103">Relatórios e rastreamento de mensagens no EOP</span><span class="sxs-lookup"><span data-stu-id="58d47-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="58d47-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP oferece vários relatórios diferentes que podem ajudá-lo a determinar o status e a integridade gerais de sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d47-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="58d47-105">Existem também ferramentas que ajudam você a solucionar problemas com eventos específicos (tais como uma mensagem que não chega aos destinatários pretendidos), e relatórios de auditoria para ajudar nos requisitos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="58d47-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="58d47-106">Relatórios de uso</span><span class="sxs-lookup"><span data-stu-id="58d47-106">Usage reports</span></span>

<span data-ttu-id="58d47-107">**Atividade de grupos do microsoft 365**: exibir informações sobre o número de grupos do Microsoft 365 que são criados e usados.</span><span class="sxs-lookup"><span data-stu-id="58d47-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="58d47-108">**Atividade de email**: exibir informações sobre o número de mensagens enviadas, recebidas e lidas em toda sua organização e por usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="58d47-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="58d47-109">**Uso do aplicativo de email**: exibir informações sobre os aplicativos de email usados.</span><span class="sxs-lookup"><span data-stu-id="58d47-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="58d47-110">Isso inclui o número total de conexões para cada aplicativo, e as versões do Outlook que estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="58d47-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="58d47-111">**Uso da caixa de correio**: exibir informações sobre o armazenamento usado, consumo de cota, contagem de itens e última atividade (atividade de envio ou leitura) para caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="58d47-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="58d47-112">Veja os seguintes recursos para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="58d47-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="58d47-113">Relatórios do Microsoft 365 no centro de administração-Microsoft 365 grupos</span><span class="sxs-lookup"><span data-stu-id="58d47-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="58d47-114">Relatórios do Microsoft 365 no centro de administração-atividade de email</span><span class="sxs-lookup"><span data-stu-id="58d47-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="58d47-115">Relatórios do Microsoft 365 no centro de administração-uso de aplicativos de email</span><span class="sxs-lookup"><span data-stu-id="58d47-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="58d47-116">Relatórios da Microsoft 365 no centro de administração-uso da caixa de correio</span><span class="sxs-lookup"><span data-stu-id="58d47-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="58d47-117">Relatórios de segurança & conformidade no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58d47-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="58d47-118">Esses relatórios aprimorados fornecem uma experiência de relatório interativa para administradores do EOP, que inclui informações de resumo e a capacidade de aprofundar para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="58d47-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="58d47-119">**Proteção avançada contra ameaças (ATP)**: exibir informações sobre links seguros e anexos seguros que fazem parte da ATP.</span><span class="sxs-lookup"><span data-stu-id="58d47-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="58d47-120">**EOP**: exibir informações sobre detecções de malware, email falsificado, detecções de spam e fluxo de emails para e da sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d47-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="58d47-121">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="58d47-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="58d47-122">Relatórios personalizados usando o Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="58d47-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="58d47-123">Criar programaticamente relatórios disponíveis no centro de administração usando o Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="58d47-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="58d47-124">Para obter mais informações, consulte [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) e [Working with Office 365 Usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="58d47-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="58d47-125">Rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="58d47-125">Message trace</span></span>

<span data-ttu-id="58d47-126">Acompanhe as mensagens enviadas conforme elas circulam através di EOP.</span><span class="sxs-lookup"><span data-stu-id="58d47-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="58d47-127">Você pode determinar se uma mensagem de email foi recebida, rejeitada, adiada ou entregue pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="58d47-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="58d47-128">Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.</span><span class="sxs-lookup"><span data-stu-id="58d47-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="58d47-129">Você pode usar essa informação para responder com eficiência às perguntas dos seus usuários, solucionar problemas de fluxo de email, validar alterações de política e reduzir a necessidade de contatar o suporte técnico para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="58d47-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="58d47-130">Consulte [rastreamento de mensagens no centro de conformidade & segurança](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="58d47-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="58d47-131">Registro em log de auditoria</span><span class="sxs-lookup"><span data-stu-id="58d47-131">Audit logging</span></span>

<span data-ttu-id="58d47-132">Rastreie alterações específica feitas pelos administradores na sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d47-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="58d47-133">Estes relatórios ajudam você a solucionar problemas de configuração ou a encontrar a causa de problemas relacionados à conformidade ou à segurança.</span><span class="sxs-lookup"><span data-stu-id="58d47-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="58d47-134">Confira [relatórios de auditoria no EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="58d47-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="58d47-135">Disponibilidade e latência de dados de relatórios e rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="58d47-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="58d47-136">A tabela a seguir descreve quando dados de relatórios e rastreamento de mensagens do EOP estão disponíveis e por quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="58d47-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="58d47-137">Tipo de relatório</span><span class="sxs-lookup"><span data-stu-id="58d47-137">Report type</span></span>|<span data-ttu-id="58d47-138">Dados disponíveis por (período retrospectivo)</span><span class="sxs-lookup"><span data-stu-id="58d47-138">Data available for (look back period)</span></span>|<span data-ttu-id="58d47-139">Latência</span><span class="sxs-lookup"><span data-stu-id="58d47-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="58d47-140">Relatórios de Resumo de proteção de email</span><span class="sxs-lookup"><span data-stu-id="58d47-140">Mail protection summary reports</span></span>|<span data-ttu-id="58d47-141">90 dias</span><span class="sxs-lookup"><span data-stu-id="58d47-141">90 days</span></span>|<span data-ttu-id="58d47-p106">A agregação de dados de mensagens geralmente é concluída em 24 a 48 horas. Algumas pequenas alterações agregadas progressivas podem ocorrer por até 5 dias.</span><span class="sxs-lookup"><span data-stu-id="58d47-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="58d47-144">Relatórios de detalhes de proteção de email</span><span class="sxs-lookup"><span data-stu-id="58d47-144">Mail protection detail reports</span></span>|<span data-ttu-id="58d47-145">90 dias</span><span class="sxs-lookup"><span data-stu-id="58d47-145">90 days</span></span>|<span data-ttu-id="58d47-p107">Para obter dados detalhados de um período menor que 7 dias, os dados deverão aparecer no prazo de 24 horas, mas a operação talvez não seja concluída em até 48 horas. Algumas pequenas alterações incrementais podem ocorrer por até 5 dias.</span><span class="sxs-lookup"><span data-stu-id="58d47-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="58d47-148">Para exibir relatórios detalhados de mensagens ocorridas em um período superior a sete dias, os resultados podem demorar umas poucas horas.</span><span class="sxs-lookup"><span data-stu-id="58d47-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="58d47-149">Dados de rastreamento de mensagem</span><span class="sxs-lookup"><span data-stu-id="58d47-149">Message trace data</span></span>|<span data-ttu-id="58d47-150">90 dias</span><span class="sxs-lookup"><span data-stu-id="58d47-150">90 days</span></span>|<span data-ttu-id="58d47-151">Ao rastrear mensagens ocorridas em um período menor que 7 dias, as mensagens devem aparecer no intervalo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="58d47-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="58d47-152">Ao rastrear mensagens ocorridas em um período superior a 7 dias, os resultados podem demorar umas poucas horas.</span><span class="sxs-lookup"><span data-stu-id="58d47-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="58d47-153">A disponibilidade e a latência dos dados é a mesma, seja ela solicitada por meio do centro de administração ou do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="58d47-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
