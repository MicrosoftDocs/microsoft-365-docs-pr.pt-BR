---
title: Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Os administradores podem aprender a usar a política de entrega avançada no Exchange Online Protection (EOP) para identificar mensagens que não devem ser filtradas em cenários com suporte específico (simulações de phishing de terceiros e mensagens entregues às caixas de correio de operações de segurança (SecOps).
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760423"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="e542d-103">Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps</span><span class="sxs-lookup"><span data-stu-id="e542d-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="e542d-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e542d-104">**Applies to**</span></span>
- [<span data-ttu-id="e542d-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e542d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e542d-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e542d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e542d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e542d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e542d-108">O recurso descrito neste artigo está em Visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="e542d-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="e542d-109">Queremos manter sua organização segura por [padrão,](secure-by-default.md)para que a Proteção do Exchange Online (EOP) não permita listas seguras ou bypass de filtragem para mensagens que resultem em malware ou vereditos de phishing de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="e542d-109">We want to keep your organization [secure by default](secure-by-default.md), so Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="e542d-110">No entanto, reconhecemos que há cenários específicos que exigem a entrega de mensagens não filtradas.</span><span class="sxs-lookup"><span data-stu-id="e542d-110">But, we recognize there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="e542d-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e542d-111">For example:</span></span>

- <span data-ttu-id="e542d-112">**Simulações de phishing de** terceiros : Ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real impacte sua organização.</span><span class="sxs-lookup"><span data-stu-id="e542d-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="e542d-113">Caixas de correio de operações de segurança **(SecOps)**: Caixas de correio dedicadas que são usadas pelas equipes de segurança para coletar e analisar mensagens não filtradas (boas e ruins).</span><span class="sxs-lookup"><span data-stu-id="e542d-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="e542d-114">Você usa a _política de entrega_ avançada no Microsoft 365 para impedir que essas mensagens nesses _cenários específicos_ seja filtrada. <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e542d-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="e542d-115">A política de entrega avançada garante que as mensagens nesses cenários não sejam filtradas:</span><span class="sxs-lookup"><span data-stu-id="e542d-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="e542d-116">Os filtros no EOP e no Microsoft Defender para Office 365 não têm nenhuma ação nessas mensagens.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e542d-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="e542d-117">[A limpeza zero hora (ZAP)](zero-hour-auto-purge.md) para spam e phishing não toma nenhuma ação nessas mensagens.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e542d-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="e542d-118">[Os alertas padrão do](alerts.md) sistema não são disparados para esses cenários.</span><span class="sxs-lookup"><span data-stu-id="e542d-118">[Default system alerts](alerts.md) are not triggered for these scenarios.</span></span>
- <span data-ttu-id="e542d-119">[AIR e clustering no Defender para Office 365](office-365-air.md) ignora essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="e542d-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="e542d-120">Especificamente para simulações de phishing de terceiros:</span><span class="sxs-lookup"><span data-stu-id="e542d-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="e542d-121">[Os envios de administrador](admin-submission.md) geram uma resposta automática informando que a mensagem faz parte de uma campanha de simulação de phishing e não é uma ameaça real.</span><span class="sxs-lookup"><span data-stu-id="e542d-121">[Admin submissions](admin-submission.md) generates an automatic response stating that the message is part of a phishing simulation campaign and is not a real threat.</span></span> <span data-ttu-id="e542d-122">Os alertas e o AIR não serão disparados.</span><span class="sxs-lookup"><span data-stu-id="e542d-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="e542d-123">[Os Links Seguros no Defender para Office 365](safe-links.md) não bloqueiam ou detonam as URLs especificamente identificadas nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="e542d-123">[Safe Links in Defender for Office 365](safe-links.md) does not block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="e542d-124">[Anexos seguros no Defender para Office 365](safe-attachments.md) não detona anexos nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="e542d-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) does not detonate attachments in these messages.</span></span>

<span data-ttu-id="e542d-125"><sup>\*</sup> Não é possível ignorar a filtragem de malware ou o ZAP para malware.</span><span class="sxs-lookup"><span data-stu-id="e542d-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="e542d-126">As mensagens identificadas pela política de entrega avançada não são ameaças de segurança, portanto, as mensagens são marcadas como substituições do sistema.</span><span class="sxs-lookup"><span data-stu-id="e542d-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="e542d-127">Os administradores podem filtrar e analisar essas substituições do sistema nas seguintes experiências:</span><span class="sxs-lookup"><span data-stu-id="e542d-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="e542d-128">Explorador de Ameaças/Detecções em tempo real no Defender para Office 365 plano 2</span><span class="sxs-lookup"><span data-stu-id="e542d-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="e542d-129">A [Página da entidade email no Explorador de Ameaças/Detecções em tempo real](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="e542d-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="e542d-130">O [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e542d-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="e542d-131">Busca avançada no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e542d-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="e542d-132">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="e542d-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e542d-133">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="e542d-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e542d-134">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e542d-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e542d-135">Para ir diretamente para a **página Entrega** Avançada, abra <https://protection.office.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="e542d-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="e542d-136">Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="e542d-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e542d-137">Para criar, modificar ou remover configurações configuradas na política de entrega  avançada **&,** você precisa ser membro do grupo de  função Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de função Gerenciamento da Organização no **Exchange Online.**</span><span class="sxs-lookup"><span data-stu-id="e542d-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="e542d-138">Para acesso somente leitura à política de entrega avançada, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="e542d-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e542d-139">Para obter mais informações, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e542d-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="e542d-140">Use o Centro de Conformidade & segurança para configurar simulações de phishing de terceiros na política de entrega avançada</span><span class="sxs-lookup"><span data-stu-id="e542d-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="e542d-141">No Centro de Conformidade & segurança, vá para **a Entrega** Avançada da Política de Gerenciamento de \>  \> **Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="e542d-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="e542d-142">Na página **Entrega Avançada,** selecione a guia **Simulação de Phishing** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e542d-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="e542d-143">No **sub-sublinhado de simulação de phishing** de terceiros que é aberto, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e542d-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e542d-144">**Domínio de** envio : é necessário pelo menos um domínio de endereço de email (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e542d-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="e542d-145">Você pode adicionar até 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="e542d-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="e542d-146">**Envio de IP**: é necessário pelo menos um endereço IPv4 válido.</span><span class="sxs-lookup"><span data-stu-id="e542d-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="e542d-147">Você pode adicionar até 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="e542d-147">You can add up to 10 entries.</span></span> <span data-ttu-id="e542d-148">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="e542d-148">Valid values are:</span></span>
     - <span data-ttu-id="e542d-149">IP único: por exemplo, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="e542d-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="e542d-150">Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="e542d-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="e542d-151">IP CIDR: Por exemplo, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="e542d-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="e542d-152">**URLs de** simulação para permitir : Opcionalmente, insira URLs específicas que fazem parte da sua campanha de simulação de phishing que não devem ser bloqueadas ou detonadas.</span><span class="sxs-lookup"><span data-stu-id="e542d-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="e542d-153">Você pode adicionar até 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="e542d-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="e542d-154">Quando terminar, clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="e542d-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="e542d-155">As entradas de simulação de phishing de terceiros que você configurou são exibidas na guia **Simulação de Phishing.** Para fazer alterações, clique **em Editar** na guia.</span><span class="sxs-lookup"><span data-stu-id="e542d-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="e542d-156">Use o Centro de Conformidade & segurança para configurar caixas de correio SecOps na política de entrega avançada</span><span class="sxs-lookup"><span data-stu-id="e542d-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="e542d-157">No Centro de Conformidade & segurança, vá para **Política de Gerenciamento** de Ameaças Entrega \>  \> **avançada**.</span><span class="sxs-lookup"><span data-stu-id="e542d-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="e542d-158">Na página **Entrega Avançada,** selecione a guia Caixa **de Correio SecOps** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e542d-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="e542d-159">No sobrevoo de caixa de correio **SecOps** que é aberto, insira os endereços de email das caixas de correio existentes do Exchange Online que você deseja designar como caixas de correio SecOps.</span><span class="sxs-lookup"><span data-stu-id="e542d-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="e542d-160">Grupos de distribuição não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e542d-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="e542d-161">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e542d-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="e542d-162">As entradas de caixa de correio SecOps que você configurou são exibidas na guia caixa de **correio SecOps.** Para fazer alterações, clique **em Editar** na guia.</span><span class="sxs-lookup"><span data-stu-id="e542d-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="e542d-163">Cenários adicionais que exigem bypass de filtragem</span><span class="sxs-lookup"><span data-stu-id="e542d-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="e542d-164">Além dos dois cenários em que a política de entrega avançada pode ajudá-lo, há outros cenários que podem exigir que você ignore a filtragem:</span><span class="sxs-lookup"><span data-stu-id="e542d-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="e542d-165">**Filtros de** terceiros : se o registro MX do domínio não apontar para o Office 365 (as mensagens são roteadas primeiro para outro [lugar),](secure-by-default.md) a segurança por padrão não está disponível.</span><span class="sxs-lookup"><span data-stu-id="e542d-165">**Third-party filters**: If you domain's MX record doesn't point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) is not available.</span></span>

  <span data-ttu-id="e542d-166">Para ignorar a filtragem da Microsoft para mensagens que já foram avaliadas pela filtragem de terceiros, use regras de fluxo de emails (também conhecidas como regras de transporte), consulte [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e542d-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

- <span data-ttu-id="e542d-167">**Falsos positivos** em revisão : talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft por meio de envios de administrador para relatar mensagens boas [conhecidas](admin-submission.md) que estão sendo marcadas incorretamente como ruins para a Microsoft (falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="e542d-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="e542d-168">Como com todas as substituições, é altamente recomendável que essas concessões sejam temporárias.</span><span class="sxs-lookup"><span data-stu-id="e542d-168">As with all overrides, we highly recommended that these allowances are temporary.</span></span>
