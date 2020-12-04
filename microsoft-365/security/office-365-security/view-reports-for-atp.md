---
title: Exibir relatórios do defender for Office 365 no painel relatórios
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Encontre e use relatórios do Microsoft defender para Office 365 no centro de conformidade e segurança &.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a237049c9ebbccf1c01feeb21129496e16d437b2
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572484"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="53620-103">Exibir relatórios do defender for Office 365 no painel relatórios no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="53620-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="53620-104">As organizações do Microsoft defender for Office 365 (por exemplo, assinaturas do Microsoft 365 E5 ou Microsoft defender para Office 365 plano 1 ou Microsoft defender para Office 365 plano 2) contêm uma variedade de relatórios relacionados à segurança.</span><span class="sxs-lookup"><span data-stu-id="53620-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="53620-105">Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), poderá exibir esses relatórios no centro de conformidade & de segurança acessando **Reports** o \> **painel** relatórios.</span><span class="sxs-lookup"><span data-stu-id="53620-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="53620-106">Para ir diretamente para o painel relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="53620-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![O painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="53620-108">Relatório de tipos de arquivo do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="53620-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="53620-109">O relatório de **relatórios de tipos de arquivo do defender for Office 365** mostra o tipo de arquivos detectados como mal-intencionados por [anexos seguros](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="53620-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="53620-110">O modo de exibição de agregação do relatório permite 90 dias de filtragem, enquanto o modo de exibição de detalhes permite apenas 10 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="53620-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="53620-111">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **defender para tipos de arquivo do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="53620-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="53620-112">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="53620-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![O widget tipos de arquivo do defender for Office 365 no painel relatórios](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="53620-114">As informações neste relatório também estão disponíveis no relatório de [disposição de mensagens do defender for Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="53620-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="53620-115">Exibição de relatório para o relatório de tipos de arquivo do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="53620-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="53620-116">Os seguintes modos de exibição estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="53620-116">The following views are available:</span></span>

- <span data-ttu-id="53620-117">**Exibir dados por: arquivo**: o gráfico contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="53620-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="53620-118">**Anexos mal-intencionados do Excel**</span><span class="sxs-lookup"><span data-stu-id="53620-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="53620-119">**Anexos de flash mal-intencionados**</span><span class="sxs-lookup"><span data-stu-id="53620-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="53620-120">**Anexos PDF mal-intencionados**</span><span class="sxs-lookup"><span data-stu-id="53620-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="53620-121">**Anexos mal-intencionados do PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="53620-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="53620-122">**URLs mal-intencionadas**</span><span class="sxs-lookup"><span data-stu-id="53620-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="53620-123">**Anexos de palavras maliciosas**</span><span class="sxs-lookup"><span data-stu-id="53620-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="53620-124">**Anexos executáveis maliciosos**</span><span class="sxs-lookup"><span data-stu-id="53620-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="53620-125">**Outros**</span><span class="sxs-lookup"><span data-stu-id="53620-125">**Others**</span></span>

  <span data-ttu-id="53620-126">Ao passar o mouse sobre um determinado dia (ponto de dados), você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros](atp-safe-attachments.md) e [proteção Antimalware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="53620-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Exibição de arquivo no relatório de tipos de arquivo do defender for Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="53620-128">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-129">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-130">Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.</span><span class="sxs-lookup"><span data-stu-id="53620-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="53620-131">**Exibir dados por: Message**: o gráfico contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="53620-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="53620-132">**Bloquear acesso**</span><span class="sxs-lookup"><span data-stu-id="53620-132">**Block access**</span></span>
  - <span data-ttu-id="53620-133">**Mensagens substituídas**</span><span class="sxs-lookup"><span data-stu-id="53620-133">**Messages replaced**</span></span>
  - <span data-ttu-id="53620-134">**Mensagens monitoradas**</span><span class="sxs-lookup"><span data-stu-id="53620-134">**Messages monitored**</span></span>
  - <span data-ttu-id="53620-135">**Substituído por entrega de emails dinâmicas**: para obter mais informações, consulte [entrega dinâmica em políticas de anexos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="53620-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Exibição de mensagens no relatório de tipos de arquivo do defender for Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="53620-137">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-138">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-139">Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .</span><span class="sxs-lookup"><span data-stu-id="53620-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="53620-140">Exibição da tabela de detalhes para o relatório de tipos de arquivo do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="53620-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="53620-141">Se você clicar em **Exibir tabela de detalhes**, o relatório fornecerá uma visão quase em tempo real de todos os cliques que acontecerem na organização pelos últimos 10 dias.</span><span class="sxs-lookup"><span data-stu-id="53620-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="53620-142">As informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="53620-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="53620-143">**Exibir dados por: arquivo**:</span><span class="sxs-lookup"><span data-stu-id="53620-143">**View data by: File**:</span></span>

  - <span data-ttu-id="53620-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="53620-144">**Date**</span></span>
  - <span data-ttu-id="53620-145">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="53620-145">**Recipient address**</span></span>
  - <span data-ttu-id="53620-146">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="53620-146">**Sender address**</span></span>
  - <span data-ttu-id="53620-147">**ID da mensagem**: disponível no campo de cabeçalho **Message-ID** no cabeçalho da mensagem e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="53620-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="53620-148">Um valor de exemplo é `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="53620-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="53620-149">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="53620-149">**File**</span></span>

  <span data-ttu-id="53620-150">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-151">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-152">Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.</span><span class="sxs-lookup"><span data-stu-id="53620-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="53620-153">**Exibir dados por: mensagem**:</span><span class="sxs-lookup"><span data-stu-id="53620-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="53620-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="53620-154">**Date**</span></span>
  - <span data-ttu-id="53620-155">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="53620-155">**Recipient address**</span></span>
  - <span data-ttu-id="53620-156">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="53620-156">**Sender address**</span></span>
  - <span data-ttu-id="53620-157">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="53620-157">**Message ID**</span></span>
  - <span data-ttu-id="53620-158">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="53620-158">**File**</span></span>
  - <span data-ttu-id="53620-159">**Subject**</span><span class="sxs-lookup"><span data-stu-id="53620-159">**Subject**</span></span>

  <span data-ttu-id="53620-160">Se você clicar em **filtros**, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="53620-161">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-162">Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .</span><span class="sxs-lookup"><span data-stu-id="53620-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="53620-163">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="53620-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="53620-164">Relatório de disposição de mensagens do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="53620-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="53620-165">O relatório de **disposição de mensagens ATP** mostra as ações que foram tomadas para mensagens de email que foram detectadas como tendo conteúdo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="53620-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="53620-166">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **defender para Office 365 disposição de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="53620-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="53620-167">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="53620-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget disposição de mensagens do defender for Office 365 no painel relatórios](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="53620-169">As informações neste relatório também estão disponíveis no relatório de [tipos de arquivo do defender for Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="53620-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="53620-170">Exibição de relatório para o relatório de disposição de mensagens do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="53620-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="53620-171">Os seguintes modos de exibição estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="53620-171">The following views are available:</span></span>

- <span data-ttu-id="53620-172">**Exibir dados por: Message**: o gráfico contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="53620-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="53620-173">**Bloquear acesso**</span><span class="sxs-lookup"><span data-stu-id="53620-173">**Block access**</span></span>
  - <span data-ttu-id="53620-174">**Mensagens substituídas**</span><span class="sxs-lookup"><span data-stu-id="53620-174">**Messages replaced**</span></span>
  - <span data-ttu-id="53620-175">**Mensagens monitoradas**</span><span class="sxs-lookup"><span data-stu-id="53620-175">**Messages monitored**</span></span>
  - <span data-ttu-id="53620-176">**Substituído por entrega de emails dinâmicas**: para obter mais informações, consulte [entrega dinâmica em políticas de anexos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="53620-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Exibição de mensagens no relatório de tipos de arquivo do defender for Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="53620-178">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-179">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-180">Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .</span><span class="sxs-lookup"><span data-stu-id="53620-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="53620-181">**Exibir dados por: arquivo**: o gráfico contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="53620-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="53620-182">**Anexos mal-intencionados do Excel**</span><span class="sxs-lookup"><span data-stu-id="53620-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="53620-183">**Anexos de flash mal-intencionados**</span><span class="sxs-lookup"><span data-stu-id="53620-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="53620-184">**Anexos PDF mal-intencionados**</span><span class="sxs-lookup"><span data-stu-id="53620-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="53620-185">**Anexos mal-intencionados do PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="53620-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="53620-186">**URLs mal-intencionadas**</span><span class="sxs-lookup"><span data-stu-id="53620-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="53620-187">**Anexos de palavras maliciosas**</span><span class="sxs-lookup"><span data-stu-id="53620-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="53620-188">**Anexos executáveis maliciosos**</span><span class="sxs-lookup"><span data-stu-id="53620-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="53620-189">**Outros**</span><span class="sxs-lookup"><span data-stu-id="53620-189">**Others**</span></span>

  <span data-ttu-id="53620-190">Ao passar o mouse sobre um determinado dia (ponto de dados), você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros](atp-safe-attachments.md) e [proteção Antimalware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="53620-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Exibição de arquivo no relatório de tipos de arquivo do defender for Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="53620-192">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-193">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-194">Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.</span><span class="sxs-lookup"><span data-stu-id="53620-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="53620-195">Exibição da tabela de detalhes do relatório de disposição de mensagens do defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="53620-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="53620-196">Se você clicar em **Exibir tabela de detalhes**, o relatório fornecerá uma visão quase em tempo real de todos os cliques que acontecerem na organização pelos últimos 10 dias.</span><span class="sxs-lookup"><span data-stu-id="53620-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="53620-197">As informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="53620-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="53620-198">**Exibir dados por: mensagem**:</span><span class="sxs-lookup"><span data-stu-id="53620-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="53620-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="53620-199">**Date**</span></span>
  - <span data-ttu-id="53620-200">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="53620-200">**Recipient address**</span></span>
  - <span data-ttu-id="53620-201">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="53620-201">**Sender address**</span></span>
  - <span data-ttu-id="53620-202">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="53620-202">**Message ID**</span></span>
  - <span data-ttu-id="53620-203">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="53620-203">**File**</span></span>
  - <span data-ttu-id="53620-204">**Subject**</span><span class="sxs-lookup"><span data-stu-id="53620-204">**Subject**</span></span>

  <span data-ttu-id="53620-205">Se você clicar em **filtros**, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="53620-206">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-207">Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .</span><span class="sxs-lookup"><span data-stu-id="53620-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="53620-208">**Exibir dados por: arquivo**:</span><span class="sxs-lookup"><span data-stu-id="53620-208">**View data by: File**:</span></span>

  - <span data-ttu-id="53620-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="53620-209">**Date**</span></span>
  - <span data-ttu-id="53620-210">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="53620-210">**Recipient address**</span></span>
  - <span data-ttu-id="53620-211">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="53620-211">**Sender address**</span></span>
  - <span data-ttu-id="53620-212">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="53620-212">**Message ID**</span></span>
  - <span data-ttu-id="53620-213">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="53620-213">**File**</span></span>

  <span data-ttu-id="53620-214">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-215">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-216">Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.</span><span class="sxs-lookup"><span data-stu-id="53620-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="53620-217">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="53620-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="53620-218">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="53620-218">Mail latency report</span></span>

<span data-ttu-id="53620-219">O **relatório de latência de email** mostra um modo de exibição de agregação da entrega de email e da latência de acionamento em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53620-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="53620-220">As horas de entrega de email no serviço são afetadas por vários fatores, e o tempo de entrega absoluto, em segundos, geralmente não é um bom indicador de sucesso ou de um problema.</span><span class="sxs-lookup"><span data-stu-id="53620-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="53620-221">Um tempo de entrega lento em um dia pode ser considerado um tempo de entrega médio em outro dia ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="53620-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="53620-222">O **relatório de latência de email** tenta qualificar a entrega de mensagens com base em dados estatísticos sobre as horas de entrega observadas de outras mensagens:</span><span class="sxs-lookup"><span data-stu-id="53620-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="53620-223">**50 º percentil**: Este é o meio para tempos de entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="53620-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="53620-224">Você pode considerar esse valor como um tempo médio de entrega.</span><span class="sxs-lookup"><span data-stu-id="53620-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="53620-225">**90th percentil**: indica uma alta latência para entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="53620-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="53620-226">Apenas 10% das mensagens demorou mais do que esse valor a ser entregue.</span><span class="sxs-lookup"><span data-stu-id="53620-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="53620-227">**99th percentil**: indica a maior latência para entrega de mensagens.</span><span class="sxs-lookup"><span data-stu-id="53620-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="53620-228">A latência do lado do cliente e da rede não estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="53620-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="53620-229">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione relatório de **latência de email**.</span><span class="sxs-lookup"><span data-stu-id="53620-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="53620-230">Para ir diretamente para o relatório, abra <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="53620-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![Widget relatório de latência de email no painel relatórios](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="53620-232">Exibição de relatório para o relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="53620-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="53620-233">Quando você abre o relatório, a guia **50 º percentils** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="53620-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="53620-234">Por padrão, este modo de exibição contém um gráfico que é configurado com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="53620-235">**Data**: os últimos 7 dias</span><span class="sxs-lookup"><span data-stu-id="53620-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="53620-236">**Exibição de mensagem**:</span><span class="sxs-lookup"><span data-stu-id="53620-236">**Message View**:</span></span>
  - <span data-ttu-id="53620-237">Mensagens do destruído</span><span class="sxs-lookup"><span data-stu-id="53620-237">Detonated messages</span></span>

<span data-ttu-id="53620-238">Este gráfico mostra as mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="53620-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="53620-239">**Latência de entrega de email**</span><span class="sxs-lookup"><span data-stu-id="53620-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="53620-240">**Latência acionamento**</span><span class="sxs-lookup"><span data-stu-id="53620-240">**Detonation latency**</span></span>

<span data-ttu-id="53620-241">Ao passar o mouse sobre uma categoria no gráfico, você pode ver uma divisão da latência em cada categoria.</span><span class="sxs-lookup"><span data-stu-id="53620-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Relatório de latência de email](../../media/mail-latency-report.png)

<span data-ttu-id="53620-243">Se você clicar em **filtro** no modo de exibição relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="53620-244">Todas as mensagens</span><span class="sxs-lookup"><span data-stu-id="53620-244">All messages</span></span>
- <span data-ttu-id="53620-245">Mensagens que contêm anexos ou URLs</span><span class="sxs-lookup"><span data-stu-id="53620-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="53620-246">Se você clicar na guia **90th percentils** ou na guia **99th percentil** , os mesmos filtros padrão do modo de exibição de **percentil do 50 º** são usados.</span><span class="sxs-lookup"><span data-stu-id="53620-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="53620-247">Exibição da tabela de detalhes para o relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="53620-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="53620-248">As informações a seguir são mostradas no modo de exibição de tabela de detalhes:</span><span class="sxs-lookup"><span data-stu-id="53620-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="53620-249">**Date**</span><span class="sxs-lookup"><span data-stu-id="53620-249">**Date**</span></span>
- <span data-ttu-id="53620-250">**Percentis**</span><span class="sxs-lookup"><span data-stu-id="53620-250">**Percentiles**</span></span>
- <span data-ttu-id="53620-251">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="53620-251">**Message count**</span></span>
- <span data-ttu-id="53620-252">**Latência geral**</span><span class="sxs-lookup"><span data-stu-id="53620-252">**Overall latency**</span></span>

![Detalhes do relatório de latência de email](../../media/mail-latency-report-details.png)

<span data-ttu-id="53620-254">O acima mostra que, em 14 de novembro, a latência média de todas as mensagens entregues e destruído foi de **108, 33** segundos.</span><span class="sxs-lookup"><span data-stu-id="53620-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="53620-255">A tabela detalhes contém as mesmas informações em cada guia.</span><span class="sxs-lookup"><span data-stu-id="53620-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="53620-256">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="53620-256">Threat protection status report</span></span>

<span data-ttu-id="53620-257">O relatório de **status de proteção contra ameaças** é um modo de exibição único que reúne informações sobre conteúdo mal-intencionado e email mal-intencionado detectado e bloqueado pela [proteção do Exchange Online](exchange-online-protection-overview.md) (EOP) e pelo Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="53620-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="53620-258">Para obter mais informações, consulte [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="53620-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="53620-259">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="53620-259">URL threat protection report</span></span>

<span data-ttu-id="53620-260">O **relatório de proteção de ameaças de URL** fornece as exibições de resumo e tendência para ameaças detectadas e ações tomadas em cliques de URL como parte de [links seguros](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="53620-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="53620-261">Este relatório não terá clique em dados de usuários em que a política de links seguros aplicada tenha a opção **não rastrear os cliques do usuário** selecionada.</span><span class="sxs-lookup"><span data-stu-id="53620-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="53620-262">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione relatório de **proteção de URL**.</span><span class="sxs-lookup"><span data-stu-id="53620-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="53620-263">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="53620-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget relatório de proteção de URL no painel relatórios](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="53620-265">Este é um *relatório de tendências de proteção*, o que significa que os dados representam tendências em um conjunto de dados maior.</span><span class="sxs-lookup"><span data-stu-id="53620-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="53620-266">Como resultado, os dados no modo de exibição de agregação não estão disponíveis em tempo real aqui, mas os dados no modo de exibição de tabela detalhes são, portanto, você pode ver uma pequena discrepância entre as duas exibições.</span><span class="sxs-lookup"><span data-stu-id="53620-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="53620-267">Exibição de relatório para o relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="53620-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="53620-268">O relatório de **proteção contra ameaças de URL** tem duas exibições agregadas que são atualizadas uma vez a cada quatro horas que mostram dados dos últimos 90 dias:</span><span class="sxs-lookup"><span data-stu-id="53620-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="53620-269">**URL clique em ação de proteção**: mostra o número de cliques de URL por usuários na organização e os resultados do clique:</span><span class="sxs-lookup"><span data-stu-id="53620-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="53620-270">**Bloqueado** (o usuário foi impedido de navegar para a URL)</span><span class="sxs-lookup"><span data-stu-id="53620-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="53620-271">**Bloqueado e clicado**</span><span class="sxs-lookup"><span data-stu-id="53620-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="53620-272">**Clicado durante a verificação**</span><span class="sxs-lookup"><span data-stu-id="53620-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="53620-273">Um clique indica que o usuário clicou através da página de bloqueio para o site mal-intencionado (os administradores podem desabilitar o clique em políticas de links seguros).</span><span class="sxs-lookup"><span data-stu-id="53620-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="53620-274">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-275">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-276">O disponível clique em ações de proteção, mais o valor **permitido** (o usuário tem permissão para navegar até a URL).</span><span class="sxs-lookup"><span data-stu-id="53620-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL clique em ação de proteção exibir no relatório de proteção contra ameaças de URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="53620-278">**URL clique por aplicativo**: mostra o número de cliques de URL por aplicativos que dão suporte a links seguros:</span><span class="sxs-lookup"><span data-stu-id="53620-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="53620-279">**Cliente de email**</span><span class="sxs-lookup"><span data-stu-id="53620-279">**Email client**</span></span>
  - <span data-ttu-id="53620-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="53620-280">**PowerPoint**</span></span>
  - <span data-ttu-id="53620-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="53620-281">**Word**</span></span>
  - <span data-ttu-id="53620-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="53620-282">**Excel**</span></span>
  - <span data-ttu-id="53620-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="53620-283">**OneNote**</span></span>
  - <span data-ttu-id="53620-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="53620-284">**Visio**</span></span>
  - <span data-ttu-id="53620-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="53620-285">**Teams**</span></span>
  - <span data-ttu-id="53620-286">**Outros**</span><span class="sxs-lookup"><span data-stu-id="53620-286">**Other**</span></span>

  <span data-ttu-id="53620-287">Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="53620-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="53620-288">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="53620-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="53620-289">Os aplicativos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="53620-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="53620-290">Exibição da tabela de detalhes para o relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="53620-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="53620-291">Se você clicar em **Exibir tabela de detalhes**, o relatório fornecerá uma visão quase em tempo real de todos os cliques que acontecerem na organização pelos últimos 7 dias com os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="53620-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="53620-292">**Horário de clique**</span><span class="sxs-lookup"><span data-stu-id="53620-292">**Click time**</span></span>
- <span data-ttu-id="53620-293">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="53620-293">**User**</span></span>
- <span data-ttu-id="53620-294">**URL**</span><span class="sxs-lookup"><span data-stu-id="53620-294">**URL**</span></span>
- <span data-ttu-id="53620-295">**Ação**</span><span class="sxs-lookup"><span data-stu-id="53620-295">**Action**</span></span>
- <span data-ttu-id="53620-296">**App**</span><span class="sxs-lookup"><span data-stu-id="53620-296">**App**</span></span>

<span data-ttu-id="53620-297">Se você clicar em **filtros** no modo de exibição tabela de detalhes, poderá filtrar pelos mesmos critérios do modo de exibição relatório e também por **domínios** ou **destinatários** separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="53620-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="53620-298">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="53620-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="53620-299">Relatórios adicionais para exibir</span><span class="sxs-lookup"><span data-stu-id="53620-299">Additional reports to view</span></span>

<span data-ttu-id="53620-300">Além dos relatórios descritos neste tópico, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="53620-300">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="53620-301">Relatório</span><span class="sxs-lookup"><span data-stu-id="53620-301">Report</span></span>|<span data-ttu-id="53620-302">Tópico</span><span class="sxs-lookup"><span data-stu-id="53620-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="53620-303">**Explorer** (Microsoft defender para Office 365 plano 2) ou **detecções em tempo real** (microsoft defender para Office 365 plano 1)</span><span class="sxs-lookup"><span data-stu-id="53620-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="53620-304">Explorador de Ameaças (e detecções em tempo real)</span><span class="sxs-lookup"><span data-stu-id="53620-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="53620-305">**Relatórios de segurança de email**, como os principais remetentes e destinatários, o relatório de email de spoof e o relatório de detecções de spam.</span><span class="sxs-lookup"><span data-stu-id="53620-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="53620-306">Exibir relatórios de segurança de email no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="53620-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="53620-307">**Relatórios de fluxo de email**, como o relatório de encaminhamento, o relatório de status do fluxo e o relatório de remetentes e destinatários principais.</span><span class="sxs-lookup"><span data-stu-id="53620-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="53620-308">Exibir relatórios de fluxo de emails no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="53620-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="53620-309">**Rastreamento de URL para links seguros** (somente PowerShell).</span><span class="sxs-lookup"><span data-stu-id="53620-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="53620-310">A saída deste cmdlet mostra os resultados das ações de links seguros nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="53620-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="53620-311">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="53620-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="53620-312">**Resultados de tráfego de email para EOP e Microsoft defender para Office 365** (somente PowerShell).</span><span class="sxs-lookup"><span data-stu-id="53620-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="53620-313">A saída desse cmdlet contém informações sobre o domínio, a data, o tipo de evento, a direção, a ação e a contagem de mensagens.</span><span class="sxs-lookup"><span data-stu-id="53620-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="53620-314">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="53620-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="53620-315">**Relatórios de detalhes de email para detecções do EOP e do defender para Office 365** (somente PowerShell).</span><span class="sxs-lookup"><span data-stu-id="53620-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="53620-316">A saída desse cmdlet contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras ameaças potenciais em emails ou arquivos.</span><span class="sxs-lookup"><span data-stu-id="53620-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="53620-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="53620-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="53620-318">Quais permissões são necessárias para exibir os relatórios do defender for Office 365?</span><span class="sxs-lookup"><span data-stu-id="53620-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="53620-319">Para exibir e usar os relatórios descritos neste tópico, você precisa ser membro de um dos seguintes grupos de função no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="53620-319">In order to view and use the reports described in this topic, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="53620-320">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="53620-320">**Organization Management**</span></span>
- <span data-ttu-id="53620-321">**Administrador de segurança**</span><span class="sxs-lookup"><span data-stu-id="53620-321">**Security Administrator**</span></span>
- <span data-ttu-id="53620-322">**Leitor de segurança**</span><span class="sxs-lookup"><span data-stu-id="53620-322">**Security Reader**</span></span>
- <span data-ttu-id="53620-323">**Leitor global**</span><span class="sxs-lookup"><span data-stu-id="53620-323">**Global Reader**</span></span>

<span data-ttu-id="53620-324">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="53620-324">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="53620-325">**Observação**: a adição de usuários à função do Azure Active Directory correspondente no centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no centro de conformidade _e_ segurança & para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53620-325">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="53620-326">Para obter mais informações, confira [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="53620-326">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="53620-327">E se os relatórios não estiverem mostrando dados?</span><span class="sxs-lookup"><span data-stu-id="53620-327">What if the reports aren't showing data?</span></span>

<span data-ttu-id="53620-328">Se você não estiver vendo dados nos seus relatórios do defender for Office 365, verifique se as políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="53620-328">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="53620-329">Sua organização deve ter [políticas de links seguros](set-up-atp-safe-links-policies.md) e [políticas de anexos seguros](set-up-atp-safe-attachments-policies.md) definidas para que a proteção do defender para Office 365 seja estabelecida.</span><span class="sxs-lookup"><span data-stu-id="53620-329">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="53620-330">Consulte também [anti-spam and Anti-Malware Protection](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="53620-330">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="53620-331">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="53620-331">Related topics</span></span>

[<span data-ttu-id="53620-332">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="53620-332">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="53620-333">Permissões de função (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="53620-333">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
