---
title: Avaliar sua postura de segurança por meio da Pontuação Segura da Microsoft
description: Descreve como tomar medidas para melhorar a Pontuação Segura da Microsoft no centro Microsoft 365 segurança.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8b321fc8883cf490cb5b2814d5c2b617a52dbb29
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246387"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="40ca6-104">Avaliar sua postura de segurança com a Pontuação Segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="40ca6-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="40ca6-105">O Microsoft Secure Score é uma medição da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria adotadas.</span><span class="sxs-lookup"><span data-stu-id="40ca6-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="40ca6-106">Ele pode ser encontrado no https://security.microsoft.com/securescore centro de Microsoft 365 [segurança](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="40ca6-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="40ca6-107">Para ajudá-lo a encontrar as informações necessárias mais rapidamente, as ações de melhoria da Microsoft são organizadas em grupos:</span><span class="sxs-lookup"><span data-stu-id="40ca6-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="40ca6-108">Identidade (Azure Active Directory contas & funções)</span><span class="sxs-lookup"><span data-stu-id="40ca6-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="40ca6-109">Dispositivo (Microsoft Defender para Ponto de Extremidade, conhecido como [Pontuação Segura da Microsoft para Dispositivos](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span><span class="sxs-lookup"><span data-stu-id="40ca6-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="40ca6-110">Aplicativos (aplicativos de email e nuvem, incluindo Office 365 e Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="40ca6-110">Apps (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="40ca6-111">Na versão recente do Microsoft Secure Score, um modelo de pontuação aprimorado foi lançado, o que tornou a Pontuação Segura da Microsoft temporariamente incompatível com a Pontuação Segura de Identidade e a API Graph.</span><span class="sxs-lookup"><span data-stu-id="40ca6-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="40ca6-112">Exibir detalhes</span><span class="sxs-lookup"><span data-stu-id="40ca6-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="40ca6-113">Na página Visão geral da Pontuação Segura da Microsoft, veja como os pontos são divididos entre esses grupos e quais pontos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="40ca6-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="40ca6-114">Você também pode obter uma visão completa da pontuação total, tendência histórica de sua pontuação segura com comparações de benchmark e ações de melhoria priorizadas que podem ser tomadas para melhorar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="40ca6-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Homepage de Pontuação Segura](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a><span data-ttu-id="40ca6-116">Verificar sua pontuação atual</span><span class="sxs-lookup"><span data-stu-id="40ca6-116">Check your current score</span></span>

<span data-ttu-id="40ca6-117">Para verificar sua pontuação atual, vá para a página Visão geral da Pontuação Segura da Microsoft e procure o pacote que diz **Sua pontuação segura**.</span><span class="sxs-lookup"><span data-stu-id="40ca6-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="40ca6-118">Sua pontuação será mostrada como uma porcentagem, juntamente com o número de pontos que você atingiu fora do total de pontos possíveis.</span><span class="sxs-lookup"><span data-stu-id="40ca6-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="40ca6-119">Além disso, se você selecionar o botão **Incluir** ao lado de sua pontuação, poderá escolher diferentes exibições de sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="40ca6-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="40ca6-120">Esses diferentes pontos de exibição de pontuação serão exibidos no gráfico no tile de pontuação e no gráfico de divisão de pontos.</span><span class="sxs-lookup"><span data-stu-id="40ca6-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="40ca6-121">Veja a seguir as pontuações que você pode adicionar ao modo de exibição de sua pontuação geral para lhe dar uma visão mais completa da sua pontuação geral:</span><span class="sxs-lookup"><span data-stu-id="40ca6-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="40ca6-122">**Pontuação planejada**: Mostrar pontuação projetada quando as ações planejadas são concluídas</span><span class="sxs-lookup"><span data-stu-id="40ca6-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="40ca6-123">**Pontuação atual da licença**: Mostrar a pontuação que pode ser atingida com a licença atual da Microsoft</span><span class="sxs-lookup"><span data-stu-id="40ca6-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="40ca6-124">**Pontuação alcançável**: Mostrar pontuação que pode ser atingida com suas licenças da Microsoft e aceitação de risco atual</span><span class="sxs-lookup"><span data-stu-id="40ca6-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="40ca6-125">Esta exibição será a aparência se você tiver incluído todos os exibições de pontuação possíveis:</span><span class="sxs-lookup"><span data-stu-id="40ca6-125">This view is what it will look like if you've included all possible score views:</span></span>

![Sua pontuação segura, incluindo pontuação planejada, pontuação de licença atual e pontuação realizável](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="40ca6-127">Tomar medidas para melhorar sua pontuação</span><span class="sxs-lookup"><span data-stu-id="40ca6-127">Take action to improve your score</span></span>

<span data-ttu-id="40ca6-128">A **guia Ações de aperfeiçoamento** lista as recomendações de segurança que abordam possíveis superfícies de ataque.</span><span class="sxs-lookup"><span data-stu-id="40ca6-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="40ca6-129">Ele também inclui seu status (para resolver, planejado, aceitar riscos, resolvido por terceiros, resolvido por meio de mitigação alternativa e concluído).</span><span class="sxs-lookup"><span data-stu-id="40ca6-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="40ca6-130">Você pode pesquisar, filtrar e agrupar todas as ações de melhoria.</span><span class="sxs-lookup"><span data-stu-id="40ca6-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="40ca6-131">Classificação</span><span class="sxs-lookup"><span data-stu-id="40ca6-131">Ranking</span></span>

<span data-ttu-id="40ca6-132">A classificação baseia-se no número de pontos a alcançar, na dificuldade de implementação, no impacto do usuário e na complexidade.</span><span class="sxs-lookup"><span data-stu-id="40ca6-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="40ca6-133">As ações de melhoria mais altas classificadas têm um grande número de pontos restantes com baixa dificuldade, impacto do usuário e complexidade.</span><span class="sxs-lookup"><span data-stu-id="40ca6-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="40ca6-134">Exibir detalhes da ação de melhoria</span><span class="sxs-lookup"><span data-stu-id="40ca6-134">View improvement action details</span></span>

<span data-ttu-id="40ca6-135">Quando você seleciona uma ação de melhoria específica, um flyout de página inteira é exibido.</span><span class="sxs-lookup"><span data-stu-id="40ca6-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![Exemplo de flyout de ação de melhoria](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="40ca6-137">Para concluir a ação, você tem algumas opções:</span><span class="sxs-lookup"><span data-stu-id="40ca6-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="40ca6-138">Selecione **Gerenciar** para ir para a tela de configuração e fazer a alteração.</span><span class="sxs-lookup"><span data-stu-id="40ca6-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="40ca6-139">Em seguida, você obterá os pontos que a ação vale, visíveis na saída de voo. Os pontos geralmente levam cerca de 24 horas para ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="40ca6-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="40ca6-140">Selecione **Compartilhar** para copiar o link direto para a ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="40ca6-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="40ca6-141">Você também pode escolher a plataforma para compartilhar o link, como email, Microsoft Teams ou Microsoft Planner.</span><span class="sxs-lookup"><span data-stu-id="40ca6-141">You can also choose the platform to share the link, such as email, Microsoft Teams, or Microsoft Planner.</span></span>

<span data-ttu-id="40ca6-142">Adicione **Anotações** para acompanhar o andamento ou qualquer outra coisa em que você queira comentar.</span><span class="sxs-lookup"><span data-stu-id="40ca6-142">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="40ca6-143">Se você adicionar suas próprias **marcas** à ação de melhoria, poderá filtrar por essas marcas.</span><span class="sxs-lookup"><span data-stu-id="40ca6-143">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="40ca6-144">Escolher um status de ação de melhoria</span><span class="sxs-lookup"><span data-stu-id="40ca6-144">Choose an improvement action status</span></span>

<span data-ttu-id="40ca6-145">Escolha quaisquer status e anotações de registro específicas da ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="40ca6-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="40ca6-146">**Para resolver** – você reconhece que a ação de melhoria é necessária e planeja a resolver em algum momento no futuro.</span><span class="sxs-lookup"><span data-stu-id="40ca6-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="40ca6-147">Esse estado também se aplica a ações detectadas parcialmente, mas não totalmente concluídas.</span><span class="sxs-lookup"><span data-stu-id="40ca6-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="40ca6-148">**Planejado** - Há planos concretos para concluir a ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="40ca6-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="40ca6-149">**Risco aceito** - A segurança sempre deve ser equilibrada com usabilidade, e nem todas as recomendações funcionarão para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="40ca6-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="40ca6-150">Quando esse for o caso, você pode optar por aceitar o risco ou o risco restante e não aprovar a ação de melhoria.</span><span class="sxs-lookup"><span data-stu-id="40ca6-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="40ca6-151">Você não receberá pontos, mas a ação não ficará mais visível na lista de ações de melhoria.</span><span class="sxs-lookup"><span data-stu-id="40ca6-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="40ca6-152">Você pode exibir essa ação no histórico ou desfazê-la a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="40ca6-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="40ca6-153">**Resolvido por meio de terceiros** e Resolvido por meio de **mitigação** alternativa - A ação de melhoria já foi abordada por um aplicativo ou software de terceiros ou por uma ferramenta interna.</span><span class="sxs-lookup"><span data-stu-id="40ca6-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="40ca6-154">Você obterá os pontos que a ação vale, para que sua pontuação reflita melhor sua postura de segurança geral.</span><span class="sxs-lookup"><span data-stu-id="40ca6-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="40ca6-155">Se uma ferramenta interna ou de terceiros não abranger mais o controle, você pode escolher outro status.</span><span class="sxs-lookup"><span data-stu-id="40ca6-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="40ca6-156">Lembre-se de que a Microsoft não terá visibilidade sobre a conclusão da implementação se a ação de melhoria estiver marcada como um desses status.</span><span class="sxs-lookup"><span data-stu-id="40ca6-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="40ca6-157">Ações & Gerenciamento de Vulnerabilidades melhoria de ameaças</span><span class="sxs-lookup"><span data-stu-id="40ca6-157">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="40ca6-158">Para ações de melhoria na categoria "Dispositivo", não é possível escolher status.</span><span class="sxs-lookup"><span data-stu-id="40ca6-158">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="40ca6-159">Em vez disso, você será direcionado para a recomendação de Gerenciamento de Ameaças e Vulnerabilidades [de](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) segurança associada no Central de Segurança do Microsoft Defender [para](/windows/security/threat-protection/microsoft-defender-atp/use) tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="40ca6-159">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="40ca6-160">A exceção escolhida e a justificativa que você escreve serão específicas para esse portal.</span><span class="sxs-lookup"><span data-stu-id="40ca6-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="40ca6-161">Ele não estará presente no portal de Pontuação Segura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40ca6-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="40ca6-162">Ações de aperfeiçoamento concluídas</span><span class="sxs-lookup"><span data-stu-id="40ca6-162">Completed improvement actions</span></span>

<span data-ttu-id="40ca6-163">As ações de melhoria têm um status "concluído" depois que todos os pontos possíveis para a ação de melhoria foram atingidos.</span><span class="sxs-lookup"><span data-stu-id="40ca6-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="40ca6-164">As ações de melhoria concluídas são confirmadas embora os dados da Microsoft e você não possa alterar o status.</span><span class="sxs-lookup"><span data-stu-id="40ca6-164">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="40ca6-165">Avaliar informações e analisar o impacto do usuário</span><span class="sxs-lookup"><span data-stu-id="40ca6-165">Assess information and review user impact</span></span>

<span data-ttu-id="40ca6-166">A seção chamada **At a glance** dirá a categoria, os ataques que ela pode proteger e o produto.</span><span class="sxs-lookup"><span data-stu-id="40ca6-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="40ca6-167">**O impacto do** usuário é o que os usuários  experimentarão se a ação de melhoria for aprovada, e os usuários afetados serão as pessoas que serão afetadas.</span><span class="sxs-lookup"><span data-stu-id="40ca6-167">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="40ca6-168">Implementar a ação de melhoria</span><span class="sxs-lookup"><span data-stu-id="40ca6-168">Implement the improvement action</span></span>

<span data-ttu-id="40ca6-169">A **seção** Implementação mostra os pré-requisitos, etapas passo a passo para concluir a ação de melhoria, o status de implementação atual da ação de melhoria e qualquer outra informação sobre mais links.</span><span class="sxs-lookup"><span data-stu-id="40ca6-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="40ca6-170">Os pré-requisitos incluem quaisquer licenças necessárias ou ações a serem concluídas antes que a ação de melhoria seja abordada.</span><span class="sxs-lookup"><span data-stu-id="40ca6-170">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="40ca6-171">Certifique-se de ter assentos suficientes em sua licença para concluir a ação de melhoria e se essas licenças são aplicadas aos usuários necessários.</span><span class="sxs-lookup"><span data-stu-id="40ca6-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="40ca6-172">Queremos ouvir de você</span><span class="sxs-lookup"><span data-stu-id="40ca6-172">We want to hear from you</span></span>

<span data-ttu-id="40ca6-173">Se você tiver algum problema, nos avise postando na comunidade [Segurança, Privacidade & Conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="40ca6-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="40ca6-174">Estamos monitorando a comunidade e forneceremos ajuda.</span><span class="sxs-lookup"><span data-stu-id="40ca6-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="40ca6-175">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="40ca6-175">Related resources</span></span>

- [<span data-ttu-id="40ca6-176">Visão geral da Pontuação Segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="40ca6-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="40ca6-177">Rastrear seu histórico de Pontuação Segura da Microsoft e cumprir metas</span><span class="sxs-lookup"><span data-stu-id="40ca6-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="40ca6-178">O que estar por vir.</span><span class="sxs-lookup"><span data-stu-id="40ca6-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="40ca6-179">Novidades</span><span class="sxs-lookup"><span data-stu-id="40ca6-179">What's new</span></span>](microsoft-secure-score-whats-new.md)