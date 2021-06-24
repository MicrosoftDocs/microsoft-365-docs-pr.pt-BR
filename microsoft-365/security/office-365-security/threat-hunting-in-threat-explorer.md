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
ms.openlocfilehash: 0ad5d73abae71cc7cc00e12665d96b2020da0c41
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105424"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="a6cba-103">Busca de ameaças no Explorador de Ameaças para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a6cba-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a6cba-104">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="a6cba-104">In this article:</span></span>

- [<span data-ttu-id="a6cba-105">Passo a passo do Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="a6cba-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="a6cba-106">Investigação de email</span><span class="sxs-lookup"><span data-stu-id="a6cba-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="a6cba-107">Correção de email</span><span class="sxs-lookup"><span data-stu-id="a6cba-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="a6cba-108">Melhorias na experiência de busca de ameaças</span><span class="sxs-lookup"><span data-stu-id="a6cba-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="a6cba-109">Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las). </span><span class="sxs-lookup"><span data-stu-id="a6cba-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="a6cba-110">Os outros dois artigos desta série são Segurança de email com [o Explorador](email-security-in-microsoft-defender.md) de Ameaças e o Explorador de Ameaças e noções [básicas de detecções em tempo real.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="a6cba-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="a6cba-111">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a6cba-111">**Applies to**</span></span>
- [<span data-ttu-id="a6cba-112">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a6cba-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a6cba-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6cba-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a6cba-114">Se sua organização tiver [o Microsoft Defender](defender-for-office-365.md)para Office 365 , e você tiver as permissões , você poderá usar detecções do **Explorer** ou em tempo **real** para detectar e remediar ameaças. [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="a6cba-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="a6cba-115">No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), acesse **Email & colaboração** e escolha **Explorer** ou **Detecções em tempo real**.</span><span class="sxs-lookup"><span data-stu-id="a6cba-115">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** or **Real-time detections**.</span></span> <span data-ttu-id="a6cba-116">Para fazer diretamente à página, use <https://security.microsoft.com/threatexplorer> ou <https://security.microsoft.com/realtimereports></span><span class="sxs-lookup"><span data-stu-id="a6cba-116">To do directly to the page, use <https://security.microsoft.com/threatexplorer> or <https://security.microsoft.com/realtimereports></span></span>

<span data-ttu-id="a6cba-117">Com essas ferramentas, você pode:</span><span class="sxs-lookup"><span data-stu-id="a6cba-117">With these tools, you can:</span></span>

- <span data-ttu-id="a6cba-118">Consulte malware detectado pelos recursos Microsoft 365 segurança</span><span class="sxs-lookup"><span data-stu-id="a6cba-118">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="a6cba-119">Exibir URL de phishing e clicar em dados de veredito</span><span class="sxs-lookup"><span data-stu-id="a6cba-119">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="a6cba-120">Iniciar um processo automatizado de investigação e resposta a partir de uma exibição no Explorer</span><span class="sxs-lookup"><span data-stu-id="a6cba-120">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="a6cba-121">Investigar emails mal-intencionados e muito mais</span><span class="sxs-lookup"><span data-stu-id="a6cba-121">Investigate malicious email, and more</span></span>

