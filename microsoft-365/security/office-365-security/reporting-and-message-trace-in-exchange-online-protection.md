---
title: Relatórios e rastreamento de mensagem no Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/18/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: O Microsoft Proteção do Exchange Online (EOP) oferece muitos relatórios diferentes que podem ajudá-lo a determinar o status e a integridade gerais de sua organização. Existem também ferramentas que ajudam você a solucionar problemas com eventos específicos (tais como uma mensagem que não chega aos destinatários pretendidos), e relatórios de auditoria para ajudar nos requisitos de conformidade. A tabela a seguir descreve os relatórios e as ferramentas de solução de problemas disponíveis para o administradores de EOP.
ms.openlocfilehash: 39ac70c401cb4a630b95fab89fe3a145495c29eb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071804"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="84a01-105">Relatórios e rastreamento de mensagem no Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="84a01-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="84a01-106">O Microsoft Proteção do Exchange Online (EOP) oferece muitos relatórios diferentes que podem ajudá-lo a determinar o status e a integridade gerais de sua organização.</span><span class="sxs-lookup"><span data-stu-id="84a01-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="84a01-107">Existem também ferramentas que ajudam você a solucionar problemas com eventos específicos (tais como uma mensagem que não chega aos destinatários pretendidos), e relatórios de auditoria para ajudar nos requisitos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="84a01-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="84a01-108">Relatórios de uso</span><span class="sxs-lookup"><span data-stu-id="84a01-108">Usage reports</span></span>

<span data-ttu-id="84a01-109">**Atividade de grupos do office 365**: exibir informações sobre o número de grupos do Office 365 que são criados e usados.</span><span class="sxs-lookup"><span data-stu-id="84a01-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="84a01-110">**Atividade de email**: exibir informações sobre o número de mensagens enviadas, recebidas e lidas em toda sua organização e por usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="84a01-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="84a01-111">**Uso do aplicativo de email**: exibir informações sobre os aplicativos de email usados.</span><span class="sxs-lookup"><span data-stu-id="84a01-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="84a01-112">Isso inclui o número total de conexões para cada aplicativo, e as versões do Outlook que estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="84a01-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="84a01-113">**Uso da caixa de correio**: exibir informações sobre o armazenamento usado, consumo de cota, contagem de itens e última atividade (atividade de envio ou leitura) para caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="84a01-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="84a01-114">Confira os recursos a seguir para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="84a01-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="84a01-115">Relatórios do Office 365 no centro de administração-grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="84a01-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610)

- [<span data-ttu-id="84a01-116">Relatórios do Office 365 no Centro de administrador - Atividade de email</span><span class="sxs-lookup"><span data-stu-id="84a01-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706)

- [<span data-ttu-id="84a01-117">Relatórios do Office 365 no Centro de administrador - Uso do aplicativo de email</span><span class="sxs-lookup"><span data-stu-id="84a01-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)

- [<span data-ttu-id="84a01-118">Relatórios do Office 365 no Centro de administrador - Uso de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="84a01-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="84a01-119">Relatórios de segurança & conformidade no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84a01-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="84a01-120">Esses relatórios aprimorados fornecem uma experiência de relatório interativa para administradores do EOP, que inclui informações de resumo e a capacidade de aprofundar para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="84a01-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="84a01-121">**Proteção avançada contra ameaças (ATP)**: exibir informações sobre links seguros e anexos seguros que fazem parte da ATP.</span><span class="sxs-lookup"><span data-stu-id="84a01-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="84a01-122">**EOP**: exibir informações sobre detecções de malware, email falsificado, detecções de spam e fluxo de emails para e da sua organização.</span><span class="sxs-lookup"><span data-stu-id="84a01-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="84a01-123">Exibir relatórios para proteção avançada contra ameaças e proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="84a01-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="84a01-124">Relatórios personalizados usando o Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="84a01-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="84a01-125">Criar programaticamente relatórios disponíveis no centro de administração do Microsoft 365 usando o Microsoft Graph Confira os subtópicos sobre [como trabalhar com os relatórios de uso do Office 365 no Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span><span class="sxs-lookup"><span data-stu-id="84a01-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span>

## <a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="84a01-126">Relatórios personalizados usando serviços Web de relatório</span><span class="sxs-lookup"><span data-stu-id="84a01-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="84a01-127">Criar programaticamente relatórios dos cmdlets disponíveis de relatórios do PowerShell do Exchange Online Protection usando a filtragem de consulta REST/ODATA2.</span><span class="sxs-lookup"><span data-stu-id="84a01-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="84a01-128">Confira [Serviços Web de relatório do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span><span class="sxs-lookup"><span data-stu-id="84a01-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span>

## <a name="message-trace"></a><span data-ttu-id="84a01-129">Rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="84a01-129">Message trace</span></span>

<span data-ttu-id="84a01-130">Acompanhe as mensagens enviadas conforme elas circulam através di EOP.</span><span class="sxs-lookup"><span data-stu-id="84a01-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="84a01-131">Você pode determinar se uma mensagem de email foi recebida, rejeitada, adiada ou entregue pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="84a01-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="84a01-132">Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.</span><span class="sxs-lookup"><span data-stu-id="84a01-132">It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="84a01-133">Você pode usar essa informação para responder com eficiência às perguntas dos seus usuários, solucionar problemas de fluxo de email, validar alterações de política e reduzir a necessidade de contatar o suporte técnico para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="84a01-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="84a01-134">Consulte [rastrear uma mensagem de email](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="84a01-134">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="84a01-135">Registro em log de auditoria</span><span class="sxs-lookup"><span data-stu-id="84a01-135">Audit logging</span></span>

<span data-ttu-id="84a01-136">Rastreie alterações específica feitas pelos administradores na sua organização.</span><span class="sxs-lookup"><span data-stu-id="84a01-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="84a01-137">Estes relatórios ajudam você a solucionar problemas de configuração ou a encontrar a causa de problemas relacionados à conformidade ou à segurança.</span><span class="sxs-lookup"><span data-stu-id="84a01-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="84a01-138">Confira [relatórios de auditoria no EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="84a01-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="84a01-139">Disponibilidade e latência de dados de relatórios e rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="84a01-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="84a01-140">A tabela a seguir descreve quando dados de relatórios e rastreamento de mensagens do EOP estão disponíveis e por quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="84a01-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="84a01-141">**Tipo de relatório**</span><span class="sxs-lookup"><span data-stu-id="84a01-141">**Report type**</span></span>|<span data-ttu-id="84a01-142">**Dados disponíveis por (período retrospectivo)**</span><span class="sxs-lookup"><span data-stu-id="84a01-142">**Data available for (look back period)**</span></span>|<span data-ttu-id="84a01-143">**Latência**</span><span class="sxs-lookup"><span data-stu-id="84a01-143">**Latency**</span></span>|
|<span data-ttu-id="84a01-144">Relatórios de Resumo de proteção de email</span><span class="sxs-lookup"><span data-stu-id="84a01-144">Mail protection summary reports</span></span>|<span data-ttu-id="84a01-145">90 dias</span><span class="sxs-lookup"><span data-stu-id="84a01-145">90 days</span></span>|<span data-ttu-id="84a01-p106">A agregação de dados de mensagens geralmente é concluída em 24 a 48 horas. Algumas pequenas alterações agregadas progressivas podem ocorrer por até 5 dias.</span><span class="sxs-lookup"><span data-stu-id="84a01-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="84a01-148">Relatórios de detalhes de proteção de email</span><span class="sxs-lookup"><span data-stu-id="84a01-148">Mail protection detail reports</span></span>|<span data-ttu-id="84a01-149">90 dias</span><span class="sxs-lookup"><span data-stu-id="84a01-149">90 days</span></span>|<span data-ttu-id="84a01-p107">Para obter dados detalhados de um período menor que 7 dias, os dados deverão aparecer no prazo de 24 horas, mas a operação talvez não seja concluída em até 48 horas. Algumas pequenas alterações incrementais podem ocorrer por até 5 dias.</span><span class="sxs-lookup"><span data-stu-id="84a01-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="84a01-152">Para exibir relatórios detalhados de mensagens ocorridas em um período superior a sete dias, os resultados podem demorar umas poucas horas.</span><span class="sxs-lookup"><span data-stu-id="84a01-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="84a01-153">Dados de rastreamento de mensagem</span><span class="sxs-lookup"><span data-stu-id="84a01-153">Message trace data</span></span>|<span data-ttu-id="84a01-154">90 dias</span><span class="sxs-lookup"><span data-stu-id="84a01-154">90 days</span></span>|<span data-ttu-id="84a01-155">Ao rastrear mensagens ocorridas em um período menor que 7 dias, as mensagens devem aparecer no intervalo de 5 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="84a01-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="84a01-156">Ao rastrear mensagens ocorridas em um período superior a 7 dias, os resultados podem demorar umas poucas horas.</span><span class="sxs-lookup"><span data-stu-id="84a01-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="84a01-157">A disponibilidade e a latência dos dados é a mesma, seja ela solicitada por meio do centro de administração do Microsoft 365 ou do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="84a01-157">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span> 
