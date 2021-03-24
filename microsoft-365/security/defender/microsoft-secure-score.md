---
title: Microsoft Secure Score
description: Descreve a Pontuação Segura da Microsoft no centro de segurança do Microsoft 365, como melhorar sua postura de segurança e o que os administradores de segurança podem esperar.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.technology: m365d
ms.openlocfilehash: 98f335a38b2e4f581d4b08def39353e53e1bafd4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053486"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="38987-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="38987-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="38987-105">O Microsoft Secure Score é uma medição da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria adotadas.</span><span class="sxs-lookup"><span data-stu-id="38987-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="38987-106">Ele pode ser encontrado no centro de segurança do https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="38987-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="38987-107">Seguir as recomendações do Secure Score pode proteger sua organização contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="38987-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="38987-108">Em um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar na segurança de suas identidades, aplicativos e dispositivos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38987-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="38987-109">O Secure Core ajuda as organizações a:</span><span class="sxs-lookup"><span data-stu-id="38987-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="38987-110">Relatar o estado atual da situação de segurança da organização.</span><span class="sxs-lookup"><span data-stu-id="38987-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="38987-111">Melhorar sua situação de segurança fornecendo capacidade de descoberta, visibilidade, orientação e controle.</span><span class="sxs-lookup"><span data-stu-id="38987-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="38987-112">Comparar com os benchmarks e estabelecer KPIs (indicadores chave de desempenho).</span><span class="sxs-lookup"><span data-stu-id="38987-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="38987-113">As organizações têm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontuação com organizações semelhantes e muito mais.</span><span class="sxs-lookup"><span data-stu-id="38987-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="38987-114">A pontuação também pode refletir quando soluções de terceiros abordaram ações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="38987-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Homepage de Pontuação Segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="38987-116">Como funciona</span><span class="sxs-lookup"><span data-stu-id="38987-116">How it works</span></span>

<span data-ttu-id="38987-117">Você recebe pontos para as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="38987-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="38987-118">Configurando recursos de segurança recomendados</span><span class="sxs-lookup"><span data-stu-id="38987-118">Configuring recommended security features</span></span>
- <span data-ttu-id="38987-119">Fazendo tarefas relacionadas à segurança</span><span class="sxs-lookup"><span data-stu-id="38987-119">Doing security-related tasks</span></span>
- <span data-ttu-id="38987-120">Endereçamento da ação de aperfeiçoamento com um aplicativo ou software de terceiros ou uma mitigação alternativa</span><span class="sxs-lookup"><span data-stu-id="38987-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="38987-121">Algumas ações de melhoria só dão pontos quando concluídas totalmente.</span><span class="sxs-lookup"><span data-stu-id="38987-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="38987-122">Alguns dão pontos parciais se eles são concluídos para alguns dispositivos ou usuários.</span><span class="sxs-lookup"><span data-stu-id="38987-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="38987-123">Se você não puder ou não quiser aprovar uma das ações de melhoria, poderá optar por aceitar o risco ou o risco restante.</span><span class="sxs-lookup"><span data-stu-id="38987-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="38987-124">Se você tiver uma licença para um dos produtos da Microsoft com suporte, verá recomendações para esses produtos.</span><span class="sxs-lookup"><span data-stu-id="38987-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="38987-125">Mostramos o conjunto completo de possíveis melhorias para um produto, independentemente da edição de licença, assinatura ou plano.</span><span class="sxs-lookup"><span data-stu-id="38987-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="38987-126">Dessa forma, você pode entender as práticas recomendadas de segurança e melhorar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="38987-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="38987-127">Sua postura de segurança absoluta, representada pela Pontuação Segura, permanece a mesma, independentemente das licenças que sua organização possui para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="38987-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="38987-128">Tenha em mente que a segurança deve ser equilibrada com a usabilidade e nem todas as recomendações podem funcionar para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="38987-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="38987-129">Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de visualizações e ações de aperfeiçoamento.</span><span class="sxs-lookup"><span data-stu-id="38987-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="38987-130">A Pontuação Segura também sincroniza diariamente para receber dados do sistema sobre seus pontos alcançados para cada ação.</span><span class="sxs-lookup"><span data-stu-id="38987-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="38987-131">Cenários principais</span><span class="sxs-lookup"><span data-stu-id="38987-131">Key scenarios</span></span>

