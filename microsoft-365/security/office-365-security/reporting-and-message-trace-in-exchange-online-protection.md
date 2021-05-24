---
title: Relatórios e rastreamento de mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre relatórios e ferramentas de solução de problemas disponíveis para administradores Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae55ded9d907754161813c9f7bfa7eeb14c558a8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625024"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="cddc9-103">Rastreamento de relatórios e mensagens no EOP</span><span class="sxs-lookup"><span data-stu-id="cddc9-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cddc9-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="cddc9-104">**Applies to**</span></span>
- [<span data-ttu-id="cddc9-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cddc9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cddc9-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cddc9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cddc9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cddc9-108">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, o EOP oferece muitos relatórios diferentes que podem ajudá-lo a determinar o status geral e a saúde da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cddc9-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="cddc9-109">Existem também ferramentas que ajudam você a solucionar problemas com eventos específicos (tais como uma mensagem que não chega aos destinatários pretendidos), e relatórios de auditoria para ajudar nos requisitos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="cddc9-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="cddc9-110">Relatórios de uso</span><span class="sxs-lookup"><span data-stu-id="cddc9-110">Usage reports</span></span>

<span data-ttu-id="cddc9-111">**Microsoft 365 de grupos**: Exibir informações sobre o número de grupos Microsoft 365 que são criados e usados.</span><span class="sxs-lookup"><span data-stu-id="cddc9-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="cddc9-112">**Atividade de email**: Exibir informações sobre o número de mensagens enviadas, recebidas e lidas em toda a organização e por usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="cddc9-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="cddc9-113">**Uso do aplicativo de** email : Exibir informações sobre os aplicativos de email usados.</span><span class="sxs-lookup"><span data-stu-id="cddc9-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="cddc9-114">Isso inclui o número total de conexões para cada aplicativo, e as versões do Outlook que estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="cddc9-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="cddc9-115">**Uso da** caixa de correio : Exibir informações sobre armazenamento usado, consumo de cota, contagem de itens e última atividade (atividade de envio ou leitura) para caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="cddc9-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="cddc9-116">Veja os seguintes recursos para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="cddc9-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="cddc9-117">Microsoft 365 Relatórios no centro de administração - Microsoft 365 grupos</span><span class="sxs-lookup"><span data-stu-id="cddc9-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="cddc9-118">Microsoft 365 Relatórios no centro de administração - Atividade de email</span><span class="sxs-lookup"><span data-stu-id="cddc9-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="cddc9-119">Microsoft 365 Relatórios no centro de administração - Uso de aplicativos de email</span><span class="sxs-lookup"><span data-stu-id="cddc9-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="cddc9-120">Microsoft 365 Relatórios no centro de administração - Uso da caixa de correio</span><span class="sxs-lookup"><span data-stu-id="cddc9-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="cddc9-121">Relatórios & de conformidade de segurança no Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="cddc9-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="cddc9-122">Esses relatórios aprimorados fornecem uma experiência interativa de relatórios para os administradores do EOP, que inclui informações resumidas e a capacidade de detalhar para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="cddc9-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="cddc9-123">**Defender for Office 365**: Exibir informações sobre Cofre Links e Cofre anexos que fazem parte do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="cddc9-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="cddc9-124">**EOP**: Exibir informações sobre detecções de malware, emails empoados, detecções de spam e fluxo de emails de e para sua organização.</span><span class="sxs-lookup"><span data-stu-id="cddc9-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="cddc9-125">Exibir relatórios do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cddc9-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="cddc9-126">Relatórios personalizados usando o Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="cddc9-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="cddc9-127">Crie relatórios programaticamente disponíveis no centro de administração usando o Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="cddc9-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="cddc9-128">Para obter mais informações, consulte [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph](/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="cddc9-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="cddc9-129">Rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="cddc9-129">Message trace</span></span>

<span data-ttu-id="cddc9-130">Acompanhe as mensagens enviadas conforme elas circulam através di EOP.</span><span class="sxs-lookup"><span data-stu-id="cddc9-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="cddc9-131">Você pode determinar se uma mensagem de email foi recebida, rejeitada, adiada ou entregue pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="cddc9-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="cddc9-132">Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.</span><span class="sxs-lookup"><span data-stu-id="cddc9-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="cddc9-133">Você pode usar essa informação para responder com eficiência às perguntas dos seus usuários, solucionar problemas de fluxo de email, validar alterações de política e reduzir a necessidade de contatar o suporte técnico para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="cddc9-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="cddc9-134">Consulte [Rastreamento de mensagens no Centro de Conformidade & segurança.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="cddc9-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="cddc9-135">Registro em log de auditoria</span><span class="sxs-lookup"><span data-stu-id="cddc9-135">Audit logging</span></span>

<span data-ttu-id="cddc9-136">Rastreie alterações específica feitas pelos administradores na sua organização.</span><span class="sxs-lookup"><span data-stu-id="cddc9-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="cddc9-137">Estes relatórios ajudam você a solucionar problemas de configuração ou a encontrar a causa de problemas relacionados à conformidade ou à segurança.</span><span class="sxs-lookup"><span data-stu-id="cddc9-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="cddc9-138">Consulte [Relatórios de auditoria em Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span><span class="sxs-lookup"><span data-stu-id="cddc9-138">See [Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="cddc9-139">Disponibilidade e latência de dados de relatórios e rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="cddc9-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="cddc9-140">A tabela a seguir descreve quando dados de relatórios e rastreamento de mensagens do EOP estão disponíveis e por quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="cddc9-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="cddc9-141">Tipo de relatório</span><span class="sxs-lookup"><span data-stu-id="cddc9-141">Report type</span></span>|<span data-ttu-id="cddc9-142">Dados disponíveis por (período retrospectivo)</span><span class="sxs-lookup"><span data-stu-id="cddc9-142">Data available for (look back period)</span></span>|<span data-ttu-id="cddc9-143">Latência</span><span class="sxs-lookup"><span data-stu-id="cddc9-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="cddc9-144">Relatórios de resumo de proteção de email</span><span class="sxs-lookup"><span data-stu-id="cddc9-144">Mail protection summary reports</span></span>|<span data-ttu-id="cddc9-145">90 dias</span><span class="sxs-lookup"><span data-stu-id="cddc9-145">90 days</span></span>|<span data-ttu-id="cddc9-p106">A agregação de dados de mensagens geralmente é concluída em 24 a 48 horas. Algumas pequenas alterações agregadas progressivas podem ocorrer por até 5 dias.</span><span class="sxs-lookup"><span data-stu-id="cddc9-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="cddc9-148">Relatórios detalhados de proteção de email</span><span class="sxs-lookup"><span data-stu-id="cddc9-148">Mail protection detail reports</span></span>|<span data-ttu-id="cddc9-149">90 dias</span><span class="sxs-lookup"><span data-stu-id="cddc9-149">90 days</span></span>|<span data-ttu-id="cddc9-p107">Para obter dados detalhados de um período menor que 7 dias, os dados deverão aparecer no prazo de 24 horas, mas a operação talvez não seja concluída em até 48 horas. Algumas pequenas alterações incrementais podem ocorrer por até 5 dias.</span><span class="sxs-lookup"><span data-stu-id="cddc9-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="cddc9-152">Para exibir relatórios detalhados de mensagens ocorridas em um período superior a sete dias, os resultados podem demorar umas poucas horas.</span><span class="sxs-lookup"><span data-stu-id="cddc9-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="cddc9-153">Dados de rastreamento de mensagem</span><span class="sxs-lookup"><span data-stu-id="cddc9-153">Message trace data</span></span>|<span data-ttu-id="cddc9-154">90 dias</span><span class="sxs-lookup"><span data-stu-id="cddc9-154">90 days</span></span>|<span data-ttu-id="cddc9-155">Ao rastrear mensagens ocorridas em um período menor que 7 dias, as mensagens devem aparecer no intervalo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="cddc9-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="cddc9-156">Ao rastrear mensagens ocorridas em um período superior a 7 dias, os resultados podem demorar umas poucas horas.</span><span class="sxs-lookup"><span data-stu-id="cddc9-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="cddc9-157">A disponibilidade e a latência de dados são as mesmas solicitadas por meio do centro de administração ou do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="cddc9-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>