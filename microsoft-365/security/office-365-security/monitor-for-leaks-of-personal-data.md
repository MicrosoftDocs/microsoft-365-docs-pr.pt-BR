---
title: Monitorar o vazamento de dados pessoais
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Conheça três ferramentas disponíveis para monitorar o vazamento de dados pessoais.
ms.openlocfilehash: 617f0fde0e4b15a014658ba0fc3cf2def4b88d81
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088372"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="48ba6-103">Monitorar o vazamento de dados pessoais</span><span class="sxs-lookup"><span data-stu-id="48ba6-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="48ba6-p101">Existem várias ferramentas disponíveis destinadas a monitorar o uso e o transporte de dados pessoais. Este tópico descreve três ferramentas muito úteis.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![Ferramentas para monitorar o uso e o transporte de dados pessoais](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="48ba6-107">Na ilustração:</span><span class="sxs-lookup"><span data-stu-id="48ba6-107">In the illustration:</span></span>

- <span data-ttu-id="48ba6-p102">Comece a usar os relatórios de prevenção contra perda de dados do Office 365 para monitorar dados pessoais no SharePoint Online, no OneDrive for Business e nos emails em trânsito. Eles fornecem um monitoramento mais detalhado de dados pessoais. No entanto, esses relatórios não incluem todos os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p102">Start with Office 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="48ba6-p103">Em seguida, use as políticas de alerta e os logs de auditoria para monitorar as atividades em todos os serviços do Office 365. Configure um monitoramento permanente ou pesquise os logs de auditoria para investigar incidentes. Os logs de auditoria do Office 365 atuam em todos os serviços desta plataforma: Sway, PowerBI, Descoberta Eletrônica, Dynamics 365, Microsoft Flow, Microsoft Teams, Atividade do administrador, OneDrive for Business, SharePoint Online, emails em trânsito e caixas de correio em repouso. As caixas de correio em repouso incluem as conversas do Skype.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p103">Next, use alert policies and the Office 365 audit log to monitor activity across Office 365 services. Setup ongoing monitoring or search the audit log to investigate an incident. The Office 365 audit log works across Office 365 services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="48ba6-p104">Por fim, use o Microsoft Cloud App Security para monitorar os arquivos com dados confidenciais em outros provedores de SaaS. Em breve, adicionaremos a capacidade de usar tipos de informações confidenciais e rótulos unificados do Office 365 com o Cloud App Security, na Proteção de Informações do Azure e no Office. Você pode configurar políticas que se apliquem a todos os aplicativos SaaS ou a aplicativos específicos, como o Box. O Cloud App Security não descobre arquivos no Exchange Online, nem os arquivos anexados em emails.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use Office 365 sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can setup policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="office-365-data-loss-prevention-reports"></a><span data-ttu-id="48ba6-119">Relatórios de prevenção contra perda de dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-119">Office 365 data loss prevention reports</span></span>

<span data-ttu-id="48ba6-p105">Após criar as políticas DLP (prevenção contra perda de dados), convém verificar se elas estão funcionando conforme esperado e se estão ajudando a manter a conformidade. Com os relatórios DLP do Office 365, você pode exibir rapidamente o número de falsos positivos, substituições ou correspondências de regra e política DLP; verificar se elas estão mais ou menos populares ao longo do tempo; filtrar o relatório de várias maneiras e exibir mais detalhes selecionando um ponto em uma linha no gráfico.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p105">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="48ba6-122">Você pode usar os relatórios DLP para:</span><span class="sxs-lookup"><span data-stu-id="48ba6-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="48ba6-123">Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.</span><span class="sxs-lookup"><span data-stu-id="48ba6-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="48ba6-124">Descobrir processos empresariais que violam as políticas DLP da organização.</span><span class="sxs-lookup"><span data-stu-id="48ba6-124">Discover business processes that violate your organization's DLP policies.</span></span>

- <span data-ttu-id="48ba6-125">Compreender qualquer impacto nos negócios das políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="48ba6-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="48ba6-126">Exiba as justificativas enviadas pelos usuários quando eles resolverem uma dica de política substituindo a política ou relatando um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="48ba6-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="48ba6-127">Verificar a conformidade com uma determinada política DLP mostrando as correspondências dessa política.</span><span class="sxs-lookup"><span data-stu-id="48ba6-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="48ba6-128">Exibir uma lista de arquivos com dados confidenciais que correspondem às políticas DLP no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="48ba6-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="48ba6-129">Além disso, você pode usar os relatórios de DLP para ajustar suas políticas DLP conforme as executa no modo de teste.</span><span class="sxs-lookup"><span data-stu-id="48ba6-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="48ba6-130">Os relatórios DLP estão no centro de segurança e o no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="48ba6-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="48ba6-131">Navegue até Relatórios \> Exibir relatórios.</span><span class="sxs-lookup"><span data-stu-id="48ba6-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="48ba6-132">Em prevenção de perda de dados (DLP), vá para correspondências de políticas e regras DLP ou substituições e falsos positivos DLP.</span><span class="sxs-lookup"><span data-stu-id="48ba6-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="48ba6-133">Para saber mais, confira o artigo [Exibir o relatório de prevenção contra perda de dados](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span><span class="sxs-lookup"><span data-stu-id="48ba6-133">For more information, see [View the reports for data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span></span>

![Relatório mostrando correspondências de política DLP](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a><span data-ttu-id="48ba6-135">Log de auditoria e políticas de alerta do Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-135">Office 365 audit log and alert policies</span></span>

<span data-ttu-id="48ba6-136">O log de auditoria inclui eventos das plataformas Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway e de outros serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="48ba6-136">The Office 365 audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other Office 365 services.</span></span>

<span data-ttu-id="48ba6-137">O centro de conformidade e o centro de segurança oferecem duas maneiras de monitorar e gerar relatórios no log de auditoria do Office 365:</span><span class="sxs-lookup"><span data-stu-id="48ba6-137">The security center and compliance center provide two ways to monitor and report against the Office 365 audit log:</span></span>

- <span data-ttu-id="48ba6-138">Configurar políticas de alerta, exibir alertas e monitorar tendências – Use as ferramentas painel de alerta e política de alerta no centro de conformidade ou no centro segurança.</span><span class="sxs-lookup"><span data-stu-id="48ba6-138">Setup alert policies, view alerts, and monitor trends — Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="48ba6-p107">Pesquisar diretamente no log de auditoria – você pode pesquisar todos os eventos em um intervalo de datas especificado ou filtrar os resultados com base em determinados critérios; por exemplo, o usuário que executou a ação, a ação ou o objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p107">Search the audit log directly — Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="48ba6-p108">As equipes de conformidade e segurança de informações podem usar essas ferramentas de forma proativa para revisar as atividades executadas por usuários finais e administradores em todos os serviços do Office 365. É possível configurar alertas automáticos a fim de enviar notificações por email, quando ocorrem determinadas atividades em conjuntos de sites específicos; por exemplo, quando o conteúdo é compartilhado de sites conhecidos por incluir informações relacionadas ao GDPR. Dessa forma, as equipes podem acompanhar os usuários para garantir que as políticas de segurança corporativa sejam cumpridas ou para fornecer treinamento adicional.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across Office 365 services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="48ba6-p109">As equipes de segurança de informações podem também pesquisar o log de auditoria para investigar suspeitas de violação de dados, bem como determinar a causa raiz e a abrangência da violação. Esta funcionalidade interna facilita o cumprimento dos artigos 33 e 34 do GDPR, que exige o envio de notificações sobre violação de dados à autoridade supervisora do GDPR e aos detentores dos dados, em um período específico. As entradas do log de auditoria são mantidas apenas por 90 dias no serviço. Recomendamos e a maioria das organizações exige que esses logs sejam mantidos por mais tempo.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="48ba6-p110">Existem soluções disponíveis, com quais é possível inscrever-se nos logs de auditoria unificados por meio da API da Atividade de Gestão da Microsoft, que podem armazenar as entradas do log conforme necessário, além de fornecer alertas e painéis avançados. Por exemplo, o [OMS (Microsoft Operations Management Suite)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="48ba6-p110">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="48ba6-149">Clique nos links abaixo para saber mais sobre as políticas de alerta e como pesquisar no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="48ba6-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="48ba6-150">Políticas de alerta nos centros de conformidade e segurança do Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

- <span data-ttu-id="48ba6-151">[Pesquisar as atividades do administrador e dos usuários no log de auditoria do Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introdução)</span><span class="sxs-lookup"><span data-stu-id="48ba6-151">[Search the audit log for user and admin activity in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduction)</span></span>

- [<span data-ttu-id="48ba6-152">Ativar e desativar a Pesquisa de log de auditoria do Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-152">Turn Office 365 audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

- [<span data-ttu-id="48ba6-153">Pesquisas o log de auditoria</span><span class="sxs-lookup"><span data-stu-id="48ba6-153">Search the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

- <span data-ttu-id="48ba6-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (cmdlet)</span><span class="sxs-lookup"><span data-stu-id="48ba6-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="48ba6-155">Propriedades detalhadas no log de auditoria do Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-155">Detailed properties in the Office 365 audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="48ba6-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48ba6-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="48ba6-157">O Microsoft Cloud App Security ajuda a descobrir outros aplicativos SaaS em uso nas redes e os dados confidenciais enviados desses aplicativos ou para eles.</span><span class="sxs-lookup"><span data-stu-id="48ba6-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="48ba6-p111">O Microsoft Cloud App Security é um serviço abrangente que fornece visibilidade ampliada, controles granulares e proteção aprimorada contra ameaças para os aplicativos de nuvem. Ele identifica mais de 15 mil aplicativos de nuvem na rede, em todos os dispositivos, além de fornecer análise, avaliação e pontuação de risco contínuas. Não são necessários agentes: os dados são coletados nos firewalls e proxies para que você tenha contexto e visibilidade completa do uso da nuvem e da TI sombra.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="48ba6-p112">Para entender melhor o ambiente de nuvem, o recurso de investigação do Cloud App Security fornece uma ampla visibilidade de atividades, arquivos e contas para aplicativos gerenciados e sancionados. Você pode obter informações detalhadas em nível de arquivo e descobrir o deslocamento dos dados nos aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p112">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="48ba6-163">Por exemplo, a ilustração a seguir mostra duas políticas do Cloud App Security que podem ajudar com o GDPR.</span><span class="sxs-lookup"><span data-stu-id="48ba6-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Exemplos de políticas do Cloud App Security](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="48ba6-165">A primeira política alerta quando os arquivos escolhidos, que incluem expressões personalizadas ou atributos de PII predefinidos, são compartilhados fora da organização nos aplicativos SaaS.</span><span class="sxs-lookup"><span data-stu-id="48ba6-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="48ba6-p113">A segunda política bloqueia os downloads de arquivos em dispositivos não gerenciados. Você escolhe os atributos que deseja procurar nos arquivos, bem como os aplicativos SaaS aos quais deseja aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="48ba6-168">Em breve, os seguintes tipos de atributos estarão disponíveis para o Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="48ba6-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="48ba6-169">Tipos de informações confidenciais do Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-169">Office 365 sensitive information types</span></span>

- <span data-ttu-id="48ba6-170">Rótulos unificados no Office 365 e na Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="48ba6-170">Unified labels across Office 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="48ba6-171">Painel do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48ba6-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="48ba6-p114">Se ainda não começou a usar o Cloud App Security, o primeiro passo é iniciá-lo. Acesse o Cloud App Security em <https://portal.cloudappsecurity.com>.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p114">If you haven't yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="48ba6-p115">Observação: não deixe de habilitar a opção "Examinar automaticamente os arquivos com rótulos de classificação da Proteção de Informações do Azure" (nas Configurações Gerais) quando começar a usar o Cloud App Security ou antes de atribuir rótulos. Depois de configurar o Cloud App Security, ele não examinará os arquivos existentes novamente até eles serem modificados.</span><span class="sxs-lookup"><span data-stu-id="48ba6-p115">Note: Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Painel mostrando informações sobre alertas](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="48ba6-177">Mais informações:</span><span class="sxs-lookup"><span data-stu-id="48ba6-177">More information:</span></span>

- [<span data-ttu-id="48ba6-178">Implantar o Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48ba6-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="48ba6-179">Mais informações sobre o Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48ba6-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="48ba6-180">Bloqueando downloads de informações confidenciais usando o proxy do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48ba6-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="48ba6-181">Políticas de atividade e arquivo de exemplo para detectar o compartilhamento de dados pessoais</span><span class="sxs-lookup"><span data-stu-id="48ba6-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="48ba6-182">Detectar compartilhamento de arquivos que contêm informações de identificação pessoal: número de cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="48ba6-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="48ba6-183">Alerta quando um arquivo que contém um número de cartão de crédito é compartilhado em um aplicativo de nuvem aprovado.</span><span class="sxs-lookup"><span data-stu-id="48ba6-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="48ba6-184"><strong>Controle</strong></span><span class="sxs-lookup"><span data-stu-id="48ba6-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="48ba6-185"><strong>Configurações</strong></span><span class="sxs-lookup"><span data-stu-id="48ba6-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-186">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="48ba6-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="48ba6-187">Política de arquivo</span><span class="sxs-lookup"><span data-stu-id="48ba6-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-188">Modelo de política</span><span class="sxs-lookup"><span data-stu-id="48ba6-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="48ba6-189">Sem modelo</span><span class="sxs-lookup"><span data-stu-id="48ba6-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-190">Severidade da política</span><span class="sxs-lookup"><span data-stu-id="48ba6-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="48ba6-191">Alta</span><span class="sxs-lookup"><span data-stu-id="48ba6-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-192">Categoria</span><span class="sxs-lookup"><span data-stu-id="48ba6-192">Category</span></span></td>
<td align="left"><span data-ttu-id="48ba6-193">DLP</span><span class="sxs-lookup"><span data-stu-id="48ba6-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-194">Configurações de Filtro</span><span class="sxs-lookup"><span data-stu-id="48ba6-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-195">Nível de acesso = Público (Internet), público, externo</span><span class="sxs-lookup"><span data-stu-id="48ba6-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="48ba6-196">Aplicativo = &lt;selecionar aplicativos&gt; (use essa configuração caso pretenda limitar o monitoramento a aplicativos SaaS específicos)</span><span class="sxs-lookup"><span data-stu-id="48ba6-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-197">Aplicar a</span><span class="sxs-lookup"><span data-stu-id="48ba6-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="48ba6-198">Todos os arquivos, todos os proprietários</span><span class="sxs-lookup"><span data-stu-id="48ba6-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-199">Inspeção de conteúdo</span><span class="sxs-lookup"><span data-stu-id="48ba6-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-200">Inclui os arquivos que correspondam a uma expressão presente: "Todos os países: finanças: número do cartão de crédito"</span><span class="sxs-lookup"><span data-stu-id="48ba6-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="48ba6-201">Não exige contexto relevante: não selecionado (isso corresponde a palavras-chave e expressões regulares)</span><span class="sxs-lookup"><span data-stu-id="48ba6-201">Don't require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="48ba6-202">Inclui arquivos com pelo menos uma correspondência</span><span class="sxs-lookup"><span data-stu-id="48ba6-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="48ba6-203">Remover a máscara dos quatro últimos caracteres da violação: selecionado</span><span class="sxs-lookup"><span data-stu-id="48ba6-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-204">Alertas</span><span class="sxs-lookup"><span data-stu-id="48ba6-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-205">Criar um alerta para cada arquivo correspondente: selecionado</span><span class="sxs-lookup"><span data-stu-id="48ba6-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="48ba6-206">Limite diário de alerta: 1.000</span><span class="sxs-lookup"><span data-stu-id="48ba6-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="48ba6-207">Selecionar um alerta como email: selecionado</span><span class="sxs-lookup"><span data-stu-id="48ba6-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="48ba6-208">Para: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="48ba6-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-209">Gestão</span><span class="sxs-lookup"><span data-stu-id="48ba6-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-210">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="48ba6-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="48ba6-211">Tornar particular: selecionar "Remover usuários externos"</span><span class="sxs-lookup"><span data-stu-id="48ba6-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="48ba6-212">Todas as outras configurações: não selecionadas</span><span class="sxs-lookup"><span data-stu-id="48ba6-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="48ba6-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="48ba6-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="48ba6-214">Tornar particular: selecionar "Remover usuários externos"</span><span class="sxs-lookup"><span data-stu-id="48ba6-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="48ba6-215">Todas as outras configurações: não selecionadas</span><span class="sxs-lookup"><span data-stu-id="48ba6-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="48ba6-216">Políticas semelhantes:</span><span class="sxs-lookup"><span data-stu-id="48ba6-216">Similar policies:</span></span>

- <span data-ttu-id="48ba6-217">Detectar compartilhamento de arquivos que contêm informações de identificação pessoal: endereço de email</span><span class="sxs-lookup"><span data-stu-id="48ba6-217">Detect sharing of Files containing PII - Email Address</span></span>

- <span data-ttu-id="48ba6-218">Detectar compartilhamento de arquivos que contêm informações de identificação pessoal: número do passaporte</span><span class="sxs-lookup"><span data-stu-id="48ba6-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="48ba6-219">Detectar clientes ou dados de RH no Box ou no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="48ba6-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="48ba6-220">Alerta quando um arquivo rotulado como "Dados do cliente" ou "Dados de RH" é carregado no Box ou no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="48ba6-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="48ba6-221">Observações:</span><span class="sxs-lookup"><span data-stu-id="48ba6-221">Notes:</span></span>

- <span data-ttu-id="48ba6-222">o monitoramento do Box exige configurar um conector com o SDK do conector de API.</span><span class="sxs-lookup"><span data-stu-id="48ba6-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

- <span data-ttu-id="48ba6-223">Essa política exige funcionalidades que estão atualmente em visualização privada.</span><span class="sxs-lookup"><span data-stu-id="48ba6-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="48ba6-224"><strong>Controle</strong></span><span class="sxs-lookup"><span data-stu-id="48ba6-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="48ba6-225"><strong>Configurações</strong></span><span class="sxs-lookup"><span data-stu-id="48ba6-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-226">Tipo de política</span><span class="sxs-lookup"><span data-stu-id="48ba6-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="48ba6-227">Política de atividade</span><span class="sxs-lookup"><span data-stu-id="48ba6-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-228">Modelo de política</span><span class="sxs-lookup"><span data-stu-id="48ba6-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="48ba6-229">Sem modelo</span><span class="sxs-lookup"><span data-stu-id="48ba6-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-230">Severidade da política</span><span class="sxs-lookup"><span data-stu-id="48ba6-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="48ba6-231">Alta</span><span class="sxs-lookup"><span data-stu-id="48ba6-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-232">Categoria</span><span class="sxs-lookup"><span data-stu-id="48ba6-232">Category</span></span></td>
<td align="left"><span data-ttu-id="48ba6-233">Controle de Compartilhamento</span><span class="sxs-lookup"><span data-stu-id="48ba6-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-234">Atuar em</span><span class="sxs-lookup"><span data-stu-id="48ba6-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="48ba6-235">Atividade única</span><span class="sxs-lookup"><span data-stu-id="48ba6-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-236">Configurações de Filtro</span><span class="sxs-lookup"><span data-stu-id="48ba6-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-237">Tipo de atividade = carregar arquivo</span><span class="sxs-lookup"><span data-stu-id="48ba6-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="48ba6-238">Aplicativo = Microsoft OneDrive for Business e Box</span><span class="sxs-lookup"><span data-stu-id="48ba6-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="48ba6-239">Rótulo de classificação (atualmente em visualização privada): Proteção de Informações do Azure = Dados do cliente, Recursos humanos: dados de salário; Recursos humanos: dados do funcionário</span><span class="sxs-lookup"><span data-stu-id="48ba6-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="48ba6-240">Alertas</span><span class="sxs-lookup"><span data-stu-id="48ba6-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-241">Criar um alerta: selecionado</span><span class="sxs-lookup"><span data-stu-id="48ba6-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="48ba6-242">Limite diário de alerta: 1.000</span><span class="sxs-lookup"><span data-stu-id="48ba6-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="48ba6-243">Selecionar um alerta como email: selecionado</span><span class="sxs-lookup"><span data-stu-id="48ba6-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="48ba6-244">Para: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="48ba6-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="48ba6-245">Gestão</span><span class="sxs-lookup"><span data-stu-id="48ba6-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="48ba6-246">Todos os aplicativos</span><span class="sxs-lookup"><span data-stu-id="48ba6-246">All apps</span></span></p>
<p><span data-ttu-id="48ba6-247">Colocar o usuário em quarentena: selecionar</span><span class="sxs-lookup"><span data-stu-id="48ba6-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="48ba6-248">Todas as outras configurações: não selecionadas</span><span class="sxs-lookup"><span data-stu-id="48ba6-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="48ba6-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="48ba6-249">Office 365</span></span></p>
<p><span data-ttu-id="48ba6-250">Colocar o usuário em quarentena: selecionar</span><span class="sxs-lookup"><span data-stu-id="48ba6-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="48ba6-251">Todas as outras configurações: não selecionadas</span><span class="sxs-lookup"><span data-stu-id="48ba6-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="48ba6-252">Políticas semelhantes:</span><span class="sxs-lookup"><span data-stu-id="48ba6-252">Similar policies:</span></span>

- <span data-ttu-id="48ba6-253">Detectar grandes downloads de dados do cliente ou de RH – alerta quando for detectada uma grande quantidade de arquivos que contêm dados de clientes ou de RH sendo baixada por um único usuário, dentro de um curto período.</span><span class="sxs-lookup"><span data-stu-id="48ba6-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

- <span data-ttu-id="48ba6-254">Detectar o compartilhamento de dados de clientes e de RH – alerta quando os arquivos com dados de clientes ou de RH são compartilhados.</span><span class="sxs-lookup"><span data-stu-id="48ba6-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
