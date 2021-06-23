---
title: Exibir relatórios do Defender para Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender a encontrar e usar o Defender para Office 365 relatórios disponíveis no portal Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7eab856f22ac1c2282e83897db6e3f93d4d97e6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083507"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="ed3bc-103">Exibir o Defender Office 365 relatórios no portal Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3bc-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ed3bc-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-104">**Applies to**</span></span>
- [<span data-ttu-id="ed3bc-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ed3bc-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ed3bc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3bc-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ed3bc-107">O Microsoft Defender para organizações Office 365 (por exemplo, assinaturas do Microsoft 365 E5 ou o Microsoft Defender para o Plano 1 do Office 365 ou o Microsoft Defender para complementos do Plano 2 do Office 365) contém uma variedade de relatórios relacionados à segurança.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="ed3bc-108">Se você tiver as permissões [necessárias,](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)poderá exibir esses relatórios no  portal Microsoft 365 Defender indo para Relatórios \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ed3bc-109">Para ir diretamente para a página Relatórios de **colaboração & email,** abra <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="ed3bc-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Página & relatórios de colaboração de email no portal Microsoft 365 Defender email](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="ed3bc-111">Relatórios de segurança de email que não exigem o Defender para Office 365 são descritos em Exibir relatórios de segurança de [email no portal Microsoft 365 Defender .](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="ed3bc-112">Os relatórios relacionados ao fluxo de emails agora estão no centro de administração Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="ed3bc-113">Para obter mais informações sobre esses relatórios, consulte [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="ed3bc-114">Cofre Relatório de tipos de arquivo anexos</span><span class="sxs-lookup"><span data-stu-id="ed3bc-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="ed3bc-115">O Cofre de tipos de arquivo **Attachments** eventualmente desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="ed3bc-116">As mesmas informações estão disponíveis no relatório de [status de proteção contra ameaças.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="ed3bc-117">Cofre Relatório de disposição de mensagens de anexos</span><span class="sxs-lookup"><span data-stu-id="ed3bc-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="ed3bc-118">O Cofre de disposição da mensagem **Attachments** eventualmente desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="ed3bc-119">As mesmas informações estão disponíveis no relatório de [status de proteção contra ameaças.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="ed3bc-120">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="ed3bc-120">Mail latency report</span></span>

<span data-ttu-id="ed3bc-121">O **relatório de latência de email** mostra uma exibição agregada da entrega de email e da latência de detonação experimentadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="ed3bc-122">Os tempos de entrega de email no serviço são afetados por vários fatores, e o tempo de entrega absoluto em segundos geralmente não é um bom indicador de sucesso ou um problema.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="ed3bc-123">Um tempo de entrega lento em um dia pode ser considerado um tempo médio de entrega em outro dia ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="ed3bc-124">Isso tenta qualificar a entrega de mensagens com base em dados estatísticos sobre os tempos de entrega observados de outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="ed3bc-125">O lado do cliente e a latência de rede não estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="ed3bc-126">Para exibir o relatório, abra o [portal Microsoft 365 Defender ,](https://security.microsoft.com)acesse **Relatórios** Email \> **& colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ed3bc-127">Na página **Relatórios de colaboração &** email, encontre Relatório de **latência** de email e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="ed3bc-128">Para ir diretamente para o relatório, abra <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="ed3bc-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Widget de relatório de latência de email na página Relatórios de & de colaboração](../../media/mail-latency-report-widget.png)

<span data-ttu-id="ed3bc-130">Na página **Relatório de latência** de email, as seguintes guias estão disponíveis na página Relatório de **latência de** email:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="ed3bc-131">**Percentil 50**: Este é o meio para os tempos de entrega da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="ed3bc-132">Você pode considerar esse valor como um tempo médio de entrega.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="ed3bc-133">Essa guia é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-133">This tab is selected by default.</span></span>
- <span data-ttu-id="ed3bc-134">**Percentil 90**: Isso indica uma alta latência para entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="ed3bc-135">Apenas 10% das mensagens demoraram mais do que esse valor para ser entregue.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="ed3bc-136">**Percentil 99**: Isso indica a latência mais alta para entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="ed3bc-137">Independentemente da guia selecionada, o gráfico mostra mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="ed3bc-138">**Latência de entrega de email**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="ed3bc-139">**Detonações**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-139">**Detonations**</span></span>

<span data-ttu-id="ed3bc-140">Ao passar o mouse sobre uma categoria no gráfico, você pode ver uma divisão da latência em cada categoria.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Exibição de percentis do 50º percentil do relatório de latência de email](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="ed3bc-142">Se você clicar **em Filtrar**, você poderá filtrar o gráfico e a tabela de detalhes pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="ed3bc-143">**Data (UTC)**: Data **de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ed3bc-144">**Exibição de** mensagem : um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="ed3bc-145">**Todas as mensagens**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-145">**All messages**</span></span>
  - <span data-ttu-id="ed3bc-146">**Mensagens que contêm anexos ou URLs**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="ed3bc-147">**Mensagens detonadas**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-147">**Detonated messages**</span></span>

<span data-ttu-id="ed3bc-148">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ed3bc-149">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ed3bc-150">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-150">**Date (UTC)**</span></span>
- <span data-ttu-id="ed3bc-151">**Percentis**: **50**, **90** ou **99**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="ed3bc-152">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-152">**Message count**</span></span>
- <span data-ttu-id="ed3bc-153">**Latência geral**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ed3bc-154">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="ed3bc-154">Threat protection status report</span></span>

<span data-ttu-id="ed3bc-155">O relatório de **status** de proteção contra ameaças é uma exibição única que reúne informações sobre conteúdo mal-intencionado e emails mal-intencionados detectados e bloqueados pelo [Proteção do Exchange Online](exchange-online-protection-overview.md) (EOP) e o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ed3bc-156">Para obter mais informações, consulte [Relatório de status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="ed3bc-157">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="ed3bc-157">URL threat protection report</span></span>

<span data-ttu-id="ed3bc-158">O **relatório de proteção contra** ameaças de URL fornece exibições de resumo e tendência para ameaças detectadas e ações realizadas em cliques de URL como parte Cofre [Links](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="ed3bc-159">Este relatório não terá os dados de clique de usuários nos quais a política de links Cofre aplicada tem a opção Não rastrear **cliques do** usuário selecionada.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="ed3bc-160">Para exibir o relatório, abra o [portal Microsoft 365 Defender ,](https://security.microsoft.com)acesse **Relatórios** Email \> **& colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ed3bc-161">Na página **Relatórios de colaboração de &** email, encontre a página de proteção de **URL** e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="ed3bc-162">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="ed3bc-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Widget de relatório de proteção de URL na página Relatórios de colaboração & email](../../media/url-protection-report-widget.png)

<span data-ttu-id="ed3bc-164">Os exibições disponíveis na página de relatório de proteção contra ameaças de **URL** são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="ed3bc-165">Este é um relatório *de tendência de proteção*, o que significa que os dados representam tendências em um conjuntos de dados maior.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="ed3bc-166">Como resultado, os dados nos gráficos não estão disponíveis em tempo real aqui, mas os dados na tabela de detalhes são, portanto, você pode ver uma pequena discrepância entre os dois.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="ed3bc-167">Os gráficos são atualizados uma vez a cada quatro horas e contêm dados dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="ed3bc-168">Exibir dados por ação de proteção de clique em URL</span><span class="sxs-lookup"><span data-stu-id="ed3bc-168">View data by URL click protection action</span></span>

![Exibição de ação de proteção de clique em URL no relatório de proteção contra ameaças de URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="ed3bc-170">O **view data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="ed3bc-171">**Permitido**: o usuário teve permissão para navegar até a URL.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="ed3bc-172">**Bloqueado**: o usuário foi impedido de navegar para a URL.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="ed3bc-173">**Bloqueado e clicado por**: O usuário optou por continuar navegando para a URL.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="ed3bc-174">**Clicado durante a verificação**: o usuário clicou no link antes de a verificação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="ed3bc-175">Um clique indica que o usuário clicou na página de bloqueio para o site mal-intencionado (os administradores podem desabilitar o clique em Cofre Políticas de Links).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="ed3bc-176">Se você clicar em **Filtros,** poderá modificar o relatório e a tabela de detalhes selecionando um ou mais dos seguintes valores no sobremenu que aparece:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ed3bc-177">**Data (UTC)**: Data **de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ed3bc-178">**Detecção**:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-178">**Detection**:</span></span>
  - <span data-ttu-id="ed3bc-179">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-179">**Allowed**</span></span>
  - <span data-ttu-id="ed3bc-180">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-180">**Blocked**</span></span>
  - <span data-ttu-id="ed3bc-181">**Bloqueado e clicado por meio**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="ed3bc-182">**Clicado durante a verificação**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="ed3bc-183">**Domínios**: os domínios de URL listados nos resultados do relatório.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="ed3bc-184">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-184">**Recipients**</span></span>

<span data-ttu-id="ed3bc-185">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ed3bc-186">A tabela de detalhes abaixo do gráfico fornece a seguinte exibição quase em tempo real de todos os cliques que aconteceram na organização nos últimos 7 dias:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="ed3bc-187">**Clique em hora**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-187">**Click time**</span></span>
- <span data-ttu-id="ed3bc-188">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-188">**User**</span></span>
- <span data-ttu-id="ed3bc-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-189">**URL**</span></span>
- <span data-ttu-id="ed3bc-190">**Action**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-190">**Action**</span></span>
- <span data-ttu-id="ed3bc-191">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="ed3bc-192">Exibir dados por URL clique por aplicativo</span><span class="sxs-lookup"><span data-stu-id="ed3bc-192">View data by URL click by application</span></span>

![Url clique por exibição de aplicativo no relatório de proteção contra ameaças de URL](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="ed3bc-194">O **view data by URL click by application** view shows the number of URL clicks by apps that support Cofre Links:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="ed3bc-195">**Cliente de email**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-195">**Email client**</span></span>
- <span data-ttu-id="ed3bc-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-196">**PowerPoint**</span></span>
- <span data-ttu-id="ed3bc-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-197">**Word**</span></span>
- <span data-ttu-id="ed3bc-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-198">**Excel**</span></span>
- <span data-ttu-id="ed3bc-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-199">**OneNote**</span></span>
- <span data-ttu-id="ed3bc-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-200">**Visio**</span></span>
- <span data-ttu-id="ed3bc-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-201">**Teams**</span></span>
- <span data-ttu-id="ed3bc-202">**Outros**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-202">**Others**</span></span>

<span data-ttu-id="ed3bc-203">Se você clicar em **Filtros,** poderá modificar o relatório e a tabela de detalhes selecionando um ou mais dos seguintes valores no sobremenu que aparece:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ed3bc-204">**Data (UTC)**: Data **de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ed3bc-205">**Detecção**: Aplicativos disponíveis no gráfico.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="ed3bc-206">**Domínios**: os domínios de URL listados nos resultados do relatório.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="ed3bc-207">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-207">**Recipients**</span></span>

<span data-ttu-id="ed3bc-208">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ed3bc-209">A tabela de detalhes abaixo do gráfico fornece a seguinte exibição quase em tempo real de todos os cliques que aconteceram na organização nos últimos 7 dias:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="ed3bc-210">**Clique em hora**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-210">**Click time**</span></span>
- <span data-ttu-id="ed3bc-211">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-211">**User**</span></span>
- <span data-ttu-id="ed3bc-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-212">**URL**</span></span>
- <span data-ttu-id="ed3bc-213">**Action**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-213">**Action**</span></span>
- <span data-ttu-id="ed3bc-214">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="ed3bc-215">Relatórios adicionais para exibição</span><span class="sxs-lookup"><span data-stu-id="ed3bc-215">Additional reports to view</span></span>

<span data-ttu-id="ed3bc-216">Além dos relatórios descritos neste artigo, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="ed3bc-217">Relatório</span><span class="sxs-lookup"><span data-stu-id="ed3bc-217">Report</span></span>|<span data-ttu-id="ed3bc-218">Tópico</span><span class="sxs-lookup"><span data-stu-id="ed3bc-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="ed3bc-219">**Explorer** (Microsoft Defender para Office 365 Plano 2) ou detecções em tempo **real** (Microsoft Defender para Office 365 Plano 1)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="ed3bc-220">Explorador de Ameaças (e detecções em tempo real)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="ed3bc-221">**Relatórios de segurança de** email , como o relatório principais remetentes e destinatários, o relatório de email Spoof e o relatório de detecções de spam.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="ed3bc-222">Exibir relatórios de segurança de email no portal Microsoft 365 Defender email</span><span class="sxs-lookup"><span data-stu-id="ed3bc-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="ed3bc-223">**Relatórios de fluxo de** emails , como o relatório de encaminhamento, o relatório de status de fluxo de emails e o relatório de principais destinatários e destinatários.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="ed3bc-224">Relatórios de fluxo de emails no novo Exchange de administração</span><span class="sxs-lookup"><span data-stu-id="ed3bc-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="ed3bc-225">**Rastreamento de URL para Cofre Links** (somente PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="ed3bc-226">A saída deste cmdlet mostra os resultados das ações Cofre Links nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="ed3bc-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="ed3bc-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="ed3bc-228">**Resultados do tráfego de email para o EOP e o Microsoft Defender para Office 365** (somente o PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="ed3bc-229">A saída deste cmdlet contém informações sobre Domínio, Data, Tipo de Evento, Direção, Ação e Contagem de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="ed3bc-230">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="ed3bc-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="ed3bc-231">**Relatórios de detalhes de email do EOP e do Defender para Office 365 detecções** (somente do PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="ed3bc-232">A saída deste cmdlet contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras possíveis ameaças em emails ou arquivos.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="ed3bc-233">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="ed3bc-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="ed3bc-234">Quais permissões são necessárias para exibir o Defender para Office 365 relatórios?</span><span class="sxs-lookup"><span data-stu-id="ed3bc-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="ed3bc-235">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de função no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="ed3bc-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ed3bc-236">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-236">**Organization Management**</span></span>
- <span data-ttu-id="ed3bc-237">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-237">**Security Administrator**</span></span>
- <span data-ttu-id="ed3bc-238">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-238">**Security Reader**</span></span>
- <span data-ttu-id="ed3bc-239">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-239">**Global Reader**</span></span>

<span data-ttu-id="ed3bc-240">Para obter mais informações, veja [Permissões no portal do Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="ed3bc-241">**Observação**: adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ed3bc-242">Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ed3bc-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ed3bc-243">E se os relatórios não mostrarem dados?</span><span class="sxs-lookup"><span data-stu-id="ed3bc-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ed3bc-244">Se você não estiver vendo dados em seus relatórios do Defender Office 365, verifique se suas políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ed3bc-245">Sua organização deve ter Cofre políticas de [Links](set-up-safe-links-policies.md) e Cofre [De anexos definidas](set-up-safe-attachments-policies.md) para que o Defender Office 365 proteção seja in-locar.</span><span class="sxs-lookup"><span data-stu-id="ed3bc-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="ed3bc-246">Consulte também [Proteção anti-spam e anti-malware.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed3bc-247">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ed3bc-247">Related topics</span></span>

[<span data-ttu-id="ed3bc-248">Relatórios inteligentes e percepções no portal Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="ed3bc-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ed3bc-249">Permissões de função (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed3bc-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
