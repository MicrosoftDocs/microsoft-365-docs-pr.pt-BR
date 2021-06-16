---
title: Busca de ameaças no Explorador de Ameaças para o Microsoft Defender para Office 365
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
description: Use o Explorador de Ameaças ou detecções em tempo real no portal Microsoft 365 Defender para investigar e responder a ameaças com eficiência.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71052cc5a3874da250772bfa628417824ba51c63
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930076"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="0e086-103">Busca de ameaças no Explorador de Ameaças para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0e086-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0e086-104">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="0e086-104">In this article:</span></span>

- [<span data-ttu-id="0e086-105">Passo a passo do Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="0e086-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="0e086-106">Investigação de email</span><span class="sxs-lookup"><span data-stu-id="0e086-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="0e086-107">Correção de email</span><span class="sxs-lookup"><span data-stu-id="0e086-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="0e086-108">Melhorias na experiência de busca de ameaças</span><span class="sxs-lookup"><span data-stu-id="0e086-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="0e086-109">Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las). </span><span class="sxs-lookup"><span data-stu-id="0e086-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="0e086-110">Os outros dois artigos desta série são Segurança de email com [o Explorador](email-security-in-microsoft-defender.md) de Ameaças e o Explorador de Ameaças e noções [básicas de detecções em tempo real.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="0e086-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="0e086-111">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="0e086-111">**Applies to**</span></span>
- [<span data-ttu-id="0e086-112">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0e086-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0e086-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e086-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0e086-114">Se sua organização tiver [o Microsoft Defender](defender-for-office-365.md)para Office 365 , e você tiver as permissões , você poderá usar detecções do **Explorer** ou em tempo **real** para detectar e remediar ameaças. [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="0e086-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="0e086-115">No portal **Microsoft 365 Defender,** acesse **Email & colaboração** e escolha **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0e086-115">In the **Microsoft 365 Defender portal**, go to **Email & collaboration**, and then choose **Explorer**.</span></span>

<br>

****

|<span data-ttu-id="0e086-116">Com o Microsoft Defender para Office 365 Plano 2, você verá:</span><span class="sxs-lookup"><span data-stu-id="0e086-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="0e086-117">Com o Microsoft Defender para Office 365 Plano 1, consulte:</span><span class="sxs-lookup"><span data-stu-id="0e086-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Explorador de ameaças](../../media/path-to-explorer.png)|![Detecções em tempo real](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="0e086-120">Com essas ferramentas, você pode:</span><span class="sxs-lookup"><span data-stu-id="0e086-120">With these tools, you can:</span></span>

- <span data-ttu-id="0e086-121">Consulte malware detectado pelos recursos Microsoft 365 segurança</span><span class="sxs-lookup"><span data-stu-id="0e086-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="0e086-122">Exibir URL de phishing e clicar em dados de veredito</span><span class="sxs-lookup"><span data-stu-id="0e086-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="0e086-123">Iniciar um processo automatizado de investigação e resposta a partir de uma exibição no Explorer</span><span class="sxs-lookup"><span data-stu-id="0e086-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="0e086-124">Investigar emails mal-intencionados e muito mais</span><span class="sxs-lookup"><span data-stu-id="0e086-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="0e086-125">Para obter mais informações, consulte [Segurança de email com o Explorador de Ameaças.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="0e086-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="0e086-126">Passo a passo do Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="0e086-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="0e086-127">No Microsoft Defender para Office 365, há dois planos de assinatura: Plano 1 e Plano 2.</span><span class="sxs-lookup"><span data-stu-id="0e086-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="0e086-128">Ferramentas de busca de ameaças operadas manualmente existem em ambos os planos, em nomes diferentes e com diferentes recursos.</span><span class="sxs-lookup"><span data-stu-id="0e086-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="0e086-129">O Defender para Office 365 Plano 1 usa detecções em tempo *real*, que é um subconjunto da ferramenta de busca *do Explorador* de Ameaças (também chamada de *Explorer)* no Plano 2.</span><span class="sxs-lookup"><span data-stu-id="0e086-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="0e086-130">Nesta série de artigos, a maioria dos exemplos foi criada usando o Explorador de Ameaças completo.</span><span class="sxs-lookup"><span data-stu-id="0e086-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="0e086-131">Os administradores devem testar todas as etapas em detecções em tempo real para ver onde se aplicam.</span><span class="sxs-lookup"><span data-stu-id="0e086-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="0e086-132">Para abrir a ferramenta Explorer, vá para Microsoft 365 **Portal do Defender** Email & Colaboração  >    >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0e086-132">To open the Explorer tool, go to **Microsoft 365 Defender portal** > **Email & collaboration** > **Explorer**.</span></span> <span data-ttu-id="0e086-133">Por padrão, você chegará na página **Malware,** mas use a lista de opções Exibir para se familiarizar com suas opções. </span><span class="sxs-lookup"><span data-stu-id="0e086-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="0e086-134">Se você estiver procurando Phish, ou pesquisando uma campanha de ameaça, escolha esses pontos de exibição.</span><span class="sxs-lookup"><span data-stu-id="0e086-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-135">![Exibir o drop-down no Explorador de Ameaças](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-135">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="0e086-136">Uma vez que uma pessoa de operações de segurança (Operações de Sec) selecione os dados que deseja ver, se o escopo é uma exibição estreita, como **envios** do usuário, ou uma exibição mais ampla, como Todos os **emails,** pode usar o botão **Remetente** para filtrar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="0e086-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="0e086-137">Lembre-se de selecionar Atualizar para concluir suas ações de filtragem.</span><span class="sxs-lookup"><span data-stu-id="0e086-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-138">![Botão Remetente no Explorador de Ameaças](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-138">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="0e086-139">O foco de refinamento no Explorer ou na detecção em tempo real pode ser pensado em camadas.</span><span class="sxs-lookup"><span data-stu-id="0e086-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="0e086-140">O primeiro é **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="0e086-140">The first is **View**.</span></span> <span data-ttu-id="0e086-141">O segundo pode ser pensado como um *foco filtrado.*</span><span class="sxs-lookup"><span data-stu-id="0e086-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="0e086-142">Por exemplo, você pode refazer as etapas que você tomou para encontrar uma ameaça registrando suas decisões como esta: Para encontrar o problema no Explorer, eu escolhi **o Foco** de filtro De exibição de malware com um destinatário.</span><span class="sxs-lookup"><span data-stu-id="0e086-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="0e086-143">Isso facilita a retração das etapas.</span><span class="sxs-lookup"><span data-stu-id="0e086-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="0e086-144">Se o Sec Ops usar **Tags** para marcar contas que consideram destinos de alto valor, eles poderão fazer seleções como o Phish View com um foco de filtro tags (inclua um intervalo de datas, se *usado)*.</span><span class="sxs-lookup"><span data-stu-id="0e086-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="0e086-145">Isso mostrará a eles quaisquer tentativas de phishing direcionadas aos seus destinos de usuário de alto valor durante um intervalo de tempo (como datas em que determinados ataques de phishing estão ocorrendo muito para o setor).</span><span class="sxs-lookup"><span data-stu-id="0e086-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="0e086-146">Refinamentos podem ser feitos em intervalos de data usando os controles de intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="0e086-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="0e086-147">Aqui você pode ver o explorer no **ponto de exibição Malware,** com um foco de filtro **tecnologia** de detecção.</span><span class="sxs-lookup"><span data-stu-id="0e086-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="0e086-148">Mas é o botão **filtro** avançado que permite que as equipes de Operações Sec cavem profundamente.</span><span class="sxs-lookup"><span data-stu-id="0e086-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-149">![Filtro avançado no Explorador de Ameaças](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-149">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="0e086-150">Clicar no **filtro Avançado** aparece em um painel que permitirá que os caçadores de Ops Sec criem consultas por conta própria, deixando-os incluir ou excluir as informações necessárias para ver.</span><span class="sxs-lookup"><span data-stu-id="0e086-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="0e086-151">O gráfico e a tabela na página Explorer refletirão seus resultados.</span><span class="sxs-lookup"><span data-stu-id="0e086-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-152">![Resultados de uma consulta](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="0e086-153">Use o **botão Opções de** coluna para obter o tipo de informação na tabela que seria mais útil:</span><span class="sxs-lookup"><span data-stu-id="0e086-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-154">![Botão Opções de coluna realçada](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-155">![Opções disponíveis em Colunas](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-155">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="0e086-156">No mesmo mien, certifique-se de testar suas opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="0e086-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="0e086-157">Audiências diferentes reagirão bem a apresentações diferentes dos mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="0e086-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="0e086-158">Para alguns visualizadores, o **mapa Origens** do Email pode mostrar que uma ameaça é difundida ou discreta mais rapidamente do que a **opção de** exibição campanha ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="0e086-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="0e086-159">As Ops sec podem usar essas exibições para melhor fazer pontos que sublinham a necessidade de segurança e proteção, ou para comparação posterior, para demonstrar a eficácia de suas ações.</span><span class="sxs-lookup"><span data-stu-id="0e086-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-160">![Mapa de Origens de Email](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-161">![Opções de exibição de campanha](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="0e086-162">Investigação de email</span><span class="sxs-lookup"><span data-stu-id="0e086-162">Email investigation</span></span>

<span data-ttu-id="0e086-163">Quando você vir um email suspeito, clique no nome para expandir o sobrevoo à direita.</span><span class="sxs-lookup"><span data-stu-id="0e086-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="0e086-164">Aqui, o banner que permite que as Ops Sec vejam a página da entidade [de email](mdo-email-entity-page.md) está disponível.</span><span class="sxs-lookup"><span data-stu-id="0e086-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="0e086-165">A página da entidade de email reúne conteúdos que podem ser encontrados em **Detalhes,** **Anexos, Dispositivos,** mas inclui dados mais organizados.</span><span class="sxs-lookup"><span data-stu-id="0e086-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="0e086-166">Isso inclui coisas como resultados DMARC, exibição simples de texto do header de email com uma opção de cópia, informações de veredito sobre anexos que foram detonados com segurança e arquivos que essas detonações foram descartados (pode incluir endereços IP que foram contatados e capturas de tela de páginas ou arquivos).</span><span class="sxs-lookup"><span data-stu-id="0e086-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="0e086-167">URLs e seus vereditos também são listados com detalhes semelhantes relatados.</span><span class="sxs-lookup"><span data-stu-id="0e086-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="0e086-168">Quando você chegar a esse estágio, a página da entidade de email será fundamental para a etapa final:*correção*.</span><span class="sxs-lookup"><span data-stu-id="0e086-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-169">![A página entidade de email](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="0e086-170">Para saber mais sobre a página de  entidade rich email (vista abaixo na guia Análise), incluindo os resultados de Anexos detonados, descobertas para URLs incluídas e visualização de email seguro, clique [aqui](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="0e086-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-171">![Guia Análise da página entidade de email](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="0e086-172">Correção de email</span><span class="sxs-lookup"><span data-stu-id="0e086-172">Email remediation</span></span>

<span data-ttu-id="0e086-173">Depois que uma pessoa de Operações da Sec determina que um email é uma ameaça, a próxima etapa de detecção do Explorer ou em tempo real está lidando com a ameaça e remediando-a.</span><span class="sxs-lookup"><span data-stu-id="0e086-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="0e086-174">Isso pode ser feito retornando ao Explorador de Ameaças, selecionando a caixa de seleção para o email do problema e usando o **botão Ações.**</span><span class="sxs-lookup"><span data-stu-id="0e086-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-175">![Botão Ações no Explorador de Ameaças](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="0e086-176">Aqui, o analista pode tomar ações como relatar o email como Spam, Phishing ou Malware, contatar destinatários ou outras investigações que podem incluir a acionamento de cartilhas de Investigação e Resposta Automatizada (ou AIR) (se você tiver o Plano 2).</span><span class="sxs-lookup"><span data-stu-id="0e086-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="0e086-177">Ou, o email também pode ser relatado como limpo.</span><span class="sxs-lookup"><span data-stu-id="0e086-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-178">![A lista de ações listada](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="0e086-179">Melhorias na experiência de busca de ameaças</span><span class="sxs-lookup"><span data-stu-id="0e086-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="0e086-180">ID do alerta</span><span class="sxs-lookup"><span data-stu-id="0e086-180">Alert ID</span></span>

<span data-ttu-id="0e086-181">Ao navegar de um alerta para o Explorador de Ameaças, o **View** será filtrado pela **ID do Alerta.**</span><span class="sxs-lookup"><span data-stu-id="0e086-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="0e086-182">Isso também se aplica à detecção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="0e086-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="0e086-183">As mensagens relevantes para o alerta específico e um total de emails (uma contagem) são mostradas.</span><span class="sxs-lookup"><span data-stu-id="0e086-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="0e086-184">Você poderá ver se uma mensagem fazia parte de um alerta, bem como navegar dessa mensagem para o alerta relacionado.</span><span class="sxs-lookup"><span data-stu-id="0e086-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="0e086-185">Por fim, a ID do alerta está incluída na URL, por exemplo: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="0e086-185">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-186">![Filtragem para ID de alerta](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-187">![ID do alerta no sobremenu de detalhes](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="0e086-188">Extensão do Explorer (e detecções em tempo real) e limite de pesquisa para locatários de avaliação</span><span class="sxs-lookup"><span data-stu-id="0e086-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="0e086-189">Como parte dessa alteração, os analistas poderão pesquisar e filtrar dados de email por 30 dias (aumento de sete dias) no Explorador de Ameaças e detecções em tempo real para os locatários de avaliação do Defender para Office P1 e P2.</span><span class="sxs-lookup"><span data-stu-id="0e086-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="0e086-190">Isso não afeta locatários de produção para clientes P1 e P2 E5, onde o padrão de retenção já é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="0e086-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="0e086-191">Limite de exportação atualizado</span><span class="sxs-lookup"><span data-stu-id="0e086-191">Updated Export limit</span></span> 

<span data-ttu-id="0e086-192">O número de registros de Emails que podem ser exportados do Explorador de Ameaças agora é 200.000 (era 9990).</span><span class="sxs-lookup"><span data-stu-id="0e086-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="0e086-193">O conjunto de colunas que pode ser exportado não mudou.</span><span class="sxs-lookup"><span data-stu-id="0e086-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="0e086-194">Marcas no Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="0e086-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="0e086-195">O recurso de marcas de usuário está em Visualização e pode não estar disponível para todos.</span><span class="sxs-lookup"><span data-stu-id="0e086-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="0e086-196">Além disso, as visualizações estão sujeitas a alterações.</span><span class="sxs-lookup"><span data-stu-id="0e086-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="0e086-197">Para obter informações sobre o cronograma de lançamento, confira o Microsoft 365 de lançamento.</span><span class="sxs-lookup"><span data-stu-id="0e086-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="0e086-198">As marcas de usuário identificam grupos específicos de usuários no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e086-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0e086-199">Para obter mais informações sobre marcas, incluindo licenciamento e configuração, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="0e086-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="0e086-200">No Explorador de Ameaças, você pode ver informações sobre marcas de usuário nas experiências a seguir.</span><span class="sxs-lookup"><span data-stu-id="0e086-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="0e086-201">Exibição de grade de email</span><span class="sxs-lookup"><span data-stu-id="0e086-201">Email grid view</span></span>

<span data-ttu-id="0e086-202">Quando os analistas olham para a coluna **Marcas** da grade de email, eles estão vendo todas as marcas que foram aplicadas a caixas de correio de remetente ou destinatário.</span><span class="sxs-lookup"><span data-stu-id="0e086-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="0e086-203">Por padrão, as marcas do sistema, como *contas de prioridade,* são mostradas primeiro.</span><span class="sxs-lookup"><span data-stu-id="0e086-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-204">![Marcas de filtro no exibição de grade de email](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="0e086-205">Filtragem</span><span class="sxs-lookup"><span data-stu-id="0e086-205">Filtering</span></span>

<span data-ttu-id="0e086-206">As marcas podem ser usadas como filtros.</span><span class="sxs-lookup"><span data-stu-id="0e086-206">Tags can be used as filters.</span></span> <span data-ttu-id="0e086-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span><span class="sxs-lookup"><span data-stu-id="0e086-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="0e086-208">Você também pode excluir resultados que tenham determinadas marcas.</span><span class="sxs-lookup"><span data-stu-id="0e086-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="0e086-209">Combine marcas com outros filtros e intervalos de datas para restringir seu escopo de investigação.</span><span class="sxs-lookup"><span data-stu-id="0e086-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="0e086-210">[![Marcas de filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0e086-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-211">![Não marcas de filtro](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="0e086-212">Sobremenu de detalhes de email</span><span class="sxs-lookup"><span data-stu-id="0e086-212">Email detail flyout</span></span>

<span data-ttu-id="0e086-213">Para exibir as marcas individuais de remetente e destinatário, selecione um email para abrir o sobremenu de detalhes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="0e086-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="0e086-214">Na guia **Resumo,** as marcas remetente e destinatário são mostradas separadamente.</span><span class="sxs-lookup"><span data-stu-id="0e086-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="0e086-215">As informações sobre marcas individuais para remetente e destinatário podem ser exportadas como dados CSV.</span><span class="sxs-lookup"><span data-stu-id="0e086-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-216">![Marcas de detalhes de email](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="0e086-217">As informações de marcas também são mostradas no flyout de cliques da URL.</span><span class="sxs-lookup"><span data-stu-id="0e086-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="0e086-218">Para vê-lo, vá para Phish or All Email view > **URLs** ou **URL Clicks** tab. Selecione um flyout de URL individual para ver detalhes adicionais sobre cliques para essa URL, incluindo todas as Marcas associadas a esse clique.</span><span class="sxs-lookup"><span data-stu-id="0e086-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="0e086-219">Exibição de linha do tempo atualizada</span><span class="sxs-lookup"><span data-stu-id="0e086-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-220">![Marcas de URL](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="0e086-221">Saiba mais assistindo a [este vídeo](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span><span class="sxs-lookup"><span data-stu-id="0e086-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="0e086-222">Recursos estendidos</span><span class="sxs-lookup"><span data-stu-id="0e086-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="0e086-223">Principais usuários direcionados</span><span class="sxs-lookup"><span data-stu-id="0e086-223">Top targeted users</span></span>

<span data-ttu-id="0e086-224">As Principais Famílias de Malware mostram os principais usuários **direcionados** na seção Malware.</span><span class="sxs-lookup"><span data-stu-id="0e086-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="0e086-225">Os principais usuários direcionados também serão estendidos por meio de exibições phishing e Todos os emails.</span><span class="sxs-lookup"><span data-stu-id="0e086-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="0e086-226">Os analistas poderão ver os cinco principais usuários direcionados, juntamente com o número de tentativas para cada usuário em cada exibição.</span><span class="sxs-lookup"><span data-stu-id="0e086-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="0e086-227">As pessoas de operações de segurança podem exportar a lista de usuários direcionados, até um limite de 3.000, juntamente com o número de tentativas feitas, para análise offline para cada modo de exibição de email.</span><span class="sxs-lookup"><span data-stu-id="0e086-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="0e086-228">Além disso, selecionar o número de tentativas (por exemplo, 13 tentativas na imagem abaixo) abrirá um modo de exibição filtrado no Explorador de Ameaças, para que você possa ver mais detalhes em emails e ameaças para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="0e086-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-229">![Principais usuários direcionados](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="0e086-230">Exchange de transporte</span><span class="sxs-lookup"><span data-stu-id="0e086-230">Exchange transport rules</span></span>

<span data-ttu-id="0e086-231">A equipe de operações de segurança poderá ver todas as regras de Exchange de transporte (ou regras de fluxo de email) aplicadas a uma mensagem, na exibição grade Email.</span><span class="sxs-lookup"><span data-stu-id="0e086-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="0e086-232">Selecione **Opções de** coluna na grade e, em seguida, adicione Exchange Regra de **Transporte** nas opções de coluna.</span><span class="sxs-lookup"><span data-stu-id="0e086-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="0e086-233">A Exchange de regras de transporte também está visível no **sobremenu de detalhes** no email.</span><span class="sxs-lookup"><span data-stu-id="0e086-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="0e086-234">Os nomes e GUIDs das regras de transporte aplicadas à mensagem são exibidos.</span><span class="sxs-lookup"><span data-stu-id="0e086-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="0e086-235">Os analistas poderão pesquisar mensagens usando o nome da regra de transporte.</span><span class="sxs-lookup"><span data-stu-id="0e086-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="0e086-236">Esta é uma pesquisa CONTAINS, o que significa que você também pode fazer pesquisas parciais.</span><span class="sxs-lookup"><span data-stu-id="0e086-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0e086-237">Exchange de pesquisa de regra de transporte e disponibilidade de nome dependem da função específica atribuída a você.</span><span class="sxs-lookup"><span data-stu-id="0e086-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="0e086-238">Você precisa ter uma das seguintes funções ou permissões para exibir os nomes das regras de transporte e a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0e086-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="0e086-239">No entanto, mesmo sem as funções ou permissões abaixo, um analista pode ver o rótulo de regra de transporte e informações guid nos Detalhes do Email.</span><span class="sxs-lookup"><span data-stu-id="0e086-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="0e086-240">Outras experiências de visualização de registro em Grades de Email, Sub-sub-sublhsados de email, Filtros e Exportação não são afetadas.</span><span class="sxs-lookup"><span data-stu-id="0e086-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="0e086-241">Exchange Online Somente - Prevenção contra Perda de Dados: Todos</span><span class="sxs-lookup"><span data-stu-id="0e086-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="0e086-242">Exchange Online Somente - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="0e086-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="0e086-243">Microsoft Azure Active Directory ou Exchange Online - Administrador de Segurança: Todos</span><span class="sxs-lookup"><span data-stu-id="0e086-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="0e086-244">Azure Active Directory ou Exchange Online - Leitor de Segurança: Tudo</span><span class="sxs-lookup"><span data-stu-id="0e086-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="0e086-245">Exchange Online Somente - Regras de Transporte: Todos</span><span class="sxs-lookup"><span data-stu-id="0e086-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="0e086-246">Exchange Online Somente - View-Only Configuração: Tudo</span><span class="sxs-lookup"><span data-stu-id="0e086-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="0e086-247">Na grade de email, sobremenos e CSV exportados, os ETRs são apresentados com um Nome/GUID, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="0e086-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="0e086-248">![Exchange Regras de Transporte](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="0e086-249">Conectores de entrada</span><span class="sxs-lookup"><span data-stu-id="0e086-249">Inbound connectors</span></span>

<span data-ttu-id="0e086-250">Conectores são uma coleção de instruções que personalizam como seu email flui de e para sua Microsoft 365 ou Office 365 organização.</span><span class="sxs-lookup"><span data-stu-id="0e086-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="0e086-251">Eles permitem que você aplique quaisquer restrições ou controles de segurança.</span><span class="sxs-lookup"><span data-stu-id="0e086-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="0e086-252">No Explorador de Ameaças, você pode exibir os conectores relacionados a um email e pesquisar emails usando nomes de conectores.</span><span class="sxs-lookup"><span data-stu-id="0e086-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="0e086-253">A pesquisa por conectores é uma consulta CONTAINS, o que significa que pesquisas parciais de palavra-chave podem funcionar:</span><span class="sxs-lookup"><span data-stu-id="0e086-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e086-254">![Detalhes do conector](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="0e086-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="0e086-255">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="0e086-255">Required licenses and permissions</span></span>

<span data-ttu-id="0e086-256">Você deve ter [o Microsoft Defender para Office 365](defender-for-office-365.md) usar detecções do Explorer ou em tempo real.</span><span class="sxs-lookup"><span data-stu-id="0e086-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="0e086-257">O Explorer está incluído no Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="0e086-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="0e086-258">O relatório de detecções em tempo real está incluído no Defender para Office 365 Plano 1.</span><span class="sxs-lookup"><span data-stu-id="0e086-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="0e086-259">Planeje atribuir licenças para todos os usuários que devem ser protegidos pelo Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e086-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="0e086-260">As detecções do Explorer e em tempo real mostram dados de detecção para usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="0e086-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="0e086-261">Para exibir e usar detecções do Explorer ou em tempo real, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0e086-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="0e086-262">Para o portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="0e086-262">For the Microsoft 365 Defender portal:</span></span>

  - <span data-ttu-id="0e086-263">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="0e086-263">Organization Management</span></span>
  - <span data-ttu-id="0e086-264">Administrador de Segurança (isso pode ser atribuído no Azure Active Directory de administração ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="0e086-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="0e086-265">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="0e086-265">Security Reader</span></span>

- <span data-ttu-id="0e086-266">Para Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0e086-266">For Exchange Online:</span></span>

  - <span data-ttu-id="0e086-267">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="0e086-267">Organization Management</span></span>
  - <span data-ttu-id="0e086-268">Gerenciamento de Organização Somente Exibição</span><span class="sxs-lookup"><span data-stu-id="0e086-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="0e086-269">Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="0e086-269">View-Only Recipients</span></span>
  - <span data-ttu-id="0e086-270">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="0e086-270">Compliance Management</span></span>

<span data-ttu-id="0e086-271">Para saber mais sobre funções e permissões, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="0e086-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="0e086-272">Permissões no portal do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e086-272">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="0e086-273">Permissões de recursos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e086-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="0e086-274">PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0e086-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="0e086-275">Mais Informações</span><span class="sxs-lookup"><span data-stu-id="0e086-275">More information</span></span>

- [<span data-ttu-id="0e086-276">Localizar e investigar emails mal-intencionados entregues</span><span class="sxs-lookup"><span data-stu-id="0e086-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="0e086-277">Exibir arquivos mal-intencionados detectados no SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e086-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="0e086-278">Obter uma visão geral dos exibições no Explorador de Ameaças (e detecções em tempo real)</span><span class="sxs-lookup"><span data-stu-id="0e086-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="0e086-279">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="0e086-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="0e086-280">Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e086-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="0e086-281">Investigar emails com a página Entidade de Email</span><span class="sxs-lookup"><span data-stu-id="0e086-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)