- [<span data-ttu-id="38987-132">Verificar sua pontuação atual</span><span class="sxs-lookup"><span data-stu-id="38987-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="38987-133">Comparar sua pontuação com organizações como a sua</span><span class="sxs-lookup"><span data-stu-id="38987-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="38987-134">Exibir ações de melhoria e decidir um plano de ação</span><span class="sxs-lookup"><span data-stu-id="38987-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="38987-135">Iniciar fluxos de trabalho para investigar ou implementar</span><span class="sxs-lookup"><span data-stu-id="38987-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="38987-136">Como as ações de melhoria são pontuadas</span><span class="sxs-lookup"><span data-stu-id="38987-136">How improvement actions are scored</span></span>

<span data-ttu-id="38987-137">Cada ação de melhoria vale 10 pontos ou menos e a maioria é pontuada de forma binária.</span><span class="sxs-lookup"><span data-stu-id="38987-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="38987-138">Se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, você obterá 100% dos pontos.</span><span class="sxs-lookup"><span data-stu-id="38987-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="38987-139">Para outras ações de melhoria, os pontos são dados como um percentual da configuração total.</span><span class="sxs-lookup"><span data-stu-id="38987-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="38987-140">Por exemplo, uma ação de melhoria afirma que você tem 10 pontos protegendo todos os usuários com autenticação multifatória.</span><span class="sxs-lookup"><span data-stu-id="38987-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="38987-141">Você só tem 50 dos 100 usuários totais protegidos, para obter uma pontuação parcial de 5 pontos (50 protegidos / 100 total \* 10 pts máximos = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="38987-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="38987-142">Produtos incluídos na Pontuação Segura</span><span class="sxs-lookup"><span data-stu-id="38987-142">Products included in Secure Score</span></span>

<span data-ttu-id="38987-143">Atualmente, há recomendações para os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="38987-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="38987-144">Microsoft 365 (incluindo o Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="38987-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="38987-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="38987-145">Azure Active Directory</span></span>
- <span data-ttu-id="38987-146">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="38987-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="38987-147">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="38987-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="38987-148">Segurança no Aplicativo na Nuvem</span><span class="sxs-lookup"><span data-stu-id="38987-148">Cloud App Security</span></span>
- <span data-ttu-id="38987-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38987-149">Microsoft Teams</span></span>

<span data-ttu-id="38987-150">As recomendações para outros produtos de segurança estão chegando em breve.</span><span class="sxs-lookup"><span data-stu-id="38987-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="38987-151">As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base.</span><span class="sxs-lookup"><span data-stu-id="38987-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="38987-152">Você também pode marcar as ações de melhoria como cobertas por terceiros ou mitigação alternativa.</span><span class="sxs-lookup"><span data-stu-id="38987-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="38987-153">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="38987-153">Security defaults</span></span>

<span data-ttu-id="38987-154">O Microsoft Secure Score atualizou as ações de melhoria para dar suporte aos padrões de segurança no [Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="38987-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="38987-155">Se você ativar os padrões de segurança, você receberá pontos completos pelas seguintes ações de melhoria:</span><span class="sxs-lookup"><span data-stu-id="38987-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="38987-156">Certifique-se de que todos os usuários possam concluir a autenticação multifa factor para acesso seguro (9 pontos)</span><span class="sxs-lookup"><span data-stu-id="38987-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="38987-157">Exigir MFA para funções administrativas (10 pontos)</span><span class="sxs-lookup"><span data-stu-id="38987-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="38987-158">Habilitar a política para bloquear a autenticação herdado (7 pontos)</span><span class="sxs-lookup"><span data-stu-id="38987-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="38987-159">Os padrões de segurança incluem recursos de segurança que fornecem segurança semelhante às ações de melhoria "política de risco de entrar" e "política de risco do usuário".</span><span class="sxs-lookup"><span data-stu-id="38987-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="38987-160">Em vez de configurar essas políticas em cima dos padrões de segurança, recomendamos atualizar seus status para "Resolvido por meio de mitigação alternativa".</span><span class="sxs-lookup"><span data-stu-id="38987-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="38987-161">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="38987-161">Required permissions</span></span>

<span data-ttu-id="38987-162">Para ter permissão para acessar a Pontuação Segura da Microsoft, você deve ter uma das seguintes funções no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38987-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="38987-163">Funções de leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="38987-163">Read and write roles</span></span>

<span data-ttu-id="38987-164">Com o acesso de leitura e gravação, você pode fazer alterações e interagir diretamente com a Pontuação Segura.</span><span class="sxs-lookup"><span data-stu-id="38987-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="38987-165">Você também pode atribuir acesso somente leitura a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="38987-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="38987-166">Administrador global</span><span class="sxs-lookup"><span data-stu-id="38987-166">Global administrator</span></span>
* <span data-ttu-id="38987-167">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="38987-167">Security administrator</span></span>
* <span data-ttu-id="38987-168">Administrador do Exchange</span><span class="sxs-lookup"><span data-stu-id="38987-168">Exchange administrator</span></span>
* <span data-ttu-id="38987-169">Administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="38987-169">SharePoint administrator</span></span>
* <span data-ttu-id="38987-170">Administrador de contas</span><span class="sxs-lookup"><span data-stu-id="38987-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="38987-171">Funções somente leitura</span><span class="sxs-lookup"><span data-stu-id="38987-171">Read-only roles</span></span>

<span data-ttu-id="38987-172">Com o acesso somente leitura, você não é capaz de editar status ou anotações para uma ação de melhoria, editar zonas de pontuação ou editar comparações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="38987-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="38987-173">Administrador da assistência técnica</span><span class="sxs-lookup"><span data-stu-id="38987-173">Helpdesk administrator</span></span>
* <span data-ttu-id="38987-174">Administrador de usuários</span><span class="sxs-lookup"><span data-stu-id="38987-174">User administrator</span></span>
* <span data-ttu-id="38987-175">Administrador de serviço</span><span class="sxs-lookup"><span data-stu-id="38987-175">Service administrator</span></span>
* <span data-ttu-id="38987-176">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="38987-176">Security reader</span></span>
* <span data-ttu-id="38987-177">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="38987-177">Security operator</span></span>
* <span data-ttu-id="38987-178">Leitor global</span><span class="sxs-lookup"><span data-stu-id="38987-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="38987-179">Conscientização de riscos</span><span class="sxs-lookup"><span data-stu-id="38987-179">Risk awareness</span></span>

<span data-ttu-id="38987-180">A Pontuação Segura da Microsoft é um resumo numérico da postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="38987-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="38987-181">Não é uma medida absoluta de como o sistema ou os dados serão violados.</span><span class="sxs-lookup"><span data-stu-id="38987-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="38987-182">Em vez disso, ele representa a extensão em que você adotou controles de segurança em seu ambiente da Microsoft que podem ajudar a evitar o risco de violação.</span><span class="sxs-lookup"><span data-stu-id="38987-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="38987-183">Nenhum serviço online é imune a violações de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violações de segurança de qualquer maneira.</span><span class="sxs-lookup"><span data-stu-id="38987-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="38987-184">Queremos ouvir de você</span><span class="sxs-lookup"><span data-stu-id="38987-184">We want to hear from you</span></span>

<span data-ttu-id="38987-185">Se você tiver algum problema, nos avise postando na comunidade [Segurança, Privacidade & Conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="38987-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="38987-186">Estamos monitorando a comunidade e forneceremos ajuda.</span><span class="sxs-lookup"><span data-stu-id="38987-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="38987-187">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="38987-187">Related resources</span></span>

- [<span data-ttu-id="38987-188">Avaliar sua postura de segurança</span><span class="sxs-lookup"><span data-stu-id="38987-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="38987-189">Rastrear seu histórico de Pontuação Segura da Microsoft e cumprir metas</span><span class="sxs-lookup"><span data-stu-id="38987-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="38987-190">O que estar por vir.</span><span class="sxs-lookup"><span data-stu-id="38987-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="38987-191">Novidades</span><span class="sxs-lookup"><span data-stu-id="38987-191">What's new</span></span>](microsoft-secure-score-whats-new.md)