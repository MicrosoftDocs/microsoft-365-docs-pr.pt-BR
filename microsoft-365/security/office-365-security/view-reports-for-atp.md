---
title: Exibir relatórios para proteção avançada contra ameaças
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Encontre e use relatórios para a proteção avançada contra ameaças do Office 365 no centro de conformidade de segurança &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e6f6e3f2fd5820f280ab47f3ffdde11bd9da72e
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613355"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="4a9c4-103">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="4a9c4-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="4a9c4-104">Se sua organização tiver a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP) e você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-the-atp-reports), poderá usar vários relatórios de ATP no centro de conformidade de segurança &amp; .</span><span class="sxs-lookup"><span data-stu-id="4a9c4-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="4a9c4-105">(Ir para **relatórios** \> **Painel**.)</span><span class="sxs-lookup"><span data-stu-id="4a9c4-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![O painel do centro de conformidade de segurança &amp; pode ajudá-lo a ver onde a proteção avançada contra ameaças está funcionando](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="4a9c4-107">Os relatórios ATP incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4a9c4-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="4a9c4-108">Relatório de Status da Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="4a9c4-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="4a9c4-109">Relatório de Tipos de Arquivo ATP</span><span class="sxs-lookup"><span data-stu-id="4a9c4-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="4a9c4-110">Relatório de Disposição de Mensagem ATP</span><span class="sxs-lookup"><span data-stu-id="4a9c4-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="4a9c4-111">[detecções ou Explorer em tempo real](threat-explorer.md) (dependendo se você tem o plano ATP 1 ou 2 do Office 365)</span><span class="sxs-lookup"><span data-stu-id="4a9c4-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="4a9c4-112">... [e muito mais](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="4a9c4-113">Leia este artigo para obter uma visão geral dos relatórios ATP e como usá-los.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="4a9c4-114">Relatório de Status da Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="4a9c4-114">Threat Protection Status report</span></span>

<span data-ttu-id="4a9c4-115">O relatório de **status de proteção contra ameaças** é um modo de exibição único que reúne informações sobre conteúdo mal-intencionado e email mal-intencionado detectado e bloqueado pela [proteção do Exchange Online](exchange-online-protection-overview.md) (EOP) e pelo [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="4a9c4-116">Este relatório é útil para exibir detecções ao longo do tempo (até 90 dias) e permite que os administradores de segurança identifiquem tendências ou determinem se as políticas precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="4a9c4-117">O relatório fornece uma contagem agregada de mensagens de email exclusivas com conteúdo mal-intencionado, como arquivos ou endereços de sites (URLs) que foram bloqueados pelo Mecanismo Antimalware, [limpeza automática de zero-hora (zap)](zero-hour-auto-purge.md)e recursos de ATP, como [links seguros de ATP](atp-safe-links.md), [anexos seguros de ATP](atp-safe-attachments.md)e [anti-phishing ATP](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="4a9c4-118">Filtros e divisões das informações permitem categorizações mais granulares das informações deste relatório.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="4a9c4-119">Especificamente, há um menu "dividir por" incluído para o phishing de **email** \> **Phish** e os modos de exibição de malware de **email** \> **Malware views**.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="4a9c4-120">Ele dividirá os dados em:</span><span class="sxs-lookup"><span data-stu-id="4a9c4-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="4a9c4-121">Por tipo de detecção</span><span class="sxs-lookup"><span data-stu-id="4a9c4-121">By detection type</span></span>|<span data-ttu-id="4a9c4-122">Qual política ajudou a atrair essas ameaças?</span><span class="sxs-lookup"><span data-stu-id="4a9c4-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="4a9c4-123">Por tecnologia de detecção</span><span class="sxs-lookup"><span data-stu-id="4a9c4-123">By detection technology</span></span>|<span data-ttu-id="4a9c4-124">Qual tecnologia subjacente da Microsoft capturou a ameaça?</span><span class="sxs-lookup"><span data-stu-id="4a9c4-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="4a9c4-125">Por status de entrega</span><span class="sxs-lookup"><span data-stu-id="4a9c4-125">By delivery status</span></span>|<span data-ttu-id="4a9c4-126">O que aconteceu com as mensagens de email detectadas como ameaças?</span><span class="sxs-lookup"><span data-stu-id="4a9c4-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="4a9c4-127">O email > Phish | Os modos de exibição de malware têm detalhamentos granulares para as tecnologias de detecção mostradas, com categorias como *reputação de arquivo gerado por ATP*, *arquivo acionamento*, *URL acionamento*, *antifalsificação: falha de DMARC*, por exemplo, útil para identificar exatamente qual recurso levou sua organização a detectar ameaças.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Proteção contra ameaças relatório de status menu suspenso mostrando ' dividir por '.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="4a9c4-129">Esses modos de exibição oferecem a opção de exportação, por meio de um clique de botão (em phishing de **email** \> **Phish**, malware de **email** \> **Malware**e modos de exibição de malware de **conteúdo** \> **Malware** ).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="4a9c4-130">Os dados agregados exportados para o seu computador podem ser abertos no Excel.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![Este gráfico mostra a exportação como uma opção no menu para o modo de exibição de malware, diretamente entre criar agendamento e relatório de solicitação.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="4a9c4-132">**Observação**: o número máximo de entradas que podem ser exportadas para **phishing** e **Malware** está apenas abaixo de 10000.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-132">**Note**: The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="4a9c4-133">Se você exportar um modo de exibição, somente as entradas 10000 mais recentes serão exportadas.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-133">If you export a view, only the most recent 10000 entries are exported.</span></span>

<span data-ttu-id="4a9c4-134">Os modos de exibição de visão geral e email exibirão informações em horas de processamento, e não em 24 horas (demanda re.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-134">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="4a9c4-135">velocidades maiores aqui foram um sinal claro)!</span><span class="sxs-lookup"><span data-stu-id="4a9c4-135">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="4a9c4-136">Um relatório de status de proteção contra ameaças está disponível para clientes que tenham o [Office 365 ATP](office-365-atp.md) ou o [Exchange Online Protection](exchange-online-protection-overview.md)(EOP); no entanto, as informações exibidas no relatório de status de proteção contra ameaças para clientes ATP provavelmente conterão dados diferentes do que os clientes do EOP podem ver.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-136">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-overview.md)) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="4a9c4-137">Por exemplo, o relatório de status de proteção contra ameaças para clientes ATP conterá informações sobre [arquivos mal-intencionados detectados no SharePoint Online, no onedrive ou no Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-137">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="4a9c4-138">Essas informações são específicas para a ATP, para que os clientes que tenham o EOP, mas não a ATP, não vejam esses detalhes no relatório de status de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-138">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="4a9c4-139">Para exibir o relatório de status de proteção contra ameaças, no [ &amp; centro de conformidade de segurança](https://protection.office.com), vá para o painel **relatórios** \> **Dashboard** \> **status de proteção contra ameaças**.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-139">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![Relatório de status de proteção contra ameaças ATP](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="4a9c4-141">Para obter o status detalhado de um dia, passe o mouse sobre o gráfico.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-141">To get detailed status for a day, hover over the graph.</span></span>

![Dados de status de proteção de ameaças ATP por um dia](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="4a9c4-143">Por padrão, o relatório de status de proteção contra ameaças mostra os dados dos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-143">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="4a9c4-144">No entanto, você pode escolher **filtros** e alterar o intervalo de datas para exibir dados de até 90 dias.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-144">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="4a9c4-145">(Se estiver usando uma assinatura de avaliação, você poderá estar limitado a 30 dias de dados.)</span><span class="sxs-lookup"><span data-stu-id="4a9c4-145">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![Filtros de status de proteção contra ameaças ATP](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="4a9c4-147">Você também pode usar o menu **exibir dados por** para alterar quais informações são exibidas no relatório.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-147">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![Opções de exibição do relatório de status de proteção contra ameaças ATP](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="4a9c4-149">Relatório de status de proteção de URL</span><span class="sxs-lookup"><span data-stu-id="4a9c4-149">URL Protection Status report</span></span>

<span data-ttu-id="4a9c4-150">Este relatório é baseado em dados coletados e ameaças detectadas, por clique (enquanto a maioria dos outros relatórios relacionados a ameaças de email são por dados de mensagem).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-150">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="4a9c4-151">Este relatório foi projetado para mostrar ameaças provenientes de hiperlinks em mensagens de email e documentos, por clique.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-151">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="4a9c4-152">Há dois modos de exibição:</span><span class="sxs-lookup"><span data-stu-id="4a9c4-152">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="4a9c4-153">URL clique em ação de proteção</span><span class="sxs-lookup"><span data-stu-id="4a9c4-153">URL click protection action</span></span>|<span data-ttu-id="4a9c4-154">Confira o número de URLs bloqueadas, bloqueadas, mas substituídas por um clique em um usuário, substituídas por um clique em um usuário, e permitidas.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-154">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="4a9c4-155">URL clique por aplicativo</span><span class="sxs-lookup"><span data-stu-id="4a9c4-155">URL click by application</span></span>|<span data-ttu-id="4a9c4-156">Consulte o aplicativo no qual a URL foi clicada.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-156">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="4a9c4-157">Na tabela detalhes, você poderá ver mais informações sobre o clique em tempo e informações do usuário.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-157">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="4a9c4-158">Por fim, tenha em mente que o relatório de status de proteção de URL mostra a proteção do recurso de links seguros de ATP, para que somente os clientes que tenham habilitados os links seguros de ATP vejam os dados refletidos nesse relatório.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-158">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="4a9c4-159">Este é um *relatório de tendências de proteção*, o que significa que os dados representam tendências em um conjunto de dados maior.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-159">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="4a9c4-160">Como resultado, os dados no modo de exibição de agregação não estão disponíveis em tempo real aqui, mas os dados no modo de exibição de tabela detalhes são, portanto, você pode ver uma pequena discrepância entre as duas exibições.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-160">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="4a9c4-161">Relatório de Tipos de Arquivo ATP</span><span class="sxs-lookup"><span data-stu-id="4a9c4-161">ATP File Types report</span></span>

<span data-ttu-id="4a9c4-162">O relatório de **tipos de arquivo ATP** mostra o tipo de arquivos detectados como mal-intencionados por [anexos seguros de ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-162">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="4a9c4-163">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para tipos de **Reports** \> **Dashboard** \> **arquivos ATP**de painel de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-163">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![Relatório de Tipos de Arquivo ATP](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="4a9c4-165">Ao passar o mouse sobre um determinado dia, você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros de ATP](atp-safe-attachments.md) e [ &amp; proteção Antimalware anti-spam](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-165">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Dados de relatório de tipos de arquivo ATP por um dia](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="4a9c4-167">Relatório de Disposição de Mensagem ATP</span><span class="sxs-lookup"><span data-stu-id="4a9c4-167">ATP Message Disposition report</span></span>

<span data-ttu-id="4a9c4-168">O relatório de **disposição de mensagens ATP** mostra as ações que foram tomadas para mensagens de email que foram detectadas como tendo conteúdo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="4a9c4-169">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para painel de **Reports** \> **Dashboard** \> **mensagens ATP**de painel de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-169">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![Relatório de disposição de mensagens ATP](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="4a9c4-171">Ao passar o mouse sobre uma barra no gráfico, você pode ver quais ações foram executadas para o email detectado nesse dia.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-171">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![Dados de relatório de disposição de mensagens ATP por dia](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="4a9c4-173">Relatórios adicionais para exibir</span><span class="sxs-lookup"><span data-stu-id="4a9c4-173">Additional reports to view</span></span>

<span data-ttu-id="4a9c4-174">Além dos relatórios ATP descritos neste artigo, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="4a9c4-174">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="4a9c4-175">**Relatório (s)**</span><span class="sxs-lookup"><span data-stu-id="4a9c4-175">**Report(s)**</span></span>|<span data-ttu-id="4a9c4-176">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4a9c4-176">**Details**</span></span>|
|<span data-ttu-id="4a9c4-177">**Navegadores** ou **detecções em tempo real**: (os clientes do plano 2 do Office 365 ATP têm o Explorer; O Office 365 ATP Plan 1 clientes têm detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-177">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="4a9c4-178">Explorador de Ameaças (e detecções em tempo real)</span><span class="sxs-lookup"><span data-stu-id="4a9c4-178">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="4a9c4-179">**Relatórios de segurança de email**, como um relatório superior de remetentes e destinatários, um relatório de email de falsificação e um relatório de detecções de spam.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-179">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="4a9c4-180">Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="4a9c4-180">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="4a9c4-181">**Rastreamento de URL de links seguros de ATP**: (este é um relatório que você gera usando o PowerShell.) Este relatório mostra os resultados das ações de links seguros de ATP nos últimos sete (7) dias.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-181">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="4a9c4-182">Referência do cmdlet Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="4a9c4-182">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="4a9c4-183">**Resultados de EOP e ATP**: (este é um relatório personalizado que você gera usando o PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-183">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="4a9c4-184">Este relatório contém informações, como o domínio, a data, o tipo de evento, a direção, a ação e a contagem de mensagens.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-184">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="4a9c4-185">Referência do cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="4a9c4-185">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="4a9c4-186">**Detecções de EOP e ATP**: (este é um relatório personalizado que você gera usando o PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-186">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="4a9c4-187">Este relatório contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras ameaças potenciais em emails ou arquivos.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-187">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="4a9c4-188">Referência do cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="4a9c4-188">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="4a9c4-189">Quais permissões são necessárias para exibir os relatórios ATP?</span><span class="sxs-lookup"><span data-stu-id="4a9c4-189">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="4a9c4-190">Para exibir e usar os relatórios descritos neste artigo, **você deve ter uma função apropriada atribuída para o centro de conformidade de segurança &amp; e o centro de administração do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-190">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="4a9c4-191">Para o centro de conformidade de segurança &amp; , você deve ter uma das seguintes funções atribuídas:</span><span class="sxs-lookup"><span data-stu-id="4a9c4-191">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="4a9c4-192">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="4a9c4-192">Organization Management</span></span>
  - <span data-ttu-id="4a9c4-193">Administrador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="4a9c4-193">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="4a9c4-194">Operador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="4a9c4-194">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="4a9c4-195">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="4a9c4-195">Security Reader</span></span>

- <span data-ttu-id="4a9c4-196">Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="4a9c4-196">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="4a9c4-197">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="4a9c4-197">Organization Management</span></span>
  - <span data-ttu-id="4a9c4-198">Gerenciamento de Organização Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="4a9c4-198">View-only Organization Management</span></span>
  - <span data-ttu-id="4a9c4-199">Função de Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="4a9c4-199">View-Only Recipients role</span></span>
  - <span data-ttu-id="4a9c4-200">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="4a9c4-200">Compliance Management</span></span>

<span data-ttu-id="4a9c4-201">Para saber mais, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4a9c4-201">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="4a9c4-202">Permissões no centro de &amp; conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="4a9c4-202">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="4a9c4-203">Permissões de recursos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4a9c4-203">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4a9c4-204">E se os relatórios não estiverem mostrando dados?</span><span class="sxs-lookup"><span data-stu-id="4a9c4-204">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4a9c4-205">Se você não estiver vendo dados em seus relatórios ATP, verifique se as políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-205">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4a9c4-206">Sua organização deve ter [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) e [políticas de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md) definidos para que a proteção ATP esteja funcionando.</span><span class="sxs-lookup"><span data-stu-id="4a9c4-206">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="4a9c4-207">Consulte também [anti-spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c4-207">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a9c4-208">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4a9c4-208">Related topics</span></span>

[<span data-ttu-id="4a9c4-209">Relatórios e insights no centro de &amp; conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="4a9c4-209">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="4a9c4-210">Permissões de função (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4a9c4-210">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
