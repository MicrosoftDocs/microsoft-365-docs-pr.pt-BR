---
title: Microsoft Secure Score
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como melhorar a postura de segurança e quais administradores de segurança podem esperar.
keywords: Pontuação segura da Microsoft, Pontuação segura, Pontuação segura do Office 365, pontuação de segurança da Microsoft, centro de segurança da Microsoft 365, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: a41e05f54a8ba94752c6df91628a2200367ac0f3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843835"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="ca89f-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="ca89f-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ca89f-105">A pontuação segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando ações mais aprimoradas.</span><span class="sxs-lookup"><span data-stu-id="ca89f-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="ca89f-106">Ele pode ser encontrado no https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="ca89f-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="ca89f-107">Seguindo as recomendações de Pontuação segura podem proteger sua organização contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="ca89f-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="ca89f-108">A partir de um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar com a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca89f-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="ca89f-109">A pontuação segura ajuda as organizações:</span><span class="sxs-lookup"><span data-stu-id="ca89f-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="ca89f-110">Relatar o estado atual da postura de segurança da organização.</span><span class="sxs-lookup"><span data-stu-id="ca89f-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="ca89f-111">Melhorar a postura de segurança fornecendo descoberta, visibilidade, orientação e controle.</span><span class="sxs-lookup"><span data-stu-id="ca89f-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="ca89f-112">Compare com benchmarks e estabeleça indicadores de desempenho principais (KPIs).</span><span class="sxs-lookup"><span data-stu-id="ca89f-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="ca89f-113">As organizações obtêm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontos com organizações similares e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ca89f-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="ca89f-114">A pontuação também pode refletir quando soluções de terceiros solucionaram as ações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ca89f-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Home Page de Pontuação segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="ca89f-116">Como funciona</span><span class="sxs-lookup"><span data-stu-id="ca89f-116">How it works</span></span>

<span data-ttu-id="ca89f-117">Você tem pontos para as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="ca89f-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="ca89f-118">Configurando recursos de segurança recomendados</span><span class="sxs-lookup"><span data-stu-id="ca89f-118">Configuring recommended security features</span></span>
- <span data-ttu-id="ca89f-119">Executando tarefas relacionadas à segurança</span><span class="sxs-lookup"><span data-stu-id="ca89f-119">Performing security-related tasks</span></span>
- <span data-ttu-id="ca89f-120">Lidando com a ação de melhoria com um aplicativo ou software de terceiros, ou uma atenuação alternativa</span><span class="sxs-lookup"><span data-stu-id="ca89f-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="ca89f-121">Algumas ações de melhoria só dão pontos quando totalmente concluídas.</span><span class="sxs-lookup"><span data-stu-id="ca89f-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="ca89f-122">Alguns dão pontos parciais se eles forem concluídos para alguns dispositivos ou usuários.</span><span class="sxs-lookup"><span data-stu-id="ca89f-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="ca89f-123">Se não for possível ou não quiser enactr uma das ações de aperfeiçoamento, você pode optar por aceitar o risco ou o risco restante.</span><span class="sxs-lookup"><span data-stu-id="ca89f-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="ca89f-124">Se você tiver uma licença para um dos produtos da Microsoft com suporte, verá recomendações para esses produtos.</span><span class="sxs-lookup"><span data-stu-id="ca89f-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="ca89f-125">Mostramos o conjunto completo de possíveis aprimoramentos de um produto, independentemente da edição da licença, assinatura ou planejamento.</span><span class="sxs-lookup"><span data-stu-id="ca89f-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="ca89f-126">Dessa forma, você pode entender as práticas recomendadas de segurança e melhorar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="ca89f-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="ca89f-127">Sua postura de segurança absoluta, representada pela pontuação segura, permanece o mesmo que as licenças que sua organização possui para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="ca89f-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="ca89f-128">Tenha em mente que a segurança deve ser balanceada com usabilidade, e nem todas as recomendações podem funcionar para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ca89f-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="ca89f-129">Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de ações de visualizações e melhorias.</span><span class="sxs-lookup"><span data-stu-id="ca89f-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="ca89f-130">A pontuação segura também sincroniza diariamente para receber dados do sistema sobre seus pontos obtidos para cada ação.</span><span class="sxs-lookup"><span data-stu-id="ca89f-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="ca89f-131">Principais cenários</span><span class="sxs-lookup"><span data-stu-id="ca89f-131">Key scenarios</span></span>