<span data-ttu-id="a6cba-122">Para obter mais informações, consulte [Segurança de email com o Explorador de Ameaças.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="a6cba-122">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="a6cba-123">Passo a passo do Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="a6cba-123">Threat Explorer walk-through</span></span>

<span data-ttu-id="a6cba-124">No Microsoft Defender para Office 365, há dois planos de assinatura: Plano 1 e Plano 2.</span><span class="sxs-lookup"><span data-stu-id="a6cba-124">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="a6cba-125">Ferramentas de busca de ameaças operadas manualmente existem em ambos os planos, em nomes diferentes e com diferentes recursos.</span><span class="sxs-lookup"><span data-stu-id="a6cba-125">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="a6cba-126">O Defender para Office 365 Plano 1 usa detecções em tempo *real*, que é um subconjunto da ferramenta de busca *do Explorador* de Ameaças (também chamada de *Explorer)* no Plano 2.</span><span class="sxs-lookup"><span data-stu-id="a6cba-126">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="a6cba-127">Nesta série de artigos, a maioria dos exemplos foi criada usando o Explorador de Ameaças completo.</span><span class="sxs-lookup"><span data-stu-id="a6cba-127">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="a6cba-128">Os administradores devem testar todas as etapas em detecções em tempo real para ver onde se aplicam.</span><span class="sxs-lookup"><span data-stu-id="a6cba-128">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="a6cba-129">Depois de ir para **o Explorer**, por padrão, você  chegará na página **Malware,** mas use a lista de menus exibir para se familiarizar com suas opções.</span><span class="sxs-lookup"><span data-stu-id="a6cba-129">After you go to **Explorer**, by default, you'll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="a6cba-130">Se você estiver procurando Phish, ou pesquisando uma campanha de ameaça, escolha esses pontos de exibição.</span><span class="sxs-lookup"><span data-stu-id="a6cba-130">If you're hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-131">![Exibir o drop-down no Explorador de Ameaças](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-131">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="a6cba-132">Uma vez que uma pessoa de operações de segurança (Operações de Sec) selecione os dados que deseja ver, se o escopo é uma exibição estreita, como **envios** do usuário, ou uma exibição mais ampla, como Todos os **emails,** pode usar o botão **Remetente** para filtrar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="a6cba-132">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="a6cba-133">Lembre-se de selecionar Atualizar para concluir suas ações de filtragem.</span><span class="sxs-lookup"><span data-stu-id="a6cba-133">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-134">![Botão Remetente no Explorador de Ameaças](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-134">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="a6cba-135">O foco de refinamento no Explorer ou na detecção em tempo real pode ser pensado em camadas.</span><span class="sxs-lookup"><span data-stu-id="a6cba-135">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="a6cba-136">O primeiro é **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="a6cba-136">The first is **View**.</span></span> <span data-ttu-id="a6cba-137">O segundo pode ser pensado como um *foco filtrado.*</span><span class="sxs-lookup"><span data-stu-id="a6cba-137">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="a6cba-138">Por exemplo, você pode refazer as etapas que você tomou para encontrar uma ameaça registrando suas decisões como esta: Para encontrar o problema no Explorer, eu escolhi **o Foco** de filtro De exibição de malware com um destinatário.</span><span class="sxs-lookup"><span data-stu-id="a6cba-138">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="a6cba-139">Isso facilita a retração das etapas.</span><span class="sxs-lookup"><span data-stu-id="a6cba-139">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="a6cba-140">Se o Sec Ops usar **Tags** para marcar contas que consideram destinos de alto valor, eles poderão fazer seleções como o Phish View com um foco de filtro tags (inclua um intervalo de datas, se *usado)*.</span><span class="sxs-lookup"><span data-stu-id="a6cba-140">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="a6cba-141">Isso mostrará a eles quaisquer tentativas de phishing direcionadas aos seus destinos de usuário de alto valor durante um intervalo de tempo (como datas em que determinados ataques de phishing estão ocorrendo muito para o setor).</span><span class="sxs-lookup"><span data-stu-id="a6cba-141">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span>

<span data-ttu-id="a6cba-142">Refinamentos podem ser feitos em intervalos de data usando os controles de intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="a6cba-142">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="a6cba-143">Aqui você pode ver o explorer no **ponto de exibição Malware,** com um foco de filtro **tecnologia** de detecção.</span><span class="sxs-lookup"><span data-stu-id="a6cba-143">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="a6cba-144">Mas é o botão **filtro** avançado que permite que as equipes de Operações Sec cavem profundamente.</span><span class="sxs-lookup"><span data-stu-id="a6cba-144">But it's the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-145">![Filtro avançado no Explorador de Ameaças](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-145">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="a6cba-146">Clicar no **filtro Avançado** aparece em um painel que permitirá que os caçadores de Ops Sec criem consultas por conta própria, deixando-os incluir ou excluir as informações necessárias para ver.</span><span class="sxs-lookup"><span data-stu-id="a6cba-146">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="a6cba-147">O gráfico e a tabela na página Explorer refletirão seus resultados.</span><span class="sxs-lookup"><span data-stu-id="a6cba-147">Both the chart and table on the Explorer page will reflect their results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-148">![Resultados de uma consulta](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-148">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="a6cba-149">Use o **botão Opções de** coluna para obter o tipo de informação na tabela que seria mais útil:</span><span class="sxs-lookup"><span data-stu-id="a6cba-149">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-150">![Botão Opções de coluna realçada](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-150">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-151">![Opções disponíveis em Colunas](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-151">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="a6cba-152">No mesmo mien, certifique-se de testar suas opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="a6cba-152">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="a6cba-153">Audiências diferentes reagirão bem a apresentações diferentes dos mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="a6cba-153">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="a6cba-154">Para alguns visualizadores, o **mapa Origens** do Email pode mostrar que uma ameaça é difundida ou discreta mais rapidamente do que a **opção de** exibição campanha ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="a6cba-154">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="a6cba-155">As Ops sec podem usar essas exibições para melhor fazer pontos que sublinham a necessidade de segurança e proteção, ou para comparação posterior, para demonstrar a eficácia de suas ações.</span><span class="sxs-lookup"><span data-stu-id="a6cba-155">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-156">![Mapa de Origens de Email](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-156">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-157">![Opções de exibição de campanha](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-157">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="a6cba-158">Investigação de email</span><span class="sxs-lookup"><span data-stu-id="a6cba-158">Email investigation</span></span>

<span data-ttu-id="a6cba-159">Quando você vir um email suspeito, clique no nome para expandir o sobrevoo à direita.</span><span class="sxs-lookup"><span data-stu-id="a6cba-159">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="a6cba-160">Aqui, o banner que permite que as Ops Sec vejam a página da entidade [de email](mdo-email-entity-page.md) está disponível.</span><span class="sxs-lookup"><span data-stu-id="a6cba-160">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="a6cba-161">A página da entidade de email reúne conteúdos que podem ser encontrados em **Detalhes,** **Anexos, Dispositivos,** mas inclui dados mais organizados.</span><span class="sxs-lookup"><span data-stu-id="a6cba-161">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="a6cba-162">Isso inclui coisas como resultados DMARC, exibição simples de texto do header de email com uma opção de cópia, informações de veredito sobre anexos que foram detonados com segurança e arquivos que essas detonações foram descartados (pode incluir endereços IP que foram contatados e capturas de tela de páginas ou arquivos).</span><span class="sxs-lookup"><span data-stu-id="a6cba-162">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="a6cba-163">URLs e seus vereditos também são listados com detalhes semelhantes relatados.</span><span class="sxs-lookup"><span data-stu-id="a6cba-163">URLs and their verdicts are also listed with similar details reported.</span></span>

<span data-ttu-id="a6cba-164">Quando você chegar a esse estágio, a página da entidade de email será fundamental para a etapa final:*correção*.</span><span class="sxs-lookup"><span data-stu-id="a6cba-164">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-165">![A página entidade de email](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-165">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="a6cba-166">Para saber mais sobre a página de  entidade rich email (vista abaixo na guia Análise), incluindo os resultados de Anexos detonados, descobertas para URLs incluídas e visualização de email seguro, clique [aqui](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="a6cba-166">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-167">![Guia Análise da página entidade de email](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-167">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="a6cba-168">Correção de email</span><span class="sxs-lookup"><span data-stu-id="a6cba-168">Email remediation</span></span>

<span data-ttu-id="a6cba-169">Depois que uma pessoa de Operações da Sec determina que um email é uma ameaça, a próxima etapa de detecção do Explorer ou em tempo real está lidando com a ameaça e remediando-a.</span><span class="sxs-lookup"><span data-stu-id="a6cba-169">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="a6cba-170">Isso pode ser feito retornando ao Explorador de Ameaças, selecionando a caixa de seleção para o email do problema e usando o **botão Ações.**</span><span class="sxs-lookup"><span data-stu-id="a6cba-170">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-171">![Botão Ações no Explorador de Ameaças](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-171">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="a6cba-172">Aqui, o analista pode tomar ações como relatar o email como Spam, Phishing ou Malware, contatar destinatários ou outras investigações que podem incluir a acionamento de cartilhas de Investigação e Resposta Automatizada (ou AIR) (se você tiver o Plano 2).</span><span class="sxs-lookup"><span data-stu-id="a6cba-172">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="a6cba-173">Ou, o email também pode ser relatado como limpo.</span><span class="sxs-lookup"><span data-stu-id="a6cba-173">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-174">![A lista de ações listada](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-174">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="a6cba-175">Melhorias na experiência de busca de ameaças</span><span class="sxs-lookup"><span data-stu-id="a6cba-175">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="a6cba-176">ID do alerta</span><span class="sxs-lookup"><span data-stu-id="a6cba-176">Alert ID</span></span>

<span data-ttu-id="a6cba-177">Ao navegar de um alerta para o Explorador de Ameaças, o **View** será filtrado pela **ID do Alerta.**</span><span class="sxs-lookup"><span data-stu-id="a6cba-177">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="a6cba-178">Isso também se aplica à detecção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="a6cba-178">This also applies in Real-time detection.</span></span> <span data-ttu-id="a6cba-179">As mensagens relevantes para o alerta específico e um total de emails (uma contagem) são mostradas.</span><span class="sxs-lookup"><span data-stu-id="a6cba-179">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="a6cba-180">Você poderá ver se uma mensagem fazia parte de um alerta, bem como navegar dessa mensagem para o alerta relacionado.</span><span class="sxs-lookup"><span data-stu-id="a6cba-180">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="a6cba-181">Por fim, a ID do alerta está incluída na URL, por exemplo: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="a6cba-181">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-182">![Filtragem para ID de alerta](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-182">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-183">![ID do alerta no sobremenu de detalhes](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-183">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="a6cba-184">Extensão do Explorer (e detecções em tempo real) e limite de pesquisa para locatários de avaliação</span><span class="sxs-lookup"><span data-stu-id="a6cba-184">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span>

<span data-ttu-id="a6cba-185">Como parte dessa alteração, os analistas poderão pesquisar e filtrar dados de email por 30 dias (aumento de sete dias) no Explorador de Ameaças e detecções em tempo real para os locatários de avaliação do Defender para Office P1 e P2.</span><span class="sxs-lookup"><span data-stu-id="a6cba-185">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="a6cba-186">Isso não afeta locatários de produção para clientes P1 e P2 E5, onde o padrão de retenção já é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a6cba-186">This doesn't impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="a6cba-187">Limite de exportação atualizado</span><span class="sxs-lookup"><span data-stu-id="a6cba-187">Updated Export limit</span></span>

<span data-ttu-id="a6cba-188">O número de registros de Emails que podem ser exportados do Explorador de Ameaças agora é 200.000 (era 9990).</span><span class="sxs-lookup"><span data-stu-id="a6cba-188">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="a6cba-189">O conjunto de colunas que pode ser exportado não mudou.</span><span class="sxs-lookup"><span data-stu-id="a6cba-189">The set of columns that can be exported is unchanged.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="a6cba-190">Marcas no Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="a6cba-190">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="a6cba-191">O recurso de marcas de usuário está em Visualização e pode não estar disponível para todos.</span><span class="sxs-lookup"><span data-stu-id="a6cba-191">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="a6cba-192">Além disso, as visualizações estão sujeitas a alterações.</span><span class="sxs-lookup"><span data-stu-id="a6cba-192">Also, Previews are subject to change.</span></span> <span data-ttu-id="a6cba-193">Para obter informações sobre o cronograma de lançamento, confira o Microsoft 365 de lançamento.</span><span class="sxs-lookup"><span data-stu-id="a6cba-193">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="a6cba-194">As marcas de usuário identificam grupos específicos de usuários no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6cba-194">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a6cba-195">Para obter mais informações sobre marcas, incluindo licenciamento e configuração, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="a6cba-195">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="a6cba-196">No Explorador de Ameaças, você pode ver informações sobre marcas de usuário nas experiências a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6cba-196">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="a6cba-197">Exibição de grade de email</span><span class="sxs-lookup"><span data-stu-id="a6cba-197">Email grid view</span></span>

<span data-ttu-id="a6cba-198">Quando os analistas olham para a coluna **Marcas** da grade de email, eles estão vendo todas as marcas que foram aplicadas a caixas de correio de remetente ou destinatário.</span><span class="sxs-lookup"><span data-stu-id="a6cba-198">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="a6cba-199">Por padrão, as marcas do sistema, como *contas de prioridade,* são mostradas primeiro.</span><span class="sxs-lookup"><span data-stu-id="a6cba-199">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-200">![Marcas de filtro no exibição de grade de email](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-200">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="a6cba-201">Filtragem</span><span class="sxs-lookup"><span data-stu-id="a6cba-201">Filtering</span></span>

<span data-ttu-id="a6cba-202">As marcas podem ser usadas como filtros.</span><span class="sxs-lookup"><span data-stu-id="a6cba-202">Tags can be used as filters.</span></span> <span data-ttu-id="a6cba-203">Hunt among priority accounts only, or use specific user tags scenarios this way.</span><span class="sxs-lookup"><span data-stu-id="a6cba-203">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="a6cba-204">Você também pode excluir resultados que tenham determinadas marcas.</span><span class="sxs-lookup"><span data-stu-id="a6cba-204">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="a6cba-205">Combine marcas com outros filtros e intervalos de datas para restringir seu escopo de investigação.</span><span class="sxs-lookup"><span data-stu-id="a6cba-205">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span>

<span data-ttu-id="a6cba-206">[![Marcas de filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a6cba-206">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-207">![Não marcas de filtro](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-207">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="a6cba-208">Sobremenu de detalhes de email</span><span class="sxs-lookup"><span data-stu-id="a6cba-208">Email detail flyout</span></span>

<span data-ttu-id="a6cba-209">Para exibir as marcas individuais de remetente e destinatário, selecione um email para abrir o sobremenu de detalhes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a6cba-209">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="a6cba-210">Na guia **Resumo,** as marcas remetente e destinatário são mostradas separadamente.</span><span class="sxs-lookup"><span data-stu-id="a6cba-210">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="a6cba-211">As informações sobre marcas individuais para remetente e destinatário podem ser exportadas como dados CSV.</span><span class="sxs-lookup"><span data-stu-id="a6cba-211">The information about individual tags for sender and recipient can be exported as CSV data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-212">![Marcas de detalhes de email](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-212">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="a6cba-213">As informações de marcas também são mostradas no flyout de cliques da URL.</span><span class="sxs-lookup"><span data-stu-id="a6cba-213">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="a6cba-214">Para vê-lo, vá para Phish or All Email view > **URLs** ou **URL Clicks** tab. Selecione um flyout de URL individual para ver detalhes adicionais sobre cliques para essa URL, incluindo todas as Marcas associadas a esse clique.</span><span class="sxs-lookup"><span data-stu-id="a6cba-214">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="a6cba-215">Exibição de linha do tempo atualizada</span><span class="sxs-lookup"><span data-stu-id="a6cba-215">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-216">![Marcas de URL](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-216">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="a6cba-217">Saiba mais assistindo a [este vídeo](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span><span class="sxs-lookup"><span data-stu-id="a6cba-217">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="a6cba-218">Recursos estendidos</span><span class="sxs-lookup"><span data-stu-id="a6cba-218">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="a6cba-219">Principais usuários direcionados</span><span class="sxs-lookup"><span data-stu-id="a6cba-219">Top targeted users</span></span>

<span data-ttu-id="a6cba-220">As Principais Famílias de Malware mostram os principais usuários **direcionados** na seção Malware.</span><span class="sxs-lookup"><span data-stu-id="a6cba-220">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="a6cba-221">Os principais usuários direcionados também serão estendidos por meio de exibições phishing e Todos os emails.</span><span class="sxs-lookup"><span data-stu-id="a6cba-221">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="a6cba-222">Os analistas poderão ver os cinco principais usuários direcionados, juntamente com o número de tentativas para cada usuário em cada exibição.</span><span class="sxs-lookup"><span data-stu-id="a6cba-222">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span>

<span data-ttu-id="a6cba-223">As pessoas de operações de segurança podem exportar a lista de usuários direcionados, até um limite de 3.000, juntamente com o número de tentativas feitas, para análise offline para cada modo de exibição de email.</span><span class="sxs-lookup"><span data-stu-id="a6cba-223">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="a6cba-224">Além disso, selecionar o número de tentativas (por exemplo, 13 tentativas na imagem abaixo) abrirá um modo de exibição filtrado no Explorador de Ameaças, para que você possa ver mais detalhes em emails e ameaças para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="a6cba-224">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-225">![Principais usuários direcionados](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-225">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="a6cba-226">Exchange de transporte</span><span class="sxs-lookup"><span data-stu-id="a6cba-226">Exchange transport rules</span></span>

<span data-ttu-id="a6cba-227">A equipe de operações de segurança poderá ver todas as regras de Exchange de transporte (ou regras de fluxo de email) aplicadas a uma mensagem, na exibição grade Email.</span><span class="sxs-lookup"><span data-stu-id="a6cba-227">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="a6cba-228">Selecione **Opções de** coluna na grade e, em seguida, adicione Exchange Regra de **Transporte** nas opções de coluna.</span><span class="sxs-lookup"><span data-stu-id="a6cba-228">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="a6cba-229">A Exchange de regras de transporte também está visível no **sobremenu de detalhes** no email.</span><span class="sxs-lookup"><span data-stu-id="a6cba-229">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="a6cba-230">Os nomes e GUIDs das regras de transporte aplicadas à mensagem são exibidos.</span><span class="sxs-lookup"><span data-stu-id="a6cba-230">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="a6cba-231">Os analistas poderão pesquisar mensagens usando o nome da regra de transporte.</span><span class="sxs-lookup"><span data-stu-id="a6cba-231">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="a6cba-232">Esta é uma pesquisa CONTAINS, o que significa que você também pode fazer pesquisas parciais.</span><span class="sxs-lookup"><span data-stu-id="a6cba-232">This is a CONTAINS search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6cba-233">Exchange de pesquisa de regra de transporte e disponibilidade de nome dependem da função específica atribuída a você.</span><span class="sxs-lookup"><span data-stu-id="a6cba-233">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="a6cba-234">Você precisa ter uma das seguintes funções ou permissões para exibir os nomes das regras de transporte e a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6cba-234">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="a6cba-235">No entanto, mesmo sem as funções ou permissões abaixo, um analista pode ver o rótulo de regra de transporte e informações guid nos Detalhes do Email.</span><span class="sxs-lookup"><span data-stu-id="a6cba-235">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="a6cba-236">Outras experiências de visualização de registro em Grades de Email, Sub-sub-sublhsados de email, Filtros e Exportação não são afetadas.</span><span class="sxs-lookup"><span data-stu-id="a6cba-236">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="a6cba-237">Exchange Online Somente - Prevenção contra Perda de Dados: Todos</span><span class="sxs-lookup"><span data-stu-id="a6cba-237">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="a6cba-238">Exchange Online Somente - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="a6cba-238">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="a6cba-239">Microsoft Azure Active Directory ou Exchange Online - Administrador de Segurança: Todos</span><span class="sxs-lookup"><span data-stu-id="a6cba-239">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="a6cba-240">Azure Active Directory ou Exchange Online - Leitor de Segurança: Tudo</span><span class="sxs-lookup"><span data-stu-id="a6cba-240">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="a6cba-241">Exchange Online Somente - Regras de Transporte: Todos</span><span class="sxs-lookup"><span data-stu-id="a6cba-241">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="a6cba-242">Exchange Online Somente - View-Only Configuração: Tudo</span><span class="sxs-lookup"><span data-stu-id="a6cba-242">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="a6cba-243">Na grade de email, sobremenos e CSV exportados, os ETRs são apresentados com um Nome/GUID, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="a6cba-243">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="a6cba-244">![Exchange Regras de Transporte](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-244">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="a6cba-245">Conectores de entrada</span><span class="sxs-lookup"><span data-stu-id="a6cba-245">Inbound connectors</span></span>

<span data-ttu-id="a6cba-246">Conectores são uma coleção de instruções que personalizam como seu email flui de e para sua Microsoft 365 ou Office 365 organização.</span><span class="sxs-lookup"><span data-stu-id="a6cba-246">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="a6cba-247">Eles permitem que você aplique quaisquer restrições ou controles de segurança.</span><span class="sxs-lookup"><span data-stu-id="a6cba-247">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="a6cba-248">No Explorador de Ameaças, você pode exibir os conectores relacionados a um email e pesquisar emails usando nomes de conectores.</span><span class="sxs-lookup"><span data-stu-id="a6cba-248">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span>

<span data-ttu-id="a6cba-249">A pesquisa por conectores é uma consulta CONTAINS, o que significa que pesquisas parciais de palavra-chave podem funcionar:</span><span class="sxs-lookup"><span data-stu-id="a6cba-249">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6cba-250">![Detalhes do conector](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="a6cba-250">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="a6cba-251">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="a6cba-251">Required licenses and permissions</span></span>

<span data-ttu-id="a6cba-252">Você deve ter [o Microsoft Defender para Office 365](defender-for-office-365.md) usar detecções do Explorer ou em tempo real.</span><span class="sxs-lookup"><span data-stu-id="a6cba-252">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="a6cba-253">O Explorer está incluído no Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="a6cba-253">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="a6cba-254">O relatório de detecções em tempo real está incluído no Defender para Office 365 Plano 1.</span><span class="sxs-lookup"><span data-stu-id="a6cba-254">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="a6cba-255">Planeje atribuir licenças para todos os usuários que devem ser protegidos pelo Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6cba-255">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="a6cba-256">As detecções do Explorer e em tempo real mostram dados de detecção para usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="a6cba-256">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="a6cba-257">Para exibir e usar detecções do Explorer ou em tempo real, você deve ter as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="a6cba-257">To view and use Explorer or Real-time detections, you must have the following permissions:</span></span>

- <span data-ttu-id="a6cba-258">Para o Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="a6cba-258">For the Microsoft 365 Defender portal:</span></span>
  - <span data-ttu-id="a6cba-259">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="a6cba-259">Organization Management</span></span>
  - <span data-ttu-id="a6cba-260">Administrador de Segurança (isso pode ser atribuído no Azure Active Directory de administração ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="a6cba-260">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="a6cba-261">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="a6cba-261">Security Reader</span></span>
- <span data-ttu-id="a6cba-262">Para Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a6cba-262">For Exchange Online:</span></span>
  - <span data-ttu-id="a6cba-263">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="a6cba-263">Organization Management</span></span>
  - <span data-ttu-id="a6cba-264">Gerenciamento de Organização Somente Exibição</span><span class="sxs-lookup"><span data-stu-id="a6cba-264">View-Only Organization Management</span></span>
  - <span data-ttu-id="a6cba-265">Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="a6cba-265">View-Only Recipients</span></span>
  - <span data-ttu-id="a6cba-266">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="a6cba-266">Compliance Management</span></span>

<span data-ttu-id="a6cba-267">Para saber mais sobre funções e permissões, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="a6cba-267">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="a6cba-268">Permissões no portal do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6cba-268">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="a6cba-269">Permissões de recursos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a6cba-269">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="a6cba-270">PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a6cba-270">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="a6cba-271">Mais informações</span><span class="sxs-lookup"><span data-stu-id="a6cba-271">More information</span></span>

- [<span data-ttu-id="a6cba-272">Localizar e investigar emails mal-intencionados entregues</span><span class="sxs-lookup"><span data-stu-id="a6cba-272">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="a6cba-273">Exibir arquivos mal-intencionados detectados no SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a6cba-273">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="a6cba-274">Obter uma visão geral dos exibições no Explorador de Ameaças (e detecções em tempo real)</span><span class="sxs-lookup"><span data-stu-id="a6cba-274">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="a6cba-275">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="a6cba-275">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="a6cba-276">Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a6cba-276">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
- [<span data-ttu-id="a6cba-277">Investigar emails com a página Entidade de Email</span><span class="sxs-lookup"><span data-stu-id="a6cba-277">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
