---
title: Endereçar contas de usuário comprometidas com investigação e resposta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção, comprometido
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Saiba como acelerar o processo de detecção e endereçamento de contas de usuário comprometidas com recursos de investigação e resposta automatizados no Microsoft defender para Office 365 plano 2.
ms.openlocfilehash: 0da065bea17796d09de771a767991804afb5335b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844591"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="5cf0f-104">Endereçar contas de usuário comprometidas com investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="5cf0f-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5cf0f-105">[O Microsoft defender para Office 365 plano 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) inclui recursos avançados de [investigação e resposta automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-105">[Microsoft Defender for Office 365 Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) includes powerful [automated investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) capabilities.</span></span> <span data-ttu-id="5cf0f-106">Esses recursos podem economizar sua equipe de operações de segurança muito tempo e esforço lidando com ameaças.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="5cf0f-107">A Microsoft continua a melhorar os recursos de segurança.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="5cf0f-108">Recentemente, os recursos de ar foram aprimorados para incluir um guia de segurança de usuário comprometido (atualmente em versão prévia).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="5cf0f-109">Leia este artigo para saber mais sobre o guia de segurança de usuário comprometido.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="5cf0f-110">E veja a velocidade da postagem do blog [para detectar e responder ao escopo do usuário e limitar o escopo de violação com o Microsoft defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Investigação automatizada para um usuário comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="5cf0f-112">O guia de segurança do usuário comprometido permite que a equipe de segurança da sua organização:</span><span class="sxs-lookup"><span data-stu-id="5cf0f-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="5cf0f-113">Acelerar a detecção de contas de usuário comprometidas;</span><span class="sxs-lookup"><span data-stu-id="5cf0f-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="5cf0f-114">Limitar o escopo de uma violação quando uma conta for comprometida; e</span><span class="sxs-lookup"><span data-stu-id="5cf0f-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="5cf0f-115">Responder aos usuários comprometidos de forma mais eficaz e eficiente.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="5cf0f-116">Alertas de usuário comprometidos</span><span class="sxs-lookup"><span data-stu-id="5cf0f-116">Compromised user alerts</span></span>

<span data-ttu-id="5cf0f-117">Quando uma conta de usuário está comprometida, ocorrem comportamentos atypical ou anômalas.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="5cf0f-118">Por exemplo, mensagens de phishing e spam podem ser enviadas internamente por uma conta de usuário confiável.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="5cf0f-119">O defender para Office 365 pode detectar essas anomalias em padrões de email e atividade de colaboração no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="5cf0f-120">Quando isso acontecer, os alertas serão acionados e o processo de mitigação de ameaças começará.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="5cf0f-121">Por exemplo, aqui está um alerta que foi acionado devido a um envio de emails suspeitos:</span><span class="sxs-lookup"><span data-stu-id="5cf0f-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Alerta acionado devido a envio de emails suspeitos](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="5cf0f-123">E aqui está um exemplo de um alerta que foi disparado quando um limite de envio foi atingido para um usuário:</span><span class="sxs-lookup"><span data-stu-id="5cf0f-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Alerta iniciado pelo limite de envio alcançado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="5cf0f-125">Investigar e responder a um usuário comprometido</span><span class="sxs-lookup"><span data-stu-id="5cf0f-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="5cf0f-126">Quando uma conta de usuário é comprometida, os alertas são acionados.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="5cf0f-127">E, em alguns casos, essa conta de usuário é bloqueada e impedida de enviar outras mensagens de email até que o problema seja resolvido pela equipe de operações de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="5cf0f-128">Em outros casos, uma investigação automatizada começa, o que pode resultar em ações recomendadas que a equipe de segurança deve executar.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="5cf0f-129">Exibir e investigar usuários restritos</span><span class="sxs-lookup"><span data-stu-id="5cf0f-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="5cf0f-130">Exibir detalhes sobre investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="5cf0f-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="5cf0f-131">Você deve ter as permissões apropriadas para executar as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="5cf0f-132">Confira [as permissões necessárias para usar os recursos de ar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-132">See [Required permissions to use AIR capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="5cf0f-133">Exibir e investigar usuários restritos</span><span class="sxs-lookup"><span data-stu-id="5cf0f-133">View and investigate restricted users</span></span>

<span data-ttu-id="5cf0f-134">Você tem algumas opções para navegar para uma lista de usuários restritos.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="5cf0f-135">Por exemplo, no centro de conformidade & segurança, você pode ir para **Gerenciamento de ameaças**  >  **examinar**  >  **usuários restritos**.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="5cf0f-136">O procedimento a seguir descreve a navegação usando o painel de **alertas** , que é uma boa maneira de ver vários tipos de alertas que podem ter sido acionados.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="5cf0f-137">Vá para [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="5cf0f-138">No painel de navegação, escolha **Alerts**  >  **painel** de alerta.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="5cf0f-139">No widget **outros alertas** , escolha **usuários restritos**.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget outros alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="5cf0f-141">Isso abre a lista de usuários restritos.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-141">This opens the list of restricted users.</span></span><br/>![Usuários restritos no Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="5cf0f-143">Selecione uma conta de usuário na lista para exibir detalhes e executar ação, como [liberar o usuário restrito](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="5cf0f-144">Exibir detalhes sobre investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="5cf0f-144">View details about automated investigations</span></span>

<span data-ttu-id="5cf0f-145">Quando uma investigação automatizada começou, você poderá ver seus detalhes e resultados no centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="5cf0f-146">Vá para **Threat management**  >  **investigações** de gerenciamento de ameaças e selecione uma investigação para exibir seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-146">Go to **Threat management** > **Investigations** , and then select an investigation to view its details.</span></span>

<span data-ttu-id="5cf0f-147">Para saber mais, confira [Exibir detalhes de uma investigação](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-147">To learn more, see [View details of an investigation](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="5cf0f-148">Tenha em mente os seguintes pontos</span><span class="sxs-lookup"><span data-stu-id="5cf0f-148">Keep the following points in mind</span></span>

- <span data-ttu-id="5cf0f-149">**Fique em cima dos alertas**.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="5cf0f-150">Como você sabe, quanto mais tempo um compromisso não for detectado, maior será o potencial de impacto e custo amplos para sua organização, clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="5cf0f-151">A detecção antecipada e a resposta oportuna são fundamentais para reduzir as ameaças e, especialmente, quando a conta de um usuário é comprometida.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="5cf0f-152">**A automação auxilia, mas não substitui, sua equipe de operações de segurança**.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="5cf0f-153">Os recursos de investigação e resposta automatizados podem detectar um usuário comprometido logo no início, mas sua equipe de operações de segurança provavelmente precisará participar e realizar algumas investigações e remediação.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="5cf0f-154">Precisa de ajuda para isso?</span><span class="sxs-lookup"><span data-stu-id="5cf0f-154">Need some help with this?</span></span> <span data-ttu-id="5cf0f-155">Consulte [revisar e aprovar ações](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-155">See [Review and approve actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span></span>

- <span data-ttu-id="5cf0f-156">**Não confie em um alerta de login suspeito como seu único indicador**.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="5cf0f-157">Quando uma conta de usuário é comprometida, ela pode ou não disparar um alerta de login suspeito.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="5cf0f-158">Às vezes, é a série de atividades que ocorrem após o comprometimento de uma conta que dispara um alerta.</span><span class="sxs-lookup"><span data-stu-id="5cf0f-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="5cf0f-159">Quer saber mais sobre os alertas?</span><span class="sxs-lookup"><span data-stu-id="5cf0f-159">Want to know more about alerts?</span></span> <span data-ttu-id="5cf0f-160">Consulte [políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="5cf0f-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5cf0f-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5cf0f-161">Next steps</span></span>

- [<span data-ttu-id="5cf0f-162">Revise as permissões necessárias para usar os recursos de ar</span><span class="sxs-lookup"><span data-stu-id="5cf0f-162">Review the required permissions to use AIR capabilities</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="5cf0f-163">Encontre e investigue emails mal-intencionados no Office 365</span><span class="sxs-lookup"><span data-stu-id="5cf0f-163">Find and investigate malicious email in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [<span data-ttu-id="5cf0f-164">Saiba mais sobre o AIR no Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="5cf0f-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="5cf0f-165">Visite o mapa do Microsoft 365 para ver o que está chegando em breve e distribuir</span><span class="sxs-lookup"><span data-stu-id="5cf0f-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

