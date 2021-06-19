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
ms.openlocfilehash: eb62961bb26b079c508cbd5bc559a95d172cff86
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029880"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7fe3a-103">Segurança de email com o Explorador de Ameaças no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7fe3a-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="7fe3a-104">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="7fe3a-104">In this article:</span></span>

- [<span data-ttu-id="7fe3a-105">Exibir malware detectado no email</span><span class="sxs-lookup"><span data-stu-id="7fe3a-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="7fe3a-106">Exibir URL de phishing e clicar em dados de veredito</span><span class="sxs-lookup"><span data-stu-id="7fe3a-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="7fe3a-107">Iniciar investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="7fe3a-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="7fe3a-108">Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las). </span><span class="sxs-lookup"><span data-stu-id="7fe3a-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="7fe3a-109">Os outros dois artigos desta série são a busca de ameaças no [Explorador](threat-hunting-in-threat-explorer.md) de Ameaças e o Explorador de Ameaças e noções [básicas de detecções em tempo real.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="7fe3a-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>

<span data-ttu-id="7fe3a-110">Este artigo explica como exibir e investigar tentativas de malware e phishing detectadas por email por Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span>

<span data-ttu-id="7fe3a-111">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7fe3a-111">**Applies to:**</span></span>

- [<span data-ttu-id="7fe3a-112">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7fe3a-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7fe3a-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fe3a-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="7fe3a-114">Exibir malware detectado no email</span><span class="sxs-lookup"><span data-stu-id="7fe3a-114">View malware detected in email</span></span>

<span data-ttu-id="7fe3a-115">Para ver malware detectado em emails organizados pela tecnologia Microsoft 365, use o > [Detecções](threat-explorer-views.md#email--malware) de Malware de Email do Explorer (ou detecções em tempo real).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="7fe3a-116">Malware é o modo de exibição padrão, portanto, ele pode ser selecionado assim que você abrir o Explorer.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-116">Malware is the default view, so it might be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="7fe3a-117">No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), escolha **Email & colaboração** \> **Explorer** (ou **detecções** em tempo real; Este exemplo usa o Explorer).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

   <span data-ttu-id="7fe3a-118">A partir daqui, comece no View, escolha um determinado período de tempo para investigar (se necessário) e concentre seus filtros, conforme a passagem [do Explorer](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-118">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="7fe3a-119">Na lista **lista listada** Exibir, verifique se **o Malware** de \> **Email** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-119">In the **View** drop down list, verify that **Email** \> **Malware** is selected.</span></span>

3. <span data-ttu-id="7fe3a-120">Clique **em Remetente** e escolha Tecnologia de **Detecção** \> **Básica** na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-120">Click **Sender**, and then choose **Basic** \> **Detection technology** in the drop down list.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="tecnologia de detecção de malware":::

   <span data-ttu-id="7fe3a-122">Suas tecnologias de detecção agora estão disponíveis como filtros para o relatório.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-122">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="7fe3a-123">Escolha uma opção e clique em **Atualizar** para aplicar esse filtro (não atualize a janela do navegador).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-123">Choose an option, and then click **Refresh** to apply that filter (don't refresh your browser window).</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="tecnologia de detecção selecionada":::

   <span data-ttu-id="7fe3a-125">O relatório é atualizado para mostrar os resultados que o malware detectou no email, usando a opção de tecnologia selecionada.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-125">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="7fe3a-126">A partir daqui, você pode realizar uma análise mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-126">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="7fe3a-127">Exibir URL de phishing e clicar em dados de veredito</span><span class="sxs-lookup"><span data-stu-id="7fe3a-127">View phishing URL and click verdict data</span></span>

<span data-ttu-id="7fe3a-128">Você pode exibir tentativas de phishing por meio de URLs por email, incluindo uma lista de URLs que foram permitidas, bloqueadas e anuladas.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-128">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="7fe3a-129">Para identificar URLs que foram clicadas, Cofre [links](safe-links.md) devem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-129">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="7fe3a-130">Certifique-se de configurar as políticas [Cofre Links](set-up-safe-links-policies.md) para proteção de tempo de clique e registro em log de vereditos de clique por Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-130">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

1. <span data-ttu-id="7fe3a-131">No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), escolha **Email & colaboração** \> **Explorer** (ou **detecções** em tempo real; Este exemplo usa o Explorer).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-131">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

2. <span data-ttu-id="7fe3a-132">Na lista **lista** da Exibir, escolha **Email** \> **Phish**.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-132">In the **View** drop down list, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe3a-133">![Menu Exibir para o Explorer no contexto de phishing](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="7fe3a-133">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="7fe3a-134">Clique **em Remetente** e, em seguida, escolha **URLs** Clique em \> **veredito** na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-134">Click **Sender**, and then choose **URLs** \> **Click verdict** in the drop down list.</span></span>

4. <span data-ttu-id="7fe3a-135">Em opções que aparecem, selecione uma ou mais opções, como **Bloqueado** e Bloqueado substituído **e** clique em Atualizar **(não** atualize a janela do navegador).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-135">In options that appear, select one or more options, such as **Blocked** and **Block overridden**, and then click **Refresh** (don't refresh your browser window).</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URLs e clique em vereditos":::

   <span data-ttu-id="7fe3a-137">O relatório é atualizado para mostrar duas tabelas de URL diferentes na **guia URLs** sob o relatório:</span><span class="sxs-lookup"><span data-stu-id="7fe3a-137">The report refreshes to show two different URL tables on the **URLs** tab under the report:</span></span>

   - <span data-ttu-id="7fe3a-138">**As URLs principais** são as URLs nas mensagens que você filtreu para baixo e a ação de entrega de email conta para cada URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-138">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="7fe3a-139">Na exibição de email phishing, essa lista normalmente contém URLs legítimas.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-139">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="7fe3a-140">Os invasores incluem uma mistura de URLs boas e ruins em suas mensagens para tentar fazê-las entregues, mas fazem com que os links mal-intencionados pareçam mais interessantes.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-140">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="7fe3a-141">A tabela de URLs é classificação pela contagem total de emails, mas essa coluna está oculta para simplificar o exibição.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-141">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="7fe3a-142">**Os cliques principais** são os Cofre URLs empacotadas por links que foram clicadas, classificação por contagem total de cliques.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-142">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="7fe3a-143">Esta coluna também não é exibida, para simplificar o exibição.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-143">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="7fe3a-144">Contagens totais por coluna indicam Cofre links clicam em contagem de vereditos para cada URL clicada.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-144">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="7fe3a-145">Na exibição de email phishing, geralmente são URLs suspeitas ou mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-145">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="7fe3a-146">Mas a exibição pode incluir URLs que não são ameaças, mas estão em mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-146">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="7fe3a-147">Os cliques de URL em links não mapeados não aparecem aqui.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-147">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="7fe3a-148">As duas tabelas de URL mostram URLs principais em mensagens de email de phishing por ação de entrega e local.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-148">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="7fe3a-149">As tabelas mostram cliques de URL que foram bloqueados ou visitados apesar de um aviso, para que você possa ver quais possíveis links inválidos foram apresentados aos usuários e que os usuários clicaram.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-149">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="7fe3a-150">A partir daqui, você pode realizar uma análise mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-150">From here, you can conduct further analysis.</span></span> <span data-ttu-id="7fe3a-151">Por exemplo, abaixo do gráfico, você pode ver as PRINCIPAIS URLs em mensagens de email que foram bloqueadas no ambiente da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-151">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe3a-152">![URLs do Explorer que foram bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="7fe3a-152">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="7fe3a-153">Selecione uma URL para exibir informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-153">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7fe3a-154">Na caixa de diálogo sobre o sobrevoo de URL, a filtragem em mensagens de email é removida para mostrar a exibição completa da exposição da URL em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-154">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="7fe3a-155">Isso permite filtrar as mensagens de email que você está preocupado no Explorer, encontrar URLs específicas que são possíveis ameaças e, em seguida, expandir seu entendimento sobre a exposição de URL em seu ambiente (por meio da caixa de diálogo detalhes da URL) sem precisar adicionar filtros de URL ao próprio exibição do Explorer.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-155">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="7fe3a-156">Interpretação de vereditos de clique</span><span class="sxs-lookup"><span data-stu-id="7fe3a-156">Interpretation of click verdicts</span></span>

<span data-ttu-id="7fe3a-157">Nos flyouts email ou URL, Top Clicks e em nossas experiências de filtragem, você verá valores de veredito de clique diferentes:</span><span class="sxs-lookup"><span data-stu-id="7fe3a-157">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="7fe3a-158">**Nenhuma:** Não é possível capturar o veredito para a URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-158">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="7fe3a-159">O usuário pode ter clicado na URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-159">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="7fe3a-160">**Permitido:** O usuário teve permissão para navegar até a URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-160">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="7fe3a-161">**Bloqueado:** O usuário foi impedido de navegar para a URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-161">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="7fe3a-162">**Veredito pendente:** O usuário foi apresentado com a página pendente de detonação.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-162">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="7fe3a-163">**Bloqueado substituído:** O usuário foi impedido de navegar diretamente para a URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-163">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="7fe3a-164">Mas o usuário sobrecarregue o bloco para navegar até a URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-164">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="7fe3a-165">**Veredito pendente ignorado:** O usuário foi apresentado com a página de detonação.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-165">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="7fe3a-166">Mas o usuário overrode a mensagem para acessar a URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-166">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="7fe3a-167">**Erro:** O usuário foi apresentado com a página de erro ou ocorreu um erro na captura do veredito.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-167">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="7fe3a-168">**Falha:** Ocorreu uma exceção desconhecida durante a captura do veredito.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-168">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="7fe3a-169">O usuário pode ter clicado na URL.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-169">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="7fe3a-170">Iniciar investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="7fe3a-170">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="7fe3a-171">Recursos automatizados de investigação e resposta estão disponíveis no Microsoft Defender para Office 365 *Plano 2* e *Office 365 E5*.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-171">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="7fe3a-172">[A investigação e a resposta automatizadas](automated-investigation-response-office.md) podem economizar tempo e esforço gastos da equipe de operações de segurança investigando e atenuando ataques cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-172">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="7fe3a-173">Além de configurar alertas que podem disparar uma playbook de segurança, você pode iniciar um processo automatizado de investigação e resposta a partir de uma exibição no Explorer.</span><span class="sxs-lookup"><span data-stu-id="7fe3a-173">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="7fe3a-174">Para obter detalhes, consulte [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span><span class="sxs-lookup"><span data-stu-id="7fe3a-174">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="7fe3a-175">Outros artigos</span><span class="sxs-lookup"><span data-stu-id="7fe3a-175">Other articles</span></span>

[<span data-ttu-id="7fe3a-176">Investigar emails com a página Entidade de Email</span><span class="sxs-lookup"><span data-stu-id="7fe3a-176">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