- [<span data-ttu-id="ca89f-132">Verificar sua pontuação atual</span><span class="sxs-lookup"><span data-stu-id="ca89f-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="ca89f-133">Comparar sua pontuação com organizações como a sua</span><span class="sxs-lookup"><span data-stu-id="ca89f-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="ca89f-134">Exibir ações de aprimoramento e decidir um plano de ação</span><span class="sxs-lookup"><span data-stu-id="ca89f-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="ca89f-135">Iniciar fluxos de trabalho para investigar ou implementar</span><span class="sxs-lookup"><span data-stu-id="ca89f-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="ca89f-136">Centro de segurança do Microsoft 365 e integração com o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ca89f-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="ca89f-137">Como as ações de aperfeiçoamento são pontuadas</span><span class="sxs-lookup"><span data-stu-id="ca89f-137">How improvement actions are scored</span></span>

<span data-ttu-id="ca89f-138">Cada ação de melhoria vale 10 pontos ou menos, e a maioria é classificada de forma binária.</span><span class="sxs-lookup"><span data-stu-id="ca89f-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="ca89f-139">Se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, obterá 100% dos pontos.</span><span class="sxs-lookup"><span data-stu-id="ca89f-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="ca89f-140">Para outras ações de melhoria, os pontos são fornecidos como uma porcentagem da configuração total.</span><span class="sxs-lookup"><span data-stu-id="ca89f-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="ca89f-141">Por exemplo, uma ação de melhoria diz que você obtém 10 pontos protegendo todos os seus usuários com autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="ca89f-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="ca89f-142">Você só tem 50 de 100 total de usuários protegidos, portanto, obteria uma pontuação parcial de cinco pontos (50 protegido/100 total \* 10 máximo de 5 pontos).</span><span class="sxs-lookup"><span data-stu-id="ca89f-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="ca89f-143">Produtos incluídos na pontuação segura</span><span class="sxs-lookup"><span data-stu-id="ca89f-143">Products included in Secure Score</span></span>

<span data-ttu-id="ca89f-144">No momento, há recomendações para o Microsoft 365 (incluindo o Exchange Online), o Azure Active Directory, o Microsoft defender para ponto de extremidade, o Microsoft defender para identidade e o Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="ca89f-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="ca89f-145">As recomendações para outros produtos de segurança serão disponibilizadas em breve.</span><span class="sxs-lookup"><span data-stu-id="ca89f-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="ca89f-146">As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base.</span><span class="sxs-lookup"><span data-stu-id="ca89f-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="ca89f-147">Você também pode marcar as ações de melhoria como cobertas por terceiros ou como atenuação alternativa.</span><span class="sxs-lookup"><span data-stu-id="ca89f-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="ca89f-148">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="ca89f-148">Security defaults</span></span>

<span data-ttu-id="ca89f-149">A pontuação segura da Microsoft atualiza as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da organização com configurações de segurança pré-configuradas para ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="ca89f-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="ca89f-150">Se você ativar os padrões de segurança, receberá pontos completos para as seguintes ações de aprimoramento:</span><span class="sxs-lookup"><span data-stu-id="ca89f-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="ca89f-151">Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro (9 pontos)</span><span class="sxs-lookup"><span data-stu-id="ca89f-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="ca89f-152">Exigir MFA para funções administrativas (10 pontos)</span><span class="sxs-lookup"><span data-stu-id="ca89f-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="ca89f-153">Habilitar política para bloquear autenticação herdada (7 pontos)</span><span class="sxs-lookup"><span data-stu-id="ca89f-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="ca89f-154">Os padrões de segurança incluem recursos de segurança que oferecem segurança semelhante às ações de aperfeiçoamento "política de risco de entrada" e "política de risco de usuário".</span><span class="sxs-lookup"><span data-stu-id="ca89f-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="ca89f-155">Em vez de configurar essas políticas na parte superior dos padrões de segurança, recomendamos atualizar seus status para "resolvido por meio de atenuação alternativa".</span><span class="sxs-lookup"><span data-stu-id="ca89f-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="ca89f-156">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="ca89f-156">Required permissions</span></span>

<span data-ttu-id="ca89f-157">Para ter permissão para acessar a pontuação segura da Microsoft, você deve receber uma das seguintes funções no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ca89f-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="ca89f-158">Funções de leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="ca89f-158">Read and write roles</span></span>

<span data-ttu-id="ca89f-159">Com acesso de leitura e gravação, você pode fazer alterações e interagir diretamente com a pontuação segura.</span><span class="sxs-lookup"><span data-stu-id="ca89f-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="ca89f-160">Você também pode atribuir acesso somente leitura a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="ca89f-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="ca89f-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="ca89f-161">Global administrator</span></span>
* <span data-ttu-id="ca89f-162">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="ca89f-162">Security administrator</span></span>
* <span data-ttu-id="ca89f-163">Administrador do Exchange</span><span class="sxs-lookup"><span data-stu-id="ca89f-163">Exchange administrator</span></span>
* <span data-ttu-id="ca89f-164">Administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ca89f-164">SharePoint administrator</span></span>
* <span data-ttu-id="ca89f-165">Administrador de contas</span><span class="sxs-lookup"><span data-stu-id="ca89f-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="ca89f-166">Funções somente leitura</span><span class="sxs-lookup"><span data-stu-id="ca89f-166">Read-only roles</span></span>

<span data-ttu-id="ca89f-167">Com acesso somente leitura, não é possível editar o status ou as anotações de uma ação de melhoria, editar zonas de pontuação ou editar comparações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ca89f-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="ca89f-168">Administrador da assistência técnica</span><span class="sxs-lookup"><span data-stu-id="ca89f-168">Helpdesk administrator</span></span>
* <span data-ttu-id="ca89f-169">Administrador de usuários</span><span class="sxs-lookup"><span data-stu-id="ca89f-169">User administrator</span></span>
* <span data-ttu-id="ca89f-170">Administrador de serviço</span><span class="sxs-lookup"><span data-stu-id="ca89f-170">Service administrator</span></span>
* <span data-ttu-id="ca89f-171">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="ca89f-171">Security reader</span></span>
* <span data-ttu-id="ca89f-172">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="ca89f-172">Security operator</span></span>
* <span data-ttu-id="ca89f-173">Leitor global</span><span class="sxs-lookup"><span data-stu-id="ca89f-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="ca89f-174">Reconhecimento de risco</span><span class="sxs-lookup"><span data-stu-id="ca89f-174">Risk awareness</span></span>

<span data-ttu-id="ca89f-175">A pontuação segura da Microsoft é um resumo numérico de sua postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="ca89f-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="ca89f-176">Não é uma medida absoluta da probabilidade de que seu sistema ou dados seja violado.</span><span class="sxs-lookup"><span data-stu-id="ca89f-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="ca89f-177">Em vez disso, ele representa a extensão à qual você adotou os controles de segurança no seu ambiente Microsoft que podem ajudar a reduzir o risco de ser violado.</span><span class="sxs-lookup"><span data-stu-id="ca89f-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="ca89f-178">Nenhum serviço online é totalmente imune às brechas de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violação de segurança de qualquer forma.</span><span class="sxs-lookup"><span data-stu-id="ca89f-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="ca89f-179">Queremos ouvir sua opinião</span><span class="sxs-lookup"><span data-stu-id="ca89f-179">We want to hear from you</span></span>

<span data-ttu-id="ca89f-180">Se você tiver problemas, fale conosco postando na Comunidade [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="ca89f-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="ca89f-181">Estamos monitorando a Comunidade e forneceremos ajuda.</span><span class="sxs-lookup"><span data-stu-id="ca89f-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="ca89f-182">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="ca89f-182">Related resources</span></span>

- [<span data-ttu-id="ca89f-183">Avaliar sua postura de segurança</span><span class="sxs-lookup"><span data-stu-id="ca89f-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="ca89f-184">Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas</span><span class="sxs-lookup"><span data-stu-id="ca89f-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="ca89f-185">O que estar por vir.</span><span class="sxs-lookup"><span data-stu-id="ca89f-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="ca89f-186">Novidades</span><span class="sxs-lookup"><span data-stu-id="ca89f-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
