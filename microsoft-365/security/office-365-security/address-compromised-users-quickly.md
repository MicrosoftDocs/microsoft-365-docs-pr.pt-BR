---
title: Resolver contas de usuário comprometidas com investigação e resposta automatizadas
keywords: AIR, autoIR, Microsoft Defender para Ponto de Extremidade, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção, comprometido
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Saiba como acelerar o processo de detecção e endereçamento de contas de usuário comprometidas com recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c500221a10c00cc3b8d9d99c102ce8ec54fa2a48
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934688"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="f723a-104">Resolver contas de usuário comprometidas com investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="f723a-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f723a-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f723a-105">**Applies to**</span></span>
- [<span data-ttu-id="f723a-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f723a-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f723a-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f723a-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f723a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f723a-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="f723a-109">[O Microsoft Defender para Office 365 Plano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) inclui poderosos recursos automatizados de investigação [e](office-365-air.md) resposta (AIR).</span><span class="sxs-lookup"><span data-stu-id="f723a-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="f723a-110">Esses recursos podem economizar muito tempo e esforço com a equipe de operações de segurança lidando com ameaças.</span><span class="sxs-lookup"><span data-stu-id="f723a-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="f723a-111">A Microsoft continua a melhorar os recursos de segurança.</span><span class="sxs-lookup"><span data-stu-id="f723a-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="f723a-112">Recentemente, os recursos AIR foram aprimorados para incluir um playbook de segurança do usuário comprometido (atualmente na visualização).</span><span class="sxs-lookup"><span data-stu-id="f723a-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="f723a-113">Leia este artigo para saber mais sobre o playbook de segurança do usuário comprometido.</span><span class="sxs-lookup"><span data-stu-id="f723a-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="f723a-114">E consulte a postagem do blog [Acelere](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) o tempo para detectar e responder ao comprometimento do usuário e limitar o escopo de violação com o Microsoft Defender Office 365 para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="f723a-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Investigação automatizada para um usuário comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="f723a-116">O playbook de segurança do usuário comprometido permite que a equipe de segurança da sua organização:</span><span class="sxs-lookup"><span data-stu-id="f723a-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="f723a-117">Acelerar a detecção de contas de usuário comprometidas;</span><span class="sxs-lookup"><span data-stu-id="f723a-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="f723a-118">Limitar o escopo de uma violação quando uma conta for comprometida; e</span><span class="sxs-lookup"><span data-stu-id="f723a-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="f723a-119">Responder aos usuários comprometidos de forma mais eficaz e eficiente.</span><span class="sxs-lookup"><span data-stu-id="f723a-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="f723a-120">Alertas de usuário comprometidos</span><span class="sxs-lookup"><span data-stu-id="f723a-120">Compromised user alerts</span></span>

<span data-ttu-id="f723a-121">Quando uma conta de usuário é comprometida, ocorrem comportamentos atípicos ou anômalos.</span><span class="sxs-lookup"><span data-stu-id="f723a-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="f723a-122">Por exemplo, mensagens de phishing e spam podem ser enviadas internamente de uma conta de usuário confiável.</span><span class="sxs-lookup"><span data-stu-id="f723a-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="f723a-123">O Defender para Office 365 pode detectar essas anomalias nos padrões de email e na atividade de colaboração dentro Office 365.</span><span class="sxs-lookup"><span data-stu-id="f723a-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="f723a-124">Quando isso acontece, os alertas são disparados e o processo de mitigação de ameaças começa.</span><span class="sxs-lookup"><span data-stu-id="f723a-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="f723a-125">Por exemplo, aqui está um alerta que foi disparado devido ao envio de emails suspeitos:</span><span class="sxs-lookup"><span data-stu-id="f723a-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Alerta disparado por causa do envio de emails suspeitos](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="f723a-127">E aqui está um exemplo de um alerta que foi disparado quando um limite de envio foi atingido para um usuário:</span><span class="sxs-lookup"><span data-stu-id="f723a-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Alerta disparado pelo limite de envio atingido](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="f723a-129">Investigar e responder a um usuário comprometido</span><span class="sxs-lookup"><span data-stu-id="f723a-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="f723a-130">Quando uma conta de usuário é comprometida, os alertas são disparados.</span><span class="sxs-lookup"><span data-stu-id="f723a-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="f723a-131">E, em alguns casos, essa conta de usuário é bloqueada e impedida de enviar outras mensagens de email até que o problema seja resolvido pela equipe de operações de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f723a-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="f723a-132">Em outros casos, uma investigação automatizada começa, o que pode resultar em ações recomendadas que sua equipe de segurança deve tomar.</span><span class="sxs-lookup"><span data-stu-id="f723a-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="f723a-133">Exibir e investigar usuários restritos</span><span class="sxs-lookup"><span data-stu-id="f723a-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="f723a-134">Exibir detalhes sobre investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="f723a-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="f723a-135">Você deve ter permissões apropriadas para executar as seguintes tarefas.</span><span class="sxs-lookup"><span data-stu-id="f723a-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="f723a-136">Consulte [Permissões necessárias para usar recursos AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="f723a-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="f723a-137">Exibir e investigar usuários restritos</span><span class="sxs-lookup"><span data-stu-id="f723a-137">View and investigate restricted users</span></span>

<span data-ttu-id="f723a-138">Você tem algumas opções para navegar até uma lista de usuários restritos.</span><span class="sxs-lookup"><span data-stu-id="f723a-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="f723a-139">Por exemplo, no Centro de Conformidade & segurança, você pode ir **para** a Análise de Gerenciamento de Ameaças \>  \> **Usuários Restritos**.</span><span class="sxs-lookup"><span data-stu-id="f723a-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="f723a-140">O procedimento a seguir descreve a navegação usando o painel **Alertas,** que é uma boa maneira de ver vários tipos de alertas que podem ter sido disparados.</span><span class="sxs-lookup"><span data-stu-id="f723a-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="f723a-141">Acesse <https://protection.office.com> e entre.</span><span class="sxs-lookup"><span data-stu-id="f723a-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="f723a-142">No painel de navegação, escolha **Painel de** \> **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="f723a-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="f723a-143">No widget **Outros alertas,** escolha **Usuários Restritos**.</span><span class="sxs-lookup"><span data-stu-id="f723a-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Outro widget de alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="f723a-145">Isso abre a lista de usuários restritos.</span><span class="sxs-lookup"><span data-stu-id="f723a-145">This opens the list of restricted users.</span></span>

   ![Usuários restritos no Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="f723a-147">Selecione uma conta de usuário na lista para exibir detalhes e tomar medidas, como [liberar o usuário restrito](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="f723a-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="f723a-148">Exibir detalhes sobre investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="f723a-148">View details about automated investigations</span></span>

<span data-ttu-id="f723a-149">Quando uma investigação automatizada é iniciada, você pode ver seus detalhes e resultados no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="f723a-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="f723a-150">Vá para **Investigações de gerenciamento** \> **de** ameaças e selecione uma investigação para exibir seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="f723a-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="f723a-151">Para saber mais, confira [Exibir detalhes de uma investigação](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="f723a-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="f723a-152">Lembre-se dos seguintes pontos</span><span class="sxs-lookup"><span data-stu-id="f723a-152">Keep the following points in mind</span></span>

- <span data-ttu-id="f723a-153">**Fique por dentro de seus alertas.**</span><span class="sxs-lookup"><span data-stu-id="f723a-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="f723a-154">Como você sabe, quanto mais um comprometimento for detectado, maior será o potencial de impacto e custo generalizados para sua organização, clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="f723a-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="f723a-155">A detecção antecipada e a resposta em tempo hábil são fundamentais para reduzir as ameaças e, especialmente quando a conta de um usuário é comprometida.</span><span class="sxs-lookup"><span data-stu-id="f723a-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="f723a-156">**A automação ajuda, mas não substitui, sua equipe de operações de segurança.**</span><span class="sxs-lookup"><span data-stu-id="f723a-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="f723a-157">Os recursos automatizados de investigação e resposta podem detectar um usuário comprometido no início, mas sua equipe de operações de segurança provavelmente precisará se envolver e fazer alguma investigação e correção.</span><span class="sxs-lookup"><span data-stu-id="f723a-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="f723a-158">Precisa de ajuda com isso?</span><span class="sxs-lookup"><span data-stu-id="f723a-158">Need some help with this?</span></span> <span data-ttu-id="f723a-159">Consulte [Revisar e aprovar ações.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="f723a-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="f723a-160">**Não confie em um alerta de logon suspeito como seu único indicador**.</span><span class="sxs-lookup"><span data-stu-id="f723a-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="f723a-161">Quando uma conta de usuário é comprometida, ela pode ou não disparar um alerta de logon suspeito.</span><span class="sxs-lookup"><span data-stu-id="f723a-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="f723a-162">Às vezes, é a série de atividades que ocorrem depois que uma conta é comprometida que dispara um alerta.</span><span class="sxs-lookup"><span data-stu-id="f723a-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="f723a-163">Quer saber mais sobre alertas?</span><span class="sxs-lookup"><span data-stu-id="f723a-163">Want to know more about alerts?</span></span> <span data-ttu-id="f723a-164">Consulte [Políticas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f723a-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f723a-165">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f723a-165">Next steps</span></span>

- [<span data-ttu-id="f723a-166">Revise as permissões necessárias para usar recursos AIR</span><span class="sxs-lookup"><span data-stu-id="f723a-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="f723a-167">Encontre e investigue emails mal-intencionados Office 365</span><span class="sxs-lookup"><span data-stu-id="f723a-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="f723a-168">Saiba mais sobre AIR no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f723a-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="f723a-169">Visite o Microsoft 365 mapa do Microsoft 365 para ver o que está por vir em breve e a ser implantada</span><span class="sxs-lookup"><span data-stu-id="f723a-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)