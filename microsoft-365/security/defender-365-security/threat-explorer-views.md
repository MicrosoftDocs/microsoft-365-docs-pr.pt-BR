---
title: Exibições no Explorador de Ameaças e detecções em tempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba como usar o Explorador de Ameaças e o relatório de detecções em tempo real para investigar e responder a ameaças no Centro de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78c03b45063f4bc34b47ab003bcf00d2befab886
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053098"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="e5cd7-103">Exibições no Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="e5cd7-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e5cd7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e5cd7-104">**Applies to**</span></span>
- [<span data-ttu-id="e5cd7-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e5cd7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e5cd7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5cd7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![Explorador de Ameaças](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="e5cd7-108">[O Explorador](threat-explorer.md) de Ameaças (e o relatório de detecções em tempo real) é uma ferramenta poderosa e quase em tempo real para ajudar as equipes de Operações de Segurança a investigar e responder a ameaças no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="e5cd7-109">O Explorer (e o relatório de detecções em tempo real) exibe informações sobre suspeita de malware e phishing em emails e arquivos no Office 365, bem como outras ameaças e riscos de segurança à sua organização.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="e5cd7-110">Se você tiver [o Microsoft Defender para Office 365](defender-for-office-365.md) Plano 2, terá o Explorer.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="e5cd7-111">Se você tiver o Microsoft Defender para Office 365 Plano 1, terá detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="e5cd7-112">Quando você abre o Explorer pela primeira vez (ou o relatório de detecções em tempo real), o modo de exibição padrão mostra detecções de malware de email nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="e5cd7-113">Este relatório também pode mostrar detecções do Microsoft Defender para Office 365, como URLs mal-intencionadas detectadas por Links Seguros [e](safe-links.md)arquivos mal-intencionados detectados por [Anexos Seguros.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="e5cd7-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="e5cd7-114">Este relatório pode ser modificado para mostrar dados dos últimos 30 dias (com uma assinatura paga do Microsoft Defender para Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="e5cd7-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="e5cd7-115">As assinaturas de avaliação incluirão dados apenas nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="e5cd7-116">Assinatura</span><span class="sxs-lookup"><span data-stu-id="e5cd7-116">Subscription</span></span>|<span data-ttu-id="e5cd7-117">Utilitário</span><span class="sxs-lookup"><span data-stu-id="e5cd7-117">Utility</span></span>|<span data-ttu-id="e5cd7-118">Dias de Dados</span><span class="sxs-lookup"><span data-stu-id="e5cd7-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="e5cd7-119">Avaliação do Microsoft Defender para Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="e5cd7-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="e5cd7-120">Detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="e5cd7-120">Real-time detections</span></span>|<span data-ttu-id="e5cd7-121">7 </span><span class="sxs-lookup"><span data-stu-id="e5cd7-121">7</span></span>|
|<span data-ttu-id="e5cd7-122">Microsoft Defender para Office 365 P1 pago</span><span class="sxs-lookup"><span data-stu-id="e5cd7-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="e5cd7-123">Detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="e5cd7-123">Real-time detections</span></span>|<span data-ttu-id="e5cd7-124">30</span><span class="sxs-lookup"><span data-stu-id="e5cd7-124">30</span></span>|
|<span data-ttu-id="e5cd7-125">Avaliação paga do Microsoft Defender para Office 365 P1 para Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="e5cd7-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="e5cd7-126">Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="e5cd7-126">Threat Explorer</span></span>|<span data-ttu-id="e5cd7-127">7 </span><span class="sxs-lookup"><span data-stu-id="e5cd7-127">7</span></span>|
|<span data-ttu-id="e5cd7-128">Avaliação do Microsoft Defender para Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="e5cd7-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="e5cd7-129">Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="e5cd7-129">Threat Explorer</span></span>|<span data-ttu-id="e5cd7-130">7 </span><span class="sxs-lookup"><span data-stu-id="e5cd7-130">7</span></span>|
|<span data-ttu-id="e5cd7-131">Microsoft Defender para Office 365 P2 pago</span><span class="sxs-lookup"><span data-stu-id="e5cd7-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="e5cd7-132">Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="e5cd7-132">Threat Explorer</span></span>|<span data-ttu-id="e5cd7-133">30</span><span class="sxs-lookup"><span data-stu-id="e5cd7-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="e5cd7-134">Em breve, estenderemos a retenção de dados do Explorer (e detecções em tempo real) e o limite de pesquisa para locatários de avaliação de 7 a 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="e5cd7-135">Essa alteração está sendo controlada como parte do item de roteiro nº 70544 e está em uma fase de lançamento.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="e5cd7-136">Use o menu **Exibir** para alterar quais informações são exibidas.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="e5cd7-137">As dicas de ferramentas ajudam a determinar qual exibição usar.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-137">Tooltips help you determine which view to use.</span></span>

![Menu De exibição do Explorador de Ameaças](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="e5cd7-139">Depois de selecionar um exibição, você pode aplicar filtros e configurar consultas para realizar mais análises.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="e5cd7-140">As seções a seguir fornecem uma breve visão geral das várias exibições disponíveis no Explorer (ou detecções em tempo real).</span><span class="sxs-lookup"><span data-stu-id="e5cd7-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="e5cd7-141">Email > Malware</span><span class="sxs-lookup"><span data-stu-id="e5cd7-141">Email > Malware</span></span>

<span data-ttu-id="e5cd7-142">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \> **Malware de** \> **Email**.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="e5cd7-143">Esta exibição mostra informações sobre mensagens de email identificadas como contendo malware.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Exibir dados sobre email identificados como malware](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="e5cd7-145">Clique **em Remetente** para abrir sua lista de opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="e5cd7-146">Use essa lista para exibir dados por remetente, destinatários, domínio do remetente, assunto, tecnologia de detecção, status de proteção e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="e5cd7-147">Por exemplo, para ver quais ações foram tomadas em mensagens de email detectadas, escolha **Status de proteção** na lista.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="e5cd7-148">Selecione uma opção e clique no botão Atualizar para aplicar esse filtro ao relatório.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opções de Status de Proteção contra Ameaças para o Explorador de Ameaças](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="e5cd7-150">Abaixo do gráfico, confira mais detalhes sobre mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="e5cd7-151">Quando você seleciona um item na lista, um painel de sobrevoo é aberto, onde você pode saber mais sobre o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Explorador de Ameaças com o flyout aberto](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="e5cd7-153">Email > Phish</span><span class="sxs-lookup"><span data-stu-id="e5cd7-153">Email > Phish</span></span>

<span data-ttu-id="e5cd7-154">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \> **Phishing de** \> **Email.**</span><span class="sxs-lookup"><span data-stu-id="e5cd7-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="e5cd7-155">Esta exibição mostra mensagens de email identificadas como tentativas de phishing.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-155">This view shows email messages identified as phishing attempts.</span></span>

![Exibir dados sobre email identificados como tentativas de phishing](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="e5cd7-157">Clique **em Remetente** para abrir sua lista de opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="e5cd7-158">Use essa lista para exibir dados por remetente, destinatários, domínio do remetente, IP do remetente, domínio de URL, veredito de clique e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="e5cd7-159">Por exemplo, para ver quais ações foram tomadas quando as pessoas clicaram  em URLs identificadas como tentativas de phishing, escolha Clique em Veredito na lista, selecione uma ou mais opções e clique no botão Atualizar.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Clique em opções de veredito para o relatório phishing](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="e5cd7-161">Abaixo do gráfico, confira mais detalhes sobre mensagens específicas, cliques de URL, URLs e origem do email.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URLs detectadas como phishing em mensagens de email](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="e5cd7-163">Quando você seleciona um item na lista, como uma URL detectada, um painel de sobrevoo é aberto, onde você pode saber mais sobre o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Detalhes sobre uma URL detectada](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="e5cd7-165">Envios > email</span><span class="sxs-lookup"><span data-stu-id="e5cd7-165">Email > Submissions</span></span>

<span data-ttu-id="e5cd7-166">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \>  \> **Envios de Email**.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="e5cd7-167">Esta exibição mostra emails que os usuários relataram como lixo eletrônico, não lixo eletrônico ou email de phishing.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Mensagens de email relatadas por usuários](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="e5cd7-169">Clique **em Remetente** para abrir sua lista de opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="e5cd7-170">Use essa lista para exibir informações por remetente, destinatários, tipo de relatório (a determinação do usuário de que o email era lixo eletrônico, não lixo eletrônico ou phishing) e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="e5cd7-171">Por exemplo, para exibir informações sobre mensagens de email relatadas como tentativas de phishing, clique em **Tipo** de Relatório do Remetente, selecione Phish e clique no \> botão Atualizar. </span><span class="sxs-lookup"><span data-stu-id="e5cd7-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish selecionado para filtro Tipo de Relatório](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="e5cd7-173">Abaixo do gráfico, confira mais detalhes sobre mensagens de email específicas, como linha de assunto, endereço IP do remetente, o usuário que relatou a mensagem como lixo eletrônico, não lixo eletrônico ou phishing e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Mensagens relatadas como tentativas de phishing](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="e5cd7-175">Selecione um item na lista para exibir detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="e5cd7-176">Email > Todos os emails</span><span class="sxs-lookup"><span data-stu-id="e5cd7-176">Email > All email</span></span>

<span data-ttu-id="e5cd7-177">Para exibir esse relatório, no Explorer, escolha **Exibir** \> **Email** \> **Todos os emails**.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="e5cd7-178">Esse modo de exibição mostra uma exibição all-up da atividade de email, incluindo emails identificados como mal-intencionados devido a phishing ou malware, bem como todos os emails não mal-intencionados (email normal, spam e email em massa).</span><span class="sxs-lookup"><span data-stu-id="e5cd7-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="e5cd7-179">Se você receber um erro que leia **Dados** demais para exibição, adicione um filtro e, se necessário, reduza o intervalo de datas que você está exibindo.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="e5cd7-180">Para aplicar um filtro, escolha **Remetente**, selecione um item na lista e clique no botão Atualizar.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="e5cd7-181">No nosso exemplo, nós utilizamos a **tecnologia de detecção** como um filtro (há várias opções disponíveis).</span><span class="sxs-lookup"><span data-stu-id="e5cd7-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="e5cd7-182">Exibir informações por remetente, domínio do remetente, destinatários, assunto, nome do arquivo de anexo, família de malware, status de proteção (ações realizadas pelos recursos e políticas de proteção contra ameaças no Office 365), tecnologia de detecção (como o malware foi detectado) e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Exibir dados sobre o email detectado pela tecnologia de detecção](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="e5cd7-184">Abaixo do gráfico, confira mais detalhes sobre mensagens de email específicas, como linha de assunto, destinatário, remetente, status e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="e5cd7-185">Malware > conteúdo</span><span class="sxs-lookup"><span data-stu-id="e5cd7-185">Content > Malware</span></span>

<span data-ttu-id="e5cd7-186">Para exibir este relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \> **Malware de** \> **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="e5cd7-187">Esta exibição mostra arquivos identificados como mal-intencionados pelo [Microsoft Defender para Office 365 no SharePoint Online, No OneDrive for Business e no Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e5cd7-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="e5cd7-188">Exibir informações por família de malware, tecnologia de detecção (como o malware foi detectado) e carga de trabalho (OneDrive, SharePoint ou Teams).</span><span class="sxs-lookup"><span data-stu-id="e5cd7-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Exibir dados sobre malware detectado](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="e5cd7-190">Abaixo do gráfico, confira mais detalhes sobre arquivos específicos, como nome do arquivo de anexo, carga de trabalho, tamanho do arquivo, quem modificou o arquivo pela última vez e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="e5cd7-191">Recursos de clique para filtrar</span><span class="sxs-lookup"><span data-stu-id="e5cd7-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="e5cd7-192">Com o Explorer (e detecções em tempo real), você pode aplicar um filtro em um clique.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="e5cd7-193">Clique em um item na legenda e esse item se tornará um filtro para o relatório.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="e5cd7-194">Por exemplo, suponhamos que estamos olhando para o exibição Malware no Explorer:</span><span class="sxs-lookup"><span data-stu-id="e5cd7-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Vá para o Explorador de gerenciamento de \> ameaças](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="e5cd7-196">Clicar em **Detonação ATP** neste gráfico resulta em uma exibição como esta:</span><span class="sxs-lookup"><span data-stu-id="e5cd7-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer filtrado para exibir apenas os resultados de Detonação do Defender para Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="e5cd7-198">Neste ponto de vista, agora estamos procurando dados para arquivos que foram detonados por [Anexos Seguros.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="e5cd7-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="e5cd7-199">Abaixo do gráfico, podemos ver detalhes sobre mensagens de email específicas que tinham anexos detectados por Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Detalhes específicos sobre mensagens de email com anexos detectados](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="e5cd7-201">Selecionar um ou mais itens ativa o menu **Ações,** que oferece várias opções das quais escolher os itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Selecionar um item ativa o menu Ações](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="e5cd7-203">A capacidade de filtrar em um clique e navegar para detalhes específicos pode economizar muito tempo na investigação de ameaças.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="e5cd7-204">Consultas e filtros</span><span class="sxs-lookup"><span data-stu-id="e5cd7-204">Queries and filters</span></span>

<span data-ttu-id="e5cd7-205">O Explorer (bem como o relatório de detecções em tempo real) tem vários filtros poderosos e recursos de consulta que permitem detalhar detalhes, como usuários principais direcionados, famílias de malware principais, tecnologia de detecção e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="e5cd7-206">Cada tipo de relatório oferece várias maneiras de exibir e explorar dados.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5cd7-207">Não use caracteres curinga, como um asterisco ou um ponto de interrogação, na barra de consulta do Explorer (ou detecções em tempo real).</span><span class="sxs-lookup"><span data-stu-id="e5cd7-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="e5cd7-208">Quando você pesquisa no campo **Assunto** para mensagens de email, o Explorer (ou detecções em tempo real) executará correspondência parcial e gerará resultados semelhantes a uma pesquisa de curinga.</span><span class="sxs-lookup"><span data-stu-id="e5cd7-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
