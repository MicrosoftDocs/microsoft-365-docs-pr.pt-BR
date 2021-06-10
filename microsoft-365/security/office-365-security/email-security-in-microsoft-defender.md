---
title: Segurança de email com o Explorador de Ameaças no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Exibir e investigar tentativas de phishing de malware.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2a6d3d10cfa21c0ad2da948bff130cb9336ebd8
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297615"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ef0be-103">Segurança de email com o Explorador de Ameaças no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ef0be-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ef0be-104">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="ef0be-104">In this article:</span></span>

- [<span data-ttu-id="ef0be-105">Exibir malware detectado no email</span><span class="sxs-lookup"><span data-stu-id="ef0be-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="ef0be-106">Exibir URL de phishing e clicar em dados de veredito</span><span class="sxs-lookup"><span data-stu-id="ef0be-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="ef0be-107">Iniciar investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="ef0be-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="ef0be-108">Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las). </span><span class="sxs-lookup"><span data-stu-id="ef0be-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="ef0be-109">Os outros dois artigos desta série são a busca de ameaças no [Explorador](threat-hunting-in-threat-explorer.md) de Ameaças e o Explorador de Ameaças e noções [básicas de detecções em tempo real.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="ef0be-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="ef0be-110">Este artigo explica como exibir e investigar tentativas de malware e phishing detectadas por email por Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="ef0be-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="ef0be-111">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="ef0be-111">**Applies to**</span></span>

- [<span data-ttu-id="ef0be-112">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ef0be-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ef0be-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef0be-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="ef0be-114">Exibir malware detectado no email</span><span class="sxs-lookup"><span data-stu-id="ef0be-114">View malware detected in email</span></span>

<span data-ttu-id="ef0be-115">Para ver malware detectado em emails organizados pela tecnologia Microsoft 365, use o > [Detecções](threat-explorer-views.md#email--malware) de Malware de Email do Explorer (ou detecções em tempo real).</span><span class="sxs-lookup"><span data-stu-id="ef0be-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="ef0be-116">Malware é o modo de exibição padrão, portanto, ele pode ser selecionado assim que você abrir o Explorer.</span><span class="sxs-lookup"><span data-stu-id="ef0be-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="ef0be-117">No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real).**</span><span class="sxs-lookup"><span data-stu-id="ef0be-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="ef0be-118">(Este exemplo usa o Explorer.) Se você estiver no centro de segurança Microsoft 365 convergido ( role para https://security.microsoft.com/) **Email & collaboration**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ef0be-118">(This example uses Explorer.) If you're in the converged Microsoft 365 security center (https://security.microsoft.com/) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="ef0be-119">A partir daqui, comece no View, escolha um determinado período de tempo para investigar (se necessário) e concentre seus filtros, conforme a passagem [do Explorer](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span><span class="sxs-lookup"><span data-stu-id="ef0be-119">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="ef0be-120">No menu **Exibir,** escolha **Malware de** \> **Email**.</span><span class="sxs-lookup"><span data-stu-id="ef0be-120">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef0be-121">![Menu Exibir para Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="ef0be-121">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="ef0be-122">Clique **em Remetente** e, em seguida, escolha Tecnologia de **Detecção** \> **Básica**.</span><span class="sxs-lookup"><span data-stu-id="ef0be-122">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="ef0be-123">Suas tecnologias de detecção agora estão disponíveis como filtros para o relatório.</span><span class="sxs-lookup"><span data-stu-id="ef0be-123">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef0be-124">![Tecnologias de detecção de malware](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="ef0be-124">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="ef0be-125">Escolha uma opção.</span><span class="sxs-lookup"><span data-stu-id="ef0be-125">Choose an option.</span></span> <span data-ttu-id="ef0be-126">Em seguida, selecione **o botão** Atualizar para aplicar esse filtro.</span><span class="sxs-lookup"><span data-stu-id="ef0be-126">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef0be-127">![Tecnologia de detecção selecionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="ef0be-127">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="ef0be-128">O relatório é atualizado para mostrar os resultados que o malware detectou no email, usando a opção de tecnologia selecionada.</span><span class="sxs-lookup"><span data-stu-id="ef0be-128">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="ef0be-129">A partir daqui, você pode realizar uma análise mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="ef0be-129">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="ef0be-130">Exibir URL de phishing e clicar em dados de veredito</span><span class="sxs-lookup"><span data-stu-id="ef0be-130">View phishing URL and click verdict data</span></span>

<span data-ttu-id="ef0be-131">Você pode exibir tentativas de phishing por meio de URLs por email, incluindo uma lista de URLs que foram permitidas, bloqueadas e anuladas.</span><span class="sxs-lookup"><span data-stu-id="ef0be-131">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="ef0be-132">Para identificar URLs que foram clicadas, Cofre [links](safe-links.md) devem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="ef0be-132">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="ef0be-133">Certifique-se de configurar as políticas [Cofre Links](set-up-safe-links-policies.md) para proteção de tempo de clique e registro em log de vereditos de clique por Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="ef0be-133">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="ef0be-134">Para revisar URLs de phishing em mensagens e cliques em URLs em mensagens de phishing, use a exibição [   >  **phishing**](threat-explorer-views.md#email--phish) de email do Explorer ou detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="ef0be-134">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="ef0be-135">No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real).**</span><span class="sxs-lookup"><span data-stu-id="ef0be-135">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="ef0be-136">(Este exemplo usa o Explorer.)</span><span class="sxs-lookup"><span data-stu-id="ef0be-136">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="ef0be-137">No menu **Exibir,** escolha **Email** \> **Phish**.</span><span class="sxs-lookup"><span data-stu-id="ef0be-137">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef0be-138">![Menu Exibir para o Explorer no contexto de phishing](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="ef0be-138">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="ef0be-139">Clique **em Remetente** e, em seguida, escolha **URLs** \> **Clique em veredito**.</span><span class="sxs-lookup"><span data-stu-id="ef0be-139">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="ef0be-140">Selecione uma ou mais opções, como **Bloqueado** e Bloqueado  **substituído,** e selecione o botão Atualizar na mesma linha que as opções para aplicar esse filtro.</span><span class="sxs-lookup"><span data-stu-id="ef0be-140">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="ef0be-141">(Não atualize a janela do navegador.)</span><span class="sxs-lookup"><span data-stu-id="ef0be-141">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef0be-142">![URLs e clique em vereditos](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="ef0be-142">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="ef0be-143">O relatório é atualizado para mostrar duas tabelas de URL diferentes na guia URL no relatório:</span><span class="sxs-lookup"><span data-stu-id="ef0be-143">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="ef0be-144">**As URLs principais** são as URLs nas mensagens que você filtreu para baixo e a ação de entrega de email conta para cada URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-144">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="ef0be-145">Na exibição de email phishing, essa lista normalmente contém URLs legítimas.</span><span class="sxs-lookup"><span data-stu-id="ef0be-145">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="ef0be-146">Os invasores incluem uma mistura de URLs boas e ruins em suas mensagens para tentar fazê-las entregues, mas fazem com que os links mal-intencionados pareçam mais interessantes.</span><span class="sxs-lookup"><span data-stu-id="ef0be-146">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="ef0be-147">A tabela de URLs é classificação pela contagem total de emails, mas essa coluna está oculta para simplificar o exibição.</span><span class="sxs-lookup"><span data-stu-id="ef0be-147">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="ef0be-148">**Os cliques principais** são os Cofre URLs empacotadas por links que foram clicadas, classificação por contagem total de cliques.</span><span class="sxs-lookup"><span data-stu-id="ef0be-148">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="ef0be-149">Esta coluna também não é exibida, para simplificar o exibição.</span><span class="sxs-lookup"><span data-stu-id="ef0be-149">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="ef0be-150">Contagens totais por coluna indicam Cofre links clicam em contagem de vereditos para cada URL clicada.</span><span class="sxs-lookup"><span data-stu-id="ef0be-150">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="ef0be-151">Na exibição de email phishing, geralmente são URLs suspeitas ou mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="ef0be-151">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="ef0be-152">Mas a exibição pode incluir URLs que não são ameaças, mas estão em mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="ef0be-152">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="ef0be-153">Os cliques de URL em links não mapeados não aparecem aqui.</span><span class="sxs-lookup"><span data-stu-id="ef0be-153">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="ef0be-154">As duas tabelas de URL mostram URLs principais em mensagens de email de phishing por ação de entrega e local.</span><span class="sxs-lookup"><span data-stu-id="ef0be-154">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="ef0be-155">As tabelas mostram cliques de URL que foram bloqueados ou visitados apesar de um aviso, para que você possa ver quais possíveis links inválidos foram apresentados aos usuários e que os usuários clicaram.</span><span class="sxs-lookup"><span data-stu-id="ef0be-155">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="ef0be-156">A partir daqui, você pode realizar uma análise mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="ef0be-156">From here, you can conduct further analysis.</span></span> <span data-ttu-id="ef0be-157">Por exemplo, abaixo do gráfico, você pode ver as PRINCIPAIS URLs em mensagens de email que foram bloqueadas no ambiente da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ef0be-157">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef0be-158">![URLs do Explorer que foram bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="ef0be-158">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="ef0be-159">Selecione uma URL para exibir informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="ef0be-159">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ef0be-160">Na caixa de diálogo sobre o sobrevoo de URL, a filtragem em mensagens de email é removida para mostrar a exibição completa da exposição da URL em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ef0be-160">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="ef0be-161">Isso permite filtrar as mensagens de email que você está preocupado no Explorer, encontrar URLs específicas que são possíveis ameaças e, em seguida, expandir seu entendimento sobre a exposição de URL em seu ambiente (por meio da caixa de diálogo detalhes da URL) sem precisar adicionar filtros de URL ao próprio exibição do Explorer.</span><span class="sxs-lookup"><span data-stu-id="ef0be-161">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="ef0be-162">Interpretação de vereditos de clique</span><span class="sxs-lookup"><span data-stu-id="ef0be-162">Interpretation of click verdicts</span></span>

<span data-ttu-id="ef0be-163">Nos flyouts email ou URL, Top Clicks e em nossas experiências de filtragem, você verá valores de veredito de clique diferentes:</span><span class="sxs-lookup"><span data-stu-id="ef0be-163">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="ef0be-164">**Nenhuma:** Não é possível capturar o veredito para a URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-164">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="ef0be-165">O usuário pode ter clicado na URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-165">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="ef0be-166">**Permitido:** O usuário teve permissão para navegar até a URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-166">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="ef0be-167">**Bloqueado:** O usuário foi impedido de navegar para a URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-167">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="ef0be-168">**Veredito pendente:** O usuário foi apresentado com a página pendente de detonação.</span><span class="sxs-lookup"><span data-stu-id="ef0be-168">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="ef0be-169">**Bloqueado substituído:** O usuário foi impedido de navegar diretamente para a URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-169">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="ef0be-170">Mas o usuário sobrecarregue o bloco para navegar até a URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-170">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="ef0be-171">**Veredito pendente ignorado:** O usuário foi apresentado com a página de detonação.</span><span class="sxs-lookup"><span data-stu-id="ef0be-171">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="ef0be-172">Mas o usuário overrode a mensagem para acessar a URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-172">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="ef0be-173">**Erro:** O usuário foi apresentado com a página de erro ou ocorreu um erro na captura do veredito.</span><span class="sxs-lookup"><span data-stu-id="ef0be-173">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="ef0be-174">**Falha:** Ocorreu uma exceção desconhecida durante a captura do veredito.</span><span class="sxs-lookup"><span data-stu-id="ef0be-174">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="ef0be-175">O usuário pode ter clicado na URL.</span><span class="sxs-lookup"><span data-stu-id="ef0be-175">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="ef0be-176">Iniciar investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="ef0be-176">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="ef0be-177">Recursos automatizados de investigação e resposta estão disponíveis no Microsoft Defender para Office 365 *Plano 2* e *Office 365 E5*.</span><span class="sxs-lookup"><span data-stu-id="ef0be-177">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="ef0be-178">[A investigação e a resposta automatizadas](automated-investigation-response-office.md) podem economizar tempo e esforço gastos da equipe de operações de segurança investigando e atenuando ataques cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="ef0be-178">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="ef0be-179">Além de configurar alertas que podem disparar uma playbook de segurança, você pode iniciar um processo automatizado de investigação e resposta a partir de uma exibição no Explorer.</span><span class="sxs-lookup"><span data-stu-id="ef0be-179">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="ef0be-180">Para obter detalhes, consulte [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span><span class="sxs-lookup"><span data-stu-id="ef0be-180">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="ef0be-181">Outros artigos</span><span class="sxs-lookup"><span data-stu-id="ef0be-181">Other articles</span></span>

[<span data-ttu-id="ef0be-182">Investigar emails com a página Entidade de Email</span><span class="sxs-lookup"><span data-stu-id="ef0be-182">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
