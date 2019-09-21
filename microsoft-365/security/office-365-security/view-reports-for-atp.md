---
title: Exibir relatórios para a proteção avançada contra ameaças do Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
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
description: Saiba como encontrar e usar relatórios para a proteção avançada contra ameaças do Office 365 no &amp; centro de conformidade de segurança.
ms.openlocfilehash: d5f0958d199684a9d6ca6bfe4ed01c0ab9102a2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073911"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="40f80-103">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="40f80-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="40f80-104">Se sua organização tiver a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP) e você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-the-atp-reports), poderá usar vários relatórios de ATP &amp; no centro de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="40f80-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="40f80-105">(Vá para o **painel**de **relatórios** \> .)</span><span class="sxs-lookup"><span data-stu-id="40f80-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![O painel &amp; do centro de conformidade de segurança pode ajudá-lo a ver onde a proteção avançada contra ameaças está funcionando](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="40f80-107">Os relatórios ATP incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="40f80-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="40f80-108">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="40f80-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="40f80-109">Relatório de tipos de arquivo ATP</span><span class="sxs-lookup"><span data-stu-id="40f80-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="40f80-110">Relatório de disposição de mensagens ATP</span><span class="sxs-lookup"><span data-stu-id="40f80-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="40f80-111">[detecções ou Explorer em tempo real](threat-explorer.md) (dependendo se você tem o plano ATP 1 ou 2 do Office 365)</span><span class="sxs-lookup"><span data-stu-id="40f80-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="40f80-112">... [e muito mais](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="40f80-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="40f80-113">Leia este artigo para obter uma visão geral dos relatórios ATP e como usá-los.</span><span class="sxs-lookup"><span data-stu-id="40f80-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="40f80-114">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="40f80-114">Threat Protection Status report</span></span>

<span data-ttu-id="40f80-115">O relatório de **status de proteção contra ameaças** é um modo de exibição único que reúne informações sobre conteúdo mal-intencionado e email mal-intencionado detectado e bloqueado pela [proteção do Exchange Online](exchange-online-protection-overview.md) (EOP) e pelo [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="40f80-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="40f80-116">Este relatório é útil para exibir detecções ao longo do tempo (até 90 dias) e permite que os administradores de segurança identifiquem tendências ou determinem se as políticas precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="40f80-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="40f80-117">O relatório de status de proteção contra ameaças fornece uma contagem agregada de mensagens de email exclusivas com conteúdo mal-intencionado, como arquivos ou endereços de sites (URLs) que foram bloqueados pelo Mecanismo Antimalware, [exclusão automática de zero horas (zap)](zero-hour-auto-purge.md)e recursos ATP como [Links seguros de ATP](atp-safe-links.md), [anexos seguros de ATP](atp-safe-attachments.md)e recursos de anti-phishing da [ATP](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="40f80-117">The Threat Protection Status report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="40f80-118">Um relatório de status de proteção contra ameaças está disponível para clientes que tenham o [Office 365 ATP](office-365-atp.md) ou o [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); no entanto, as informações exibidas no relatório de status de proteção contra ameaças para clientes ATP provavelmente conterão dados diferentes do que os clientes do EOP podem ver.</span><span class="sxs-lookup"><span data-stu-id="40f80-118">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="40f80-119">Por exemplo, o relatório de status de proteção contra ameaças para clientes ATP conterá informações sobre [arquivos mal-intencionados detectados no SharePoint Online, no onedrive ou no Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="40f80-119">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="40f80-120">Essas informações são específicas para a ATP, para que os clientes que tenham o EOP, mas não a ATP, não vejam esses detalhes no relatório de status de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="40f80-120">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="40f80-121">Para exibir o relatório de status de proteção contra ameaças, no [centro de conformidade de &amp; segurança](https://protection.office.com), vá para o **painel** \> **relatórios** \> **status de proteção contra ameaças**.</span><span class="sxs-lookup"><span data-stu-id="40f80-121">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Relatório de status de proteção contra ameaças ATP](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="40f80-123">Para obter o status detalhado de um dia, passe o mouse sobre o gráfico.</span><span class="sxs-lookup"><span data-stu-id="40f80-123">To get detailed status for a day, hover over the graph.</span></span>
  
![Dados de status de proteção de ameaças ATP por um dia](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="40f80-125">Por padrão, o relatório de status de proteção contra ameaças mostra os dados dos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="40f80-125">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="40f80-126">No entanto, você pode escolher **filtros** e alterar o intervalo de datas para exibir dados de até 90 dias.</span><span class="sxs-lookup"><span data-stu-id="40f80-126">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="40f80-127">(Se estiver usando uma assinatura de avaliação, você poderá estar limitado a 30 dias de dados.)</span><span class="sxs-lookup"><span data-stu-id="40f80-127">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Filtros de status de proteção contra ameaças ATP](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="40f80-129">Você também pode usar o menu **exibir dados por** para alterar quais informações são exibidas no relatório.</span><span class="sxs-lookup"><span data-stu-id="40f80-129">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opções de exibição do relatório de status de proteção contra ameaças ATP](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="40f80-131">Relatório de tipos de arquivo ATP</span><span class="sxs-lookup"><span data-stu-id="40f80-131">ATP File Types report</span></span>

<span data-ttu-id="40f80-132">O relatório de **tipos de arquivo ATP** mostra o tipo de arquivos detectados como mal-intencionados por [anexos seguros de ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="40f80-132">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="40f80-133">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para **tipos de arquivos ATP**de **painel** \> de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="40f80-133">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Relatório de tipos de arquivo ATP](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="40f80-135">Ao passar o mouse sobre um determinado dia, você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros de ATP](atp-safe-attachments.md) e [proteção &amp; Antimalware anti-spam no Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="40f80-135">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Dados de relatório de tipos de arquivo ATP por um dia](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="40f80-137">Relatório de disposição de mensagens ATP</span><span class="sxs-lookup"><span data-stu-id="40f80-137">ATP Message Disposition report</span></span>

<span data-ttu-id="40f80-138">O relatório de **disposição de mensagens ATP** mostra as ações que foram tomadas para mensagens de email que foram detectadas como tendo conteúdo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="40f80-138">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="40f80-139">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para painel de **mensagens ATP**de **painel** \> de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="40f80-139">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Relatório de disposição de mensagens ATP](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="40f80-141">Ao passar o mouse sobre uma barra no gráfico, você pode ver quais ações foram executadas para o email detectado nesse dia.</span><span class="sxs-lookup"><span data-stu-id="40f80-141">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Dados de relatório de disposição de mensagens ATP por dia](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="40f80-143">Relatórios adicionais para exibir</span><span class="sxs-lookup"><span data-stu-id="40f80-143">Additional reports to view</span></span>

<span data-ttu-id="40f80-144">Além dos relatórios ATP descritos neste artigo, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="40f80-144">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="40f80-145">Relatório (s)</span><span class="sxs-lookup"><span data-stu-id="40f80-145">Report(s)</span></span>  |<span data-ttu-id="40f80-146">Detalhes</span><span class="sxs-lookup"><span data-stu-id="40f80-146">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="40f80-147">As detecções do **Explorer** ou **em tempo real** (Office 365 ATP Plan 2 clientes têm Explorer; O Office 365 ATP Plan 1 clientes têm detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="40f80-147">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="40f80-148">Explorador de ameaças (e detecções em tempo real)</span><span class="sxs-lookup"><span data-stu-id="40f80-148">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="40f80-149">**Relatórios de segurança de email**, como um relatório superior de remetentes e destinatários, um relatório de email de falsificação e um relatório de detecções de spam.</span><span class="sxs-lookup"><span data-stu-id="40f80-149">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="40f80-150">Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="40f80-150">View email security reports in the Security &amp; Compliance Center</span></span>](../../compliance/view-email-security-reports.md)        |
|<span data-ttu-id="40f80-151">**Rastreamento de URL de links seguros de ATP** (Esse é um relatório que você gera usando o PowerShell.) Este relatório mostra os resultados das ações de links seguros de ATP nos últimos sete (7) dias.</span><span class="sxs-lookup"><span data-stu-id="40f80-151">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="40f80-152">Referência do cmdlet Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="40f80-152">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|<span data-ttu-id="40f80-153">**Resultados de EOP e ATP** (Este é um relatório personalizado que você gera usando o PowerShell).</span><span class="sxs-lookup"><span data-stu-id="40f80-153">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="40f80-154">Este relatório contém informações, como o domínio, a data, o tipo de evento, a direção, a ação e a contagem de mensagens.</span><span class="sxs-lookup"><span data-stu-id="40f80-154">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="40f80-155">Referência do cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="40f80-155">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="40f80-156">**Detecções de EOP e ATP** (Este é um relatório personalizado que você gera usando o PowerShell).</span><span class="sxs-lookup"><span data-stu-id="40f80-156">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="40f80-157">Este relatório contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras ameaças potenciais em emails ou arquivos.</span><span class="sxs-lookup"><span data-stu-id="40f80-157">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="40f80-158">Referência do cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="40f80-158">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="40f80-159">Quais permissões são necessárias para exibir os relatórios ATP?</span><span class="sxs-lookup"><span data-stu-id="40f80-159">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="40f80-160">Para exibir e usar os relatórios descritos neste artigo, **você deve ter uma função apropriada atribuída para o centro de conformidade de segurança &amp; e o centro de administração do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="40f80-160">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="40f80-161">Para o centro &amp; de conformidade de segurança, você deve ter uma das seguintes funções atribuídas:</span><span class="sxs-lookup"><span data-stu-id="40f80-161">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="40f80-162">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="40f80-162">Organization Management</span></span>
    - <span data-ttu-id="40f80-163">Administrador de segurança (pode ser atribuído no centro[https://aad.portal.azure.com](https://aad.portal.azure.com)de administração do Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="40f80-163">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="40f80-164">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="40f80-164">Security Reader</span></span>

- <span data-ttu-id="40f80-165">Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="40f80-165">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="40f80-166">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="40f80-166">Organization Management</span></span>
    - <span data-ttu-id="40f80-167">Gerenciamento de Organização Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="40f80-167">View-only Organization Management</span></span>
    - <span data-ttu-id="40f80-168">Função de Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="40f80-168">View-Only Recipients role</span></span>
    - <span data-ttu-id="40f80-169">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="40f80-169">Compliance Management</span></span>

<span data-ttu-id="40f80-170">Para saber mais, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="40f80-170">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="40f80-171">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="40f80-171">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="40f80-172">Permissões de recursos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="40f80-172">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="40f80-173">E se os relatórios não estiverem mostrando dados?</span><span class="sxs-lookup"><span data-stu-id="40f80-173">What if the reports aren't showing data?</span></span>

<span data-ttu-id="40f80-174">Se você não estiver vendo dados em seus relatórios ATP, verifique se as políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="40f80-174">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="40f80-175">Sua organização deve ter [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) e [políticas de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md) definidos para que a proteção ATP esteja funcionando.</span><span class="sxs-lookup"><span data-stu-id="40f80-175">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="40f80-176">Consulte também [anti-spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="40f80-176">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="40f80-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="40f80-177">Related topics</span></span>

[<span data-ttu-id="40f80-178">Relatórios e insights no centro de conformidade de &amp; segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="40f80-178">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="40f80-179">Criar um cronograma para um relatório no centro de &amp; conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="40f80-179">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="40f80-180">Configurar e baixar um relatório personalizado no centro de conformidade &amp; de segurança</span><span class="sxs-lookup"><span data-stu-id="40f80-180">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

