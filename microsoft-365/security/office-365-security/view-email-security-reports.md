---
title: Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança, usuários comprometidos, criptografia, status de proteção contra ameaças, detecções de malware, malware superior, detecção de spam, email enviado e recebido, mensagens relatadas pelo usuário, relatórios de leitura, detecção, dados de segurança, informações de segurança
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Saiba como localizar e usar relatórios de segurança de email da sua organização. Relatórios de segurança de email estão disponíveis no &amp; centro de conformidade de segurança.
ms.openlocfilehash: fba10207fe0b7a8e02aa96f9c8513e1e5b2cd61f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634059"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="54fe8-104">Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="54fe8-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="54fe8-105">Vários relatórios estão disponíveis no [centro de conformidade de &amp; segurança](https://protection.office.com) para ajudá-lo a ver como os recursos de segurança de email, como os recursos antispam, Antimalware e de criptografia no Office 365 estão protegendo sua organização.</span><span class="sxs-lookup"><span data-stu-id="54fe8-105">A variety of reports are available in the [Security &amp; Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="54fe8-106">Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de conformidade &amp; de segurança acessando o **painel**de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="54fe8-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![Painel em que você vê como a proteção avançada contra ameaças está funcionando](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="54fe8-108">Os relatórios de segurança de email incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="54fe8-108">Your email security reports include the following:</span></span>
- [<span data-ttu-id="54fe8-109">Relatório de usuários comprometidos (**novo!**)</span><span class="sxs-lookup"><span data-stu-id="54fe8-109">Compromised Users report (**NEW!**)</span></span>](#compromised-users-report-new)
- [<span data-ttu-id="54fe8-110">Relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="54fe8-110">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="54fe8-111">Relatório de Status da Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="54fe8-111">Threat Protection Status report</span></span>](#threat-protection-status-report) 
- [<span data-ttu-id="54fe8-112">Relatório de detecções de malware</span><span class="sxs-lookup"><span data-stu-id="54fe8-112">Malware Detections report</span></span>](#malware-detections-report) 
- [<span data-ttu-id="54fe8-113">Relatório de malware superior</span><span class="sxs-lookup"><span data-stu-id="54fe8-113">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="54fe8-114">Relatório de principais remetentes e destinatários</span><span class="sxs-lookup"><span data-stu-id="54fe8-114">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="54fe8-115">Relatório de detecções falsas</span><span class="sxs-lookup"><span data-stu-id="54fe8-115">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="54fe8-116">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="54fe8-116">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="54fe8-117">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="54fe8-117">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="54fe8-118">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="54fe8-118">User-reported messages report</span></span>](#user-reported-messages-report)


## <a name="compromised-users-report-new"></a><span data-ttu-id="54fe8-119">Relatório de usuários comprometidos (**novo!**)</span><span class="sxs-lookup"><span data-stu-id="54fe8-119">Compromised Users report (**NEW!**)</span></span> 

<span data-ttu-id="54fe8-120">Este relatório, disponível para qualquer pessoa com proteção do Exchange Online, mostra o número de contas de usuário marcadas como usuários suspeitos ou restritos, dados particularmente úteis como contas Insira um dos Estados que indicam que a conta de usuário pode ser problemática ou até mesmo ficasse.</span><span class="sxs-lookup"><span data-stu-id="54fe8-120">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="54fe8-121">Com o uso frequente, o relatório de usuário comprometido pode apontar picos e até mesmo tendências, em contas marcadas em Estados suspeitos ou restritos, fornecendo evidências, pode haver um problema com a segurança e o benefício do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="54fe8-121">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![O relatório de usuários comprometidos como aparece no Office 365.](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="54fe8-123">Relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="54fe8-123">Encryption report</span></span>

<span data-ttu-id="54fe8-124">O **relatório de criptografia** mostra informações sobre as mensagens de email que foram criptografadas, seja por meio das políticas da sua organização ou por meio de controles de usuário final.</span><span class="sxs-lookup"><span data-stu-id="54fe8-124">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="54fe8-125">A equipe de segurança da sua organização pode usar informações neste relatório para identificar padrões e aplicar proativamente ou ajustar políticas para mensagens de email confidenciais.</span><span class="sxs-lookup"><span data-stu-id="54fe8-125">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="54fe8-126">Para exibir esse relatório, no centro de conformidade & de segurança, vá para **relatório de criptografia**de **painel** \> de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="54fe8-126">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![Relatório de criptografia](../../media/encryptionreport-defaultview.png) 

<span data-ttu-id="54fe8-128">Quando o relatório for aberto pela primeira vez, você verá dados sobre os métodos de criptografia usados em mensagens de email dos últimos sete (7) dias.</span><span class="sxs-lookup"><span data-stu-id="54fe8-128">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="54fe8-129">Você pode alterar o intervalo de datas e os detalhes que são exibidos no relatório clicando em **filtros** no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="54fe8-129">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![Filtros de relatório de criptografia](../../media/encryptionreport-filters.png)   

<span data-ttu-id="54fe8-131">Você também pode usar o menu **dividir por** para exibir dados por modelo de criptografia (ou método).</span><span class="sxs-lookup"><span data-stu-id="54fe8-131">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![Método ou modelo de criptografia](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="54fe8-133">E você pode usar o menu **exibir dados por** para alterar o modo de exibição para ver as contagens de mensagens criptografadas para os cinco domínios de destinatários principais.</span><span class="sxs-lookup"><span data-stu-id="54fe8-133">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![Dados de exibição do relatório de criptografia por menu](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="54fe8-135">Com a flexibilidade do novo relatório de criptografia, você pode exibir tendências e tomar as ações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="54fe8-135">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="54fe8-136">Por exemplo, se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="54fe8-136">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="54fe8-137">(Para obter ajuda com isso, consulte [definir regras de fluxo de email para criptografar mensagens de email no Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) Como outro exemplo, se você tiver vários modelos de criptografia disponíveis, mas nenhum estiver usando, você poderá explorar se os usuários precisam de treinamento para esse recurso.</span><span class="sxs-lookup"><span data-stu-id="54fe8-137">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span> 

<span data-ttu-id="54fe8-138">Use este relatório permite que a equipe de segurança e conformidade da sua organização monitore a forma como a criptografia de mensagens está sendo usada e se as ações serão necessárias.</span><span class="sxs-lookup"><span data-stu-id="54fe8-138">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="54fe8-139">Para saber mais sobre criptografia, confira [criptografia de email no Office 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="54fe8-139">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="54fe8-140">Relatório de Status da Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="54fe8-140">Threat Protection Status report</span></span>

<span data-ttu-id="54fe8-141">O relatório de **status de proteção contra ameaças** é um relatório inteligente que mostra emails mal-intencionados que foram detectados e bloqueados pela proteção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="54fe8-141">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="54fe8-142">Este relatório é útil para exibir emails identificados como malware ou uma tentativa de phishing ao longo do tempo (até 90 dias) e permite que administradores de segurança identifiquem tendências ou determinem se as políticas precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="54fe8-142">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="54fe8-143">Um relatório de status de proteção contra ameaças está disponível para clientes que tenham o [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) ou o [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); no entanto, as informações exibidas no relatório de status de proteção contra ameaças para clientes ATP provavelmente conterão dados diferentes do que os clientes do EOP podem ver.</span><span class="sxs-lookup"><span data-stu-id="54fe8-143">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="54fe8-144">Por exemplo, os clientes do EOP podem exibir informações sobre malware detectado no email, mas não informações sobre [arquivos mal-intencionados detectados no SharePoint Online, no onedrive ou no Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), um recurso específico de ATP.</span><span class="sxs-lookup"><span data-stu-id="54fe8-144">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="54fe8-145">([Saiba mais sobre os relatórios de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span><span class="sxs-lookup"><span data-stu-id="54fe8-145">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>
  
<span data-ttu-id="54fe8-146">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para o **painel** \> **relatórios** \> **status de proteção contra ameaças**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Relatório de Status da Proteção contra Ameaças](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="54fe8-148">Quando você abre o relatório de status de proteção contra ameaças pela primeira vez, o relatório mostra os dados dos últimos sete dias por padrão; no entanto, você pode clicar em **filtros** e alterar o intervalo de datas para até 90 dias de detalhes.</span><span class="sxs-lookup"><span data-stu-id="54fe8-148">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="54fe8-149">(Se estiver usando uma assinatura de avaliação, você poderá estar limitado a 30 dias de dados.)</span><span class="sxs-lookup"><span data-stu-id="54fe8-149">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="54fe8-150">Este relatório é útil para ver a eficácia e o impacto dos recursos de [proteção do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)da sua organização e para tendência de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="54fe8-150">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span> 
  
![Filtros de relatório de status de proteção contra ameaças](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="54fe8-152">Você também pode escolher se deseja exibir dados para emails identificados como mal-intencionados, emails identificados como tentativas de phishing ou emails identificados como contendo malware.</span><span class="sxs-lookup"><span data-stu-id="54fe8-152">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Opções de exibição do relatório de status de proteção contra ameaças](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="54fe8-154">Relatório de detecções de malware</span><span class="sxs-lookup"><span data-stu-id="54fe8-154">Malware Detections report</span></span>

<span data-ttu-id="54fe8-155">O relatório de **detecções de malware** mostra quantas mensagens de entrada e saída foram detectadas como contendo malware para sua organização.</span><span class="sxs-lookup"><span data-stu-id="54fe8-155">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="54fe8-156">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para relatórios de **malware**de **painel** \> de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="54fe8-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Exemplo de relatório de detecções de malware](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="54fe8-158">Semelhante a outros relatórios, como o [relatório de status de proteção contra ameaças](#threat-protection-status-report), o relatório exibe dados dos últimos sete dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="54fe8-158">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="54fe8-159">No entanto, você pode escolher **filtros** para alterar o intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="54fe8-159">However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="54fe8-160">Relatório de malware superior</span><span class="sxs-lookup"><span data-stu-id="54fe8-160">Top Malware report</span></span>

<span data-ttu-id="54fe8-161">O relatório de **malware superior** mostra os vários tipos de malware detectados pelo [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span><span class="sxs-lookup"><span data-stu-id="54fe8-161">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span> 
  
<span data-ttu-id="54fe8-162">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para **painel** \> de **relatórios** \> de **malware superior**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![Malware EOP superior](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="54fe8-164">Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="54fe8-164">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="54fe8-165">Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.</span><span class="sxs-lookup"><span data-stu-id="54fe8-165">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Este relatório mostra o malware superior detectado para sua organização](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="54fe8-167">Abaixo do gráfico, você verá uma lista de malware detectado e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="54fe8-167">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="54fe8-168">Relatório de principais remetentes e destinatários</span><span class="sxs-lookup"><span data-stu-id="54fe8-168">Top Senders and Recipients report</span></span>

<span data-ttu-id="54fe8-169">O relatório de **remetentes e destinatários principais** é um gráfico de pizza mostrando seus principais remetentes de email.</span><span class="sxs-lookup"><span data-stu-id="54fe8-169">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="54fe8-170">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para **painel** \> de **relatórios** \> **principais remetentes e destinatários**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Para exibir esse relatório, no centro de &amp; conformidade de segurança, vá para \> painel \> de relatórios principais remetentes e destinatários](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="54fe8-172">Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="54fe8-172">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="54fe8-173">Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.</span><span class="sxs-lookup"><span data-stu-id="54fe8-173">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="54fe8-174">Use a lista **Mostrar dados de** para escolher se deseja exibir dados para os remetentes principais, receptores, destinatários de spam e destinatários de malware.</span><span class="sxs-lookup"><span data-stu-id="54fe8-174">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="54fe8-175">Você também pode ver quem recebeu o malware que foi detectado pela [proteção do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span><span class="sxs-lookup"><span data-stu-id="54fe8-175">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span> 
  
![Use a lista Mostrar dados para exibir informações específicas](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="54fe8-177">Abaixo do gráfico, você verá quem os principais remetentes ou destinatários de emails foram, juntamente com uma contagem de mensagens enviadas ou recebidas pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="54fe8-177">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-detections-report"></a><span data-ttu-id="54fe8-178">Relatório de detecções falsas</span><span class="sxs-lookup"><span data-stu-id="54fe8-178">Spoof Detections report</span></span>

<span data-ttu-id="54fe8-179">O relatório de **detecções falsas** mostra quantas mensagens de email de falsificação foram detectadas, e dessas, quais foram consideradas "boas" (emails falsos realizados por motivos de negócios legítimos).</span><span class="sxs-lookup"><span data-stu-id="54fe8-179">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="54fe8-180">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para relatório de **falsificação**de **painel** \> de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="54fe8-180">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![No centro de &amp; conformidade de segurança, vá para \> o \> painel relatórios email de spoof](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="54fe8-182">Ao passar o mouse sobre um dia no gráfico, você pode ver quantas mensagens de email de falsificação foram recebidas.</span><span class="sxs-lookup"><span data-stu-id="54fe8-182">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="54fe8-183">Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.</span><span class="sxs-lookup"><span data-stu-id="54fe8-183">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="54fe8-184">Para saber mais sobre proteção contra falsificação, confira [proteção contra falsificação no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span><span class="sxs-lookup"><span data-stu-id="54fe8-184">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="54fe8-185">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="54fe8-185">Spam Detections report</span></span>

<span data-ttu-id="54fe8-186">O relatório **detecções de spam** mostra todo o conteúdo de spam bloqueado pelo Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="54fe8-186">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="54fe8-187">As mensagens são contadas por mensagem e não por destinatário.</span><span class="sxs-lookup"><span data-stu-id="54fe8-187">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="54fe8-188">Por exemplo, se uma mensagem de email foi enviada a 100 destinatários em sua organização, ela será contada como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="54fe8-188">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>
  
<span data-ttu-id="54fe8-189">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para relatórios de **spam**de **painel** \> de **relatórios** \> .</span><span class="sxs-lookup"><span data-stu-id="54fe8-189">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Para exibir esse relatório, no centro de &amp; conformidade de segurança, vá para \> painel \> de relatórios EOP detecções de spam](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="54fe8-191">Ao passar o mouse sobre um dia no gráfico, você pode ver quantos itens foram bloqueados naquele dia, bem como os itens são categorizados.</span><span class="sxs-lookup"><span data-stu-id="54fe8-191">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="54fe8-192">Por exemplo, você pode ver quantas mensagens de spam foram filtradas e quantos itens vieram de um endereço IP bloqueado.</span><span class="sxs-lookup"><span data-stu-id="54fe8-192">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="54fe8-193">Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.</span><span class="sxs-lookup"><span data-stu-id="54fe8-193">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![O relatório de detecções de spam informa quantas mensagens de spam foram bloqueadas ou filtradas](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="54fe8-195">Abaixo do gráfico, você verá uma lista de itens de spam que foram detectados.</span><span class="sxs-lookup"><span data-stu-id="54fe8-195">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="54fe8-196">Selecione um item para exibir informações adicionais, como se o item de spam era de entrada ou de saída, sua ID de mensagem e seu destinatário.</span><span class="sxs-lookup"><span data-stu-id="54fe8-196">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="54fe8-197">Para saber mais sobre proteção antispam, confira [proteção antispam de email do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span><span class="sxs-lookup"><span data-stu-id="54fe8-197">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="54fe8-198">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="54fe8-198">Sent and received email report</span></span>

<span data-ttu-id="54fe8-199">O relatório de **email enviado e recebido** é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bom".</span><span class="sxs-lookup"><span data-stu-id="54fe8-199">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="54fe8-200">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para o **painel** \> **relatórios** \> **enviado e recebido emails**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-200">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Para exibir esse relatório, no centro de &amp; conformidade de segurança, vá para \> o \> painel relatórios enviado e recebido email](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="54fe8-202">Ao passar o mouse sobre um dia no gráfico, você pode ver quantas mensagens vieram e como essas mensagens são categorizadas.</span><span class="sxs-lookup"><span data-stu-id="54fe8-202">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="54fe8-203">Por exemplo, você pode ver quantas mensagens foram detectadas como contendo malware e quantas foram identificadas como spam.</span><span class="sxs-lookup"><span data-stu-id="54fe8-203">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="54fe8-204">Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.</span><span class="sxs-lookup"><span data-stu-id="54fe8-204">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="54fe8-205">Você pode usar a lista **dividir por** para exibir informações por tipo ou por direção (entrada e saída).</span><span class="sxs-lookup"><span data-stu-id="54fe8-205">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Use a lista dividir por para exibir informações por tipo ou direção](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="54fe8-207">Abaixo do gráfico, você verá uma lista de categorias de email, como **GoodMail**, **SpamContentFiltered**e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="54fe8-207">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="54fe8-208">Selecione uma categoria para exibir informações adicionais, como ações que foram tomadas para malware e se o email era de entrada ou saída.</span><span class="sxs-lookup"><span data-stu-id="54fe8-208">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Este relatório informa sobre o anti-malware, antispam e outras detecções de mensagens](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="54fe8-210">Para saber mais sobre inteligência de email, consulte [inteligência de fluxo de emails no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="54fe8-210">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>
  
## <a name="user-reported-messages-report"></a><span data-ttu-id="54fe8-211">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="54fe8-211">User-reported messages report</span></span>

<span data-ttu-id="54fe8-212">O relatório de **mensagens relatadas pelo usuário** mostra informações sobre as mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails de boa qualidade usando o [suplemento de mensagem de relatório](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span><span class="sxs-lookup"><span data-stu-id="54fe8-212">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>
  
<span data-ttu-id="54fe8-213">Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, como uma exceção de política de spam ou uma regra de fluxo de email configurada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="54fe8-213">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="54fe8-214">Para exibir detalhes, selecione um item na lista relatórios do usuário e, em seguida, exiba as informações nas guias **Resumo** e **detalhes** .</span><span class="sxs-lookup"><span data-stu-id="54fe8-214">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![O relatório mensagens relatadas pelo usuário mostra as mensagens que os usuários rotularam como lixo eletrônico, não lixo eletrônico ou tentativas de phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="54fe8-216">Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="54fe8-216">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="54fe8-217">Vá para o **painel** \> **Gerenciamento** \> **de ameaças mensagens relatadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-217">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="54fe8-218">Vá para **Gerenciamento** \> de ameaças **revise** \> **mensagens relatadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-218">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![No centro de &amp; conformidade de segurança, escolha revisão \> \> de gerenciamento de ameaças mensagens relatadas pelo usuário](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="54fe8-220">Para que o relatório de mensagens relatadas pelo usuário funcione corretamente, o **log de auditoria deve estar ativado** para o seu ambiente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="54fe8-220">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="54fe8-221">Isso geralmente é feito por alguém que tenha a função de logs de auditoria atribuída no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="54fe8-221">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="54fe8-222">Para obter mais informações, consulte [Ativar ou desativar a pesquisa de log de auditoria do Office 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="54fe8-222">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="54fe8-223">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="54fe8-223">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="54fe8-224">Para exibir e usar os relatórios descritos neste artigo, **você deve ter uma função apropriada atribuída para o centro de conformidade de segurança &amp; e o centro de administração do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="54fe8-224">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="54fe8-225">Para o centro &amp; de conformidade de segurança, você deve ter uma das seguintes funções atribuídas:</span><span class="sxs-lookup"><span data-stu-id="54fe8-225">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="54fe8-226">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="54fe8-226">Organization Management</span></span>
    - <span data-ttu-id="54fe8-227">Administrador de segurança (isso pode ser atribuído no centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()</span><span class="sxs-lookup"><span data-stu-id="54fe8-227">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="54fe8-228">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="54fe8-228">Security Reader</span></span>

- <span data-ttu-id="54fe8-229">Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="54fe8-229">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="54fe8-230">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="54fe8-230">Organization Management</span></span>
    - <span data-ttu-id="54fe8-231">Gerenciamento de Organização Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="54fe8-231">View-only Organization Management</span></span>
    - <span data-ttu-id="54fe8-232">Função de Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="54fe8-232">View-Only Recipients role</span></span>
    - <span data-ttu-id="54fe8-233">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="54fe8-233">Compliance Management</span></span>

<span data-ttu-id="54fe8-234">Para saber mais, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="54fe8-234">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="54fe8-235">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="54fe8-235">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="54fe8-236">Permissões de recursos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="54fe8-236">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="54fe8-237">E se os relatórios não estiverem mostrando dados?</span><span class="sxs-lookup"><span data-stu-id="54fe8-237">What if the reports aren't showing data?</span></span>

<span data-ttu-id="54fe8-238">Se você não estiver vendo dados nos seus relatórios, verifique se as suas políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="54fe8-238">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="54fe8-239">Para saber mais, confira [proteger contra ameaças no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span><span class="sxs-lookup"><span data-stu-id="54fe8-239">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="54fe8-240">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="54fe8-240">Related topics</span></span>

[<span data-ttu-id="54fe8-241">Proteção anti-spam de emails do Office 365</span><span class="sxs-lookup"><span data-stu-id="54fe8-241">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[<span data-ttu-id="54fe8-242">Relatórios e insights no centro de conformidade de &amp; segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="54fe8-242">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[<span data-ttu-id="54fe8-243">Criar um cronograma para um relatório no centro de &amp; conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="54fe8-243">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[<span data-ttu-id="54fe8-244">Configurar e baixar um relatório personalizado no centro de conformidade &amp; de segurança</span><span class="sxs-lookup"><span data-stu-id="54fe8-244">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

