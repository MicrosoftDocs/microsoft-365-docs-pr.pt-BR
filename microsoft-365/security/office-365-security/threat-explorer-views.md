---
title: Modos de exibição no Gerenciador de ameaças e detecções em tempo real
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre os vários tipos de modos de exibição disponíveis no Gerenciador de ameaças e detecções em tempo real.
ms.openlocfilehash: 7c3d78c5b5d4b1708fc57adba6951b4e352f0eaa
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073805"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="d3c32-103">Modos de exibição no Gerenciador de ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="d3c32-103">Views in Threat Explorer and real-time detections</span></span>

![Explorador de Ameaças](../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="d3c32-105">[Explorador de ameaças](threat-explorer.md) (e o relatório de detecções em tempo real) é uma ferramenta poderosa e quase em tempo real para ajudar as equipes de operações de segurança a investigar e responder a &amp; ameaças no centro de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="d3c32-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="d3c32-106">O Explorer (e o relatório de detecções em tempo real) exibe informações sobre o malware e phishing suspeitos em emails e arquivos no Office 365, bem como outras ameaças e riscos de segurança à sua organização.</span><span class="sxs-lookup"><span data-stu-id="d3c32-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

- <span data-ttu-id="d3c32-107">Se você tiver o [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) plano 2, você terá o Explorer.</span><span class="sxs-lookup"><span data-stu-id="d3c32-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="d3c32-108">Se você tiver o Office 365 ATP Plan 1, então você tem detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="d3c32-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="d3c32-109">Quando você abre o primeiro Explorer (ou o relatório de detecções em tempo real), o modo de exibição padrão mostra as detecções de malware de email dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="d3c32-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="d3c32-110">Este relatório também pode mostrar detecções de ATP, como URLs mal-intencionadas detectadas por [links seguros](atp-safe-links.md)e arquivos mal-intencionados detectados por [anexos seguros](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="d3c32-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="d3c32-111">Esse relatório pode ser modificado para mostrar dados nos últimos 30 dias (a menos que você esteja usando uma assinatura de avaliação).</span><span class="sxs-lookup"><span data-stu-id="d3c32-111">This report can be modified to show data for the past 30 days (unless you are using a trial subscription).</span></span> <span data-ttu-id="d3c32-112">As assinaturas de avaliação incluirão dados apenas nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="d3c32-112">Trial subscriptions will include data for the past seven days only.</span></span>

<span data-ttu-id="d3c32-113">Use o menu **Exibir** para alterar as informações que são exibidas.</span><span class="sxs-lookup"><span data-stu-id="d3c32-113">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="d3c32-114">As dicas de ferramentas ajudam a determinar o modo de exibição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="d3c32-114">Tooltips help you determine which view to use.</span></span>
  
![Menu Exibir do explorador de ameaças](../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="d3c32-116">Depois de selecionar um modo de exibição, você pode aplicar filtros e configurar consultas para realizar mais análises.</span><span class="sxs-lookup"><span data-stu-id="d3c32-116">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="d3c32-117">As seções a seguir fornecem uma breve visão geral dos vários modos de exibição disponíveis no Explorer (ou detecções em tempo real).</span><span class="sxs-lookup"><span data-stu-id="d3c32-117">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>  

## <a name="email--malware"></a><span data-ttu-id="d3c32-118">Malware de > de email</span><span class="sxs-lookup"><span data-stu-id="d3c32-118">Email > Malware</span></span>

<span data-ttu-id="d3c32-119">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** > \*\*\*\* > **malware**de email.</span><span class="sxs-lookup"><span data-stu-id="d3c32-119">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="d3c32-120">Este modo de exibição mostra informações sobre mensagens de email identificadas como contendo malware.</span><span class="sxs-lookup"><span data-stu-id="d3c32-120">This view shows information about email messages that were identified as containing malware.</span></span>  

![Exibir dados sobre email identificados como malware](../media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="d3c32-122">Clique em **remetente** para abrir a lista de opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="d3c32-122">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="d3c32-123">Use essa lista para exibir dados por remetente, destinatários, domínio do remetente, assunto, tecnologia de detecção, status de proteção e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-123">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="d3c32-124">Por exemplo, para ver quais ações foram executadas nas mensagens de email detectadas, escolha o **status de proteção** na lista.</span><span class="sxs-lookup"><span data-stu-id="d3c32-124">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="d3c32-125">Selecione uma opção e, em seguida, clique no botão atualizar para aplicar esse filtro ao relatório.</span><span class="sxs-lookup"><span data-stu-id="d3c32-125">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opções de status de proteção contra ameaças para o explorador de ameaças](../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="d3c32-127">Abaixo do gráfico, veja mais detalhes sobre mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="d3c32-127">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="d3c32-128">Quando você seleciona um item na lista, um painel de saída é aberto, onde você pode saber mais sobre o item que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="d3c32-128">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Gerenciador de ameaças com submenu aberto](../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="d3c32-130">Phishing > Phish</span><span class="sxs-lookup"><span data-stu-id="d3c32-130">Email > Phish</span></span>

<span data-ttu-id="d3c32-131">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** > \*\*\*\* > **phishing**de email.</span><span class="sxs-lookup"><span data-stu-id="d3c32-131">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="d3c32-132">Este modo de exibição mostra mensagens de email identificadas como tentativas de phishing.</span><span class="sxs-lookup"><span data-stu-id="d3c32-132">This view shows email messages identified as phishing attempts.</span></span>  

![Exibir dados sobre email identificados como tentativas de phishing](../media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="d3c32-134">Clique em **remetente** para abrir a lista de opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="d3c32-134">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="d3c32-135">Use esta lista para exibir dados por remetente, destinatários, domínio do remetente, IP do remetente, domínio da URL, clique em veredicto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-135">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="d3c32-136">Por exemplo, para ver que ações foram executadas quando pessoas clicaram nas URLs que foram identificadas como tentativas de phishing, escolha **clicar em veredicto** na lista, selecione uma ou mais opções e clique no botão atualizar.</span><span class="sxs-lookup"><span data-stu-id="d3c32-136">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Clique em opções do veredicto para o relatório de phishing](../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="d3c32-138">Abaixo do gráfico, veja mais detalhes sobre mensagens específicas, cliques de URL, URLs e origem de email.</span><span class="sxs-lookup"><span data-stu-id="d3c32-138">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![URLs detectadas como Phish em mensagens de email](../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="d3c32-140">Quando você seleciona um item na lista, como uma URL que foi detectada, um painel de saída é aberto, onde você pode saber mais sobre o item que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="d3c32-140">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Detalhes sobre uma URL detectada](../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="d3c32-142">Envios de > de email</span><span class="sxs-lookup"><span data-stu-id="d3c32-142">Email > Submissions</span></span>

<span data-ttu-id="d3c32-143">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** > \*\*\*\* > **envios**de email.</span><span class="sxs-lookup"><span data-stu-id="d3c32-143">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="d3c32-144">Este modo de exibição mostra o email que os usuários relataram como lixo eletrônico, não lixo eletrônico ou email de phishing.</span><span class="sxs-lookup"><span data-stu-id="d3c32-144">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![Mensagens de email relatadas por usuários](../media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="d3c32-146">Clique em **remetente** para abrir a lista de opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="d3c32-146">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="d3c32-147">Use esta lista para exibir informações por remetente, destinatários, tipo de relatório (a determinação do usuário de que o email era lixo eletrônico, não lixo eletrônico ou Phish) e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-147">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="d3c32-148">Por exemplo, para exibir informações sobre mensagens de email relatadas como tentativas de phishing, clique em**tipo de relatório**do **remetente** > , selecione **phishing**e clique no botão atualizar.</span><span class="sxs-lookup"><span data-stu-id="d3c32-148">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phishing selecionado para o filtro de tipo de relatório](../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="d3c32-150">Abaixo do gráfico, veja mais detalhes sobre mensagens de email específicas, como a linha de assunto, o endereço IP do remetente, o usuário que informou a mensagem como lixo eletrônico, não lixo eletrônico ou Phish e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-150">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![Mensagens relatadas como tentativas de phishing](../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="d3c32-152">Selecione um item na lista para exibir detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-152">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="d3c32-153">Email > todos os emails</span><span class="sxs-lookup"><span data-stu-id="d3c32-153">Email > All email</span></span>

<span data-ttu-id="d3c32-154">Para exibir esse relatório, no Explorer, escolha **Exibir** > **email** > **todos os emails**.</span><span class="sxs-lookup"><span data-stu-id="d3c32-154">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="d3c32-155">Este modo de exibição mostra uma visão detalhada da atividade de email, incluindo emails identificados como mal-intencionados devido a phishing ou malware, bem como todos os emails não-mal-intencionados (emails, spam e emails em massa normais).</span><span class="sxs-lookup"><span data-stu-id="d3c32-155">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="d3c32-156">Se você receber um erro que leia **muitos dados a serem exibidos**, adicione um filtro e, se necessário, restrinja o intervalo de datas que você está exibindo.</span><span class="sxs-lookup"><span data-stu-id="d3c32-156">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="d3c32-157">Para aplicar um filtro, escolha **remetente**, selecione um item na lista e clique no botão atualizar.</span><span class="sxs-lookup"><span data-stu-id="d3c32-157">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="d3c32-158">No nosso exemplo, usamos a **tecnologia de detecção** como um filtro (há várias opções disponíveis).</span><span class="sxs-lookup"><span data-stu-id="d3c32-158">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="d3c32-159">Exibir informações por remetente, domínio do remetente, destinatários, assunto, nome do arquivo de anexo, família de malware, status de proteção (ações executadas por seus recursos e políticas de proteção contra ameaças no Office 365), tecnologia de detecção (como o malware foi detectado) e adicionais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-159">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Exibir dados sobre o email detectado por tecnologia de detecção](../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="d3c32-161">Abaixo do gráfico, veja mais detalhes sobre mensagens de email específicas, como linha de assunto, destinatário, remetente, status e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d3c32-161">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="d3c32-162">Malware de > de conteúdo</span><span class="sxs-lookup"><span data-stu-id="d3c32-162">Content > Malware</span></span>

<span data-ttu-id="d3c32-163">Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** > \*\*\*\* > **malware**de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d3c32-163">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="d3c32-164">Este modo de exibição mostra arquivos que foram identificados como mal-intencionados pela [proteção avançada contra ameaças do Office 365 no SharePoint Online, no onedrive for Business e no Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d3c32-164">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d3c32-165">Exibir informações pela família de malware, tecnologia de detecção (como o malware foi detectado) e carga de trabalho (OneDrive, SharePoint ou Teams).</span><span class="sxs-lookup"><span data-stu-id="d3c32-165">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Exibir dados sobre malware detectado](../media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="d3c32-167">Abaixo do gráfico, veja mais detalhes sobre arquivos específicos, como o nome do arquivo anexo, carga de trabalho, tamanho do arquivo, que modificou o arquivo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-167">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="d3c32-168">Recursos de clique para filtrar</span><span class="sxs-lookup"><span data-stu-id="d3c32-168">Click-to-filter capabilities</span></span>

<span data-ttu-id="d3c32-169">Com o Explorer (e detecções em tempo real), você pode aplicar um filtro em um clique.</span><span class="sxs-lookup"><span data-stu-id="d3c32-169">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="d3c32-170">Clique em um item na legenda e esse item se torna um filtro para o relatório.</span><span class="sxs-lookup"><span data-stu-id="d3c32-170">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="d3c32-171">Por exemplo, vamos supor que estamos examinando o modo de exibição de malware no Explorer:</span><span class="sxs-lookup"><span data-stu-id="d3c32-171">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Vá para o Gerenciador \> de gerenciamento de ameaças](../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="d3c32-173">Clicar em **acionamento ATP** neste gráfico resultará em um modo de exibição como este:</span><span class="sxs-lookup"><span data-stu-id="d3c32-173">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Explorer filtrado para exibir somente os resultados de acionamento ATP](../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="d3c32-175">Neste modo de exibição, agora estamos examinando dados para arquivos que foram destruídodos por [anexos seguros do Office 365 ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="d3c32-175">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="d3c32-176">Abaixo do gráfico, podemos ver detalhes sobre mensagens de email específicas que tinham anexos detectados por anexos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="d3c32-176">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Detalhes específicos sobre mensagens de email com anexos detectados](../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="d3c32-178">Selecionar um ou mais itens ativa o menu **ações** , que oferece várias opções de escolha para os itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="d3c32-178">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Selecionar um item ativa o menu ações](../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="d3c32-180">A capacidade de filtrar em um clique e navegar para detalhes específicos pode poupar muito tempo na investigação de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d3c32-180">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="d3c32-181">Consultas e filtros</span><span class="sxs-lookup"><span data-stu-id="d3c32-181">Queries and filters</span></span>

<span data-ttu-id="d3c32-182">O Explorer (bem como o relatório de detecções em tempo real) tem vários filtros e recursos de consulta avançados que permitem detalhar detalhes, como os principais usuários direcionados, principais famílias de malware, tecnologia de detecção e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d3c32-182">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="d3c32-183">Cada tipo de relatório oferece várias maneiras de exibir e explorar dados.</span><span class="sxs-lookup"><span data-stu-id="d3c32-183">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3c32-184">Não use caracteres curinga, como um asterisco ou um ponto de interrogação, na barra de consulta para o Explorer (ou detecções em tempo real).</span><span class="sxs-lookup"><span data-stu-id="d3c32-184">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="d3c32-185">Quando você pesquisa o **campo assunto** de mensagens de email, Explorer (ou detecções em tempo real) executará a correspondência parcial e produzirá resultados similares a uma pesquisa curinga.</span><span class="sxs-lookup"><span data-stu-id="d3c32-185">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
