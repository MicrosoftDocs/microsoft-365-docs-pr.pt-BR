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
description: Os administradores podem aprender a usar a política de entrega avançada no Proteção do Exchange Online (EOP) para identificar mensagens que não devem ser filtradas em cenários com suporte específico (simulações de phishing de terceiros e mensagens entregues às caixas de correio de operações de segurança (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d35c1f0c7abc7b6ce34fc9c2ec4d5fd5b228ae
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137734"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="518fe-103">Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="518fe-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="518fe-104">**Applies to**</span></span>
- [<span data-ttu-id="518fe-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="518fe-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="518fe-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="518fe-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="518fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="518fe-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="518fe-108">O recurso descrito neste artigo está em Visualização, não está disponível para todos e está sujeito a alterações.</span><span class="sxs-lookup"><span data-stu-id="518fe-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="518fe-109">Para manter sua organização segura por [padrão,](secure-by-default.md)o Proteção do Exchange Online (EOP) não permite listas seguras ou bypass de filtragem para mensagens identificadas como malware ou phishing de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="518fe-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="518fe-110">Porém, há cenários específicos que exigem a entrega de mensagens não filtradas.</span><span class="sxs-lookup"><span data-stu-id="518fe-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="518fe-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="518fe-111">For example:</span></span>

- <span data-ttu-id="518fe-112">**Simulações de phishing de** terceiros : Ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real impacte sua organização.</span><span class="sxs-lookup"><span data-stu-id="518fe-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="518fe-113">Caixas de correio de operações de segurança **(SecOps)**: Caixas de correio dedicadas que são usadas pelas equipes de segurança para coletar e analisar mensagens não filtradas (boas e ruins).</span><span class="sxs-lookup"><span data-stu-id="518fe-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="518fe-114">Você usa a _política de entrega_ avançada Microsoft 365 impedir que essas mensagens nesses _cenários específicos_ seja filtrada. <sup>\*</sup> A política de entrega avançada garante que as mensagens nesses cenários alcancem os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="518fe-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="518fe-115">Os filtros no EOP e no Microsoft Defender Office 365 tomar nenhuma ação nessas mensagens.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="518fe-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="518fe-116">[A limpeza zero hora (ZAP)](zero-hour-auto-purge.md) para spam e phishing não toma nenhuma ação nessas mensagens.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="518fe-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="518fe-117">[Os alertas padrão do](alerts.md) sistema não são disparados para esses cenários.</span><span class="sxs-lookup"><span data-stu-id="518fe-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="518fe-118">[AIR e clustering no Defender para Office 365](office-365-air.md) ignora essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="518fe-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="518fe-119">Especificamente para simulações de phishing de terceiros:</span><span class="sxs-lookup"><span data-stu-id="518fe-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="518fe-120">[Os envios de administrador](admin-submission.md) geram uma resposta automática dizendo que a mensagem faz parte de uma campanha de simulação de phishing e não é uma ameaça real.</span><span class="sxs-lookup"><span data-stu-id="518fe-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="518fe-121">Os alertas e o AIR não serão disparados.</span><span class="sxs-lookup"><span data-stu-id="518fe-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="518fe-122">[Cofre Links no Defender para Office 365](safe-links.md) não bloqueia ou detona as URLs especificamente identificadas nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="518fe-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="518fe-123">[Cofre Anexos no Defender para](safe-attachments.md) Office 365 não detona anexos nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="518fe-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="518fe-124"><sup>\*</sup> Não é possível ignorar a filtragem de malware ou o ZAP para malware.</span><span class="sxs-lookup"><span data-stu-id="518fe-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="518fe-125">As mensagens identificadas pela política de entrega avançada não são ameaças de segurança, portanto, as mensagens são marcadas como substituições do sistema.</span><span class="sxs-lookup"><span data-stu-id="518fe-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="518fe-126">Os administradores podem filtrar e analisar essas substituições do sistema nas seguintes experiências:</span><span class="sxs-lookup"><span data-stu-id="518fe-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="518fe-127">Explorador de Ameaças/Detecções em tempo real no Defender para Office 365 plano 2</span><span class="sxs-lookup"><span data-stu-id="518fe-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="518fe-128">A [Página da entidade email no Explorador de Ameaças/Detecções em tempo real](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="518fe-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="518fe-129">O [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="518fe-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="518fe-130">Busca avançada no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="518fe-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="518fe-131">Modos de Exibição de Campanha</span><span class="sxs-lookup"><span data-stu-id="518fe-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="518fe-132">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="518fe-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="518fe-133">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="518fe-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="518fe-134">Para ir diretamente para a **página Entrega** Avançada, abra <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="518fe-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="518fe-135">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="518fe-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="518fe-136">Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="518fe-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="518fe-137">Para criar, modificar ou remover configurações configuradas na política de entrega  avançada, você precisa ser membro do grupo de  função Administrador de Segurança no **portal do Microsoft 365 Defender** e membro do grupo de função Gerenciamento da Organização **no Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="518fe-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="518fe-138">Para acesso somente leitura à política de entrega avançada, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="518fe-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="518fe-139">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="518fe-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="518fe-140">Adicionar usuários à função Azure Active Directory correspondente fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="518fe-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="518fe-141">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="518fe-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="518fe-142">Use o portal Microsoft 365 Defender para configurar caixas de correio SecOps na política de entrega avançada</span><span class="sxs-lookup"><span data-stu-id="518fe-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="518fe-143">No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Regras De acordo com a página Regras seção Entrega \>  \>  \>  \> **avançada**.</span><span class="sxs-lookup"><span data-stu-id="518fe-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="518fe-144">Na página **Entrega Avançada,** verifique se a guia caixa de correio **SecOps** está selecionada e, em seguida, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="518fe-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="518fe-145">Clique ![ em Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="518fe-146">Se não houver simulações de phishing configuradas, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="518fe-147">No sobrevoo Editar caixas de correio **SecOps** que são abertas, insira uma caixa de correio Exchange Online existente que você deseja designar como caixa de correio SecOps, seguindo uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="518fe-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="518fe-148">Clique na caixa, deixe a lista de caixas de correio resolver e selecione a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="518fe-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="518fe-149">Clique na caixa comece a digitar um identificador para a caixa de correio (nome, nome de exibição, alias, endereço de email, nome da conta etc.) e selecione a caixa de correio (nome de exibição) dos resultados.</span><span class="sxs-lookup"><span data-stu-id="518fe-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="518fe-150">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="518fe-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="518fe-151">Grupos de distribuição não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="518fe-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="518fe-152">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="518fe-152">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="518fe-154">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="518fe-154">next to the value.</span></span>

4. <span data-ttu-id="518fe-155">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="518fe-156">As entradas de caixa de correio SecOps que você configurou são exibidas na guia caixa de **correio SecOps.** Para fazer alterações, clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar** na guia.</span><span class="sxs-lookup"><span data-stu-id="518fe-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="518fe-157">Use o Microsoft 365 Defender portal para configurar simulações de phishing de terceiros na política de entrega avançada</span><span class="sxs-lookup"><span data-stu-id="518fe-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="518fe-158">No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Regras De acordo com a página Regras seção Entrega \>  \>  \>  \> **avançada**.</span><span class="sxs-lookup"><span data-stu-id="518fe-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="518fe-159">Na página **Entrega Avançada,** selecione a guia **Simulação de Phishing** e, em seguida, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="518fe-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="518fe-160">Clique ![ em Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="518fe-161">Se não houver simulações de phishing configuradas, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="518fe-162">No **sub-sublinhado Editar simulação de phishing** de terceiros que é aberto, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="518fe-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="518fe-163">**Domínio** de envio : expanda essa configuração e insira pelo menos um domínio de endereço de email (por exemplo, contoso.com) clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="518fe-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="518fe-164">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="518fe-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="518fe-165">Você pode adicionar até 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="518fe-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="518fe-166">**Envio de IP**: expanda essa configuração e insira pelo menos um endereço IPv4 válido é necessário clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="518fe-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="518fe-167">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="518fe-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="518fe-168">Você pode adicionar até 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="518fe-168">You can add up to 10 entries.</span></span> <span data-ttu-id="518fe-169">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="518fe-169">Valid values are:</span></span>
     - <span data-ttu-id="518fe-170">IP único: por exemplo, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="518fe-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="518fe-171">Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="518fe-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="518fe-172">IP CIDR: Por exemplo, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="518fe-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="518fe-173">**URLs** de simulação para permitir : Expanda essa configuração e, opcionalmente, insira URLs específicas que fazem parte da sua campanha de simulação de phishing que não devem ser bloqueadas ou detonadas clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="518fe-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="518fe-174">Você pode adicionar até 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="518fe-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="518fe-175">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="518fe-175">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="518fe-177">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="518fe-177">next to the value.</span></span>

4. <span data-ttu-id="518fe-178">Quando terminar, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="518fe-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="518fe-179">**Primeira vez:** clique **em Adicionar** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="518fe-180">**Editar existente**: clique em **Salvar** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="518fe-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="518fe-181">As entradas de simulação de phishing de terceiros que você configurou são exibidas na guia **Simulação de Phishing.** Para fazer alterações, clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar** na guia.</span><span class="sxs-lookup"><span data-stu-id="518fe-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="518fe-182">Cenários adicionais que exigem bypass de filtragem</span><span class="sxs-lookup"><span data-stu-id="518fe-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="518fe-183">Além dos dois cenários em que a política de entrega avançada pode ajudá-lo, há outros cenários que podem exigir que você ignore a filtragem:</span><span class="sxs-lookup"><span data-stu-id="518fe-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="518fe-184">**Filtros de** terceiros : Se o  registro MX do seu domínio não apontar para o Office 365 (as mensagens são roteadas primeiro para outro [lugar),](secure-by-default.md) a segurança por padrão não está *disponível*.</span><span class="sxs-lookup"><span data-stu-id="518fe-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="518fe-185">Se você quiser adicionar proteção, será necessário habilitar a Filtragem Aprimorada para Conectores (também conhecida como *lista de ignorar).*</span><span class="sxs-lookup"><span data-stu-id="518fe-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="518fe-186">Para obter mais informações, consulte [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span><span class="sxs-lookup"><span data-stu-id="518fe-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="518fe-187">Se você não quiser Filtragem Aprimorada para Conectores, use regras de fluxo de emails (também conhecidas como regras de transporte) para ignorar a filtragem da Microsoft para mensagens que já foram avaliadas pela filtragem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="518fe-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="518fe-188">Para obter mais informações, [consulte Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span><span class="sxs-lookup"><span data-stu-id="518fe-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="518fe-189">**Falsos positivos** em revisão : talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft por meio de envios de administrador para relatar mensagens boas [conhecidas](admin-submission.md) que estão sendo marcadas incorretamente como ruins para a Microsoft (falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="518fe-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="518fe-190">Como com todas as substituições, é **_altamente recomendável_** que essas concessões sejam temporárias.</span><span class="sxs-lookup"><span data-stu-id="518fe-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="518fe-191">Exchange Online Procedimentos do PowerShell para caixas de correio SecOps na política de entrega avançada</span><span class="sxs-lookup"><span data-stu-id="518fe-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="518fe-192">No Exchange Online PowerShell, os elementos básicos das caixas de correio SecOps na política de entrega avançada são:</span><span class="sxs-lookup"><span data-stu-id="518fe-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="518fe-193">**A política de substituição de SecOps**: Controlada pelos cmdlets **\* -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="518fe-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="518fe-194">**A regra de substituição SecOps**: Controlada pelos cmdlets **\* -SecOpsOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="518fe-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="518fe-195">Esse comportamento tem os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="518fe-195">This behavior has the following results:</span></span>

- <span data-ttu-id="518fe-196">Primeiro você cria a política e, em seguida, cria a regra que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="518fe-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="518fe-197">Quando você remove uma política do PowerShell, a regra correspondente também é removida.</span><span class="sxs-lookup"><span data-stu-id="518fe-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="518fe-198">Quando você remove uma regra do PowerShell, a política correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="518fe-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="518fe-199">Você precisa remover a política correspondente manualmente.</span><span class="sxs-lookup"><span data-stu-id="518fe-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="518fe-200">Usar o PowerShell para configurar caixas de correio SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="518fe-201">Configurar uma caixa de correio SecOps na política de entrega avançada no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="518fe-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="518fe-202">Crie a política de substituição SecOps.</span><span class="sxs-lookup"><span data-stu-id="518fe-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="518fe-203">Crie a regra de substituição SecOps que especifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="518fe-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="518fe-204">Etapa 1: Usar o PowerShell para criar a política de substituição de SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="518fe-205">Para criar a política de substituição SecOps, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="518fe-206">**Observação**: independentemente do valor Name que você especificar, o nome da política será SecOpsOverridePolicy, portanto, é melhor usar esse valor.</span><span class="sxs-lookup"><span data-stu-id="518fe-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="518fe-207">Este exemplo cria a política de caixa de correio SecOps.</span><span class="sxs-lookup"><span data-stu-id="518fe-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SendTo secops@contoso.com
```

<span data-ttu-id="518fe-208">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="518fe-209">Etapa 2: Usar o PowerShell para criar a regra de substituição SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="518fe-210">Este exemplo cria a regra de caixa de correio SecOps com as configurações especificadas.</span><span class="sxs-lookup"><span data-stu-id="518fe-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="518fe-211">**Observação**: \*\*Independentemente do valor name especificado, o nome da regra será SecOpsOverrideRule, onde é um valor GUID exclusivo \<GUID\> \<GUID\> (por exemplo, 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="518fe-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="518fe-212">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="518fe-213">Use o PowerShell para exibir a política de substituição SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="518fe-214">Este exemplo retorna informações detalhadas sobre a única e única política de caixa de correio SecOps.</span><span class="sxs-lookup"><span data-stu-id="518fe-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="518fe-215">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="518fe-216">Usar o PowerShell para exibir regras de substituição de SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="518fe-217">Este exemplo retorna informações detalhadas sobre regras de substituição de SecOps.</span><span class="sxs-lookup"><span data-stu-id="518fe-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="518fe-218">Embora o comando anterior deva retornar apenas uma regra, todas as regras que estão pendentes de exclusão também podem ser incluídas nos resultados.</span><span class="sxs-lookup"><span data-stu-id="518fe-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="518fe-219">Este exemplo identifica a regra válida (uma) e quaisquer regras inválidas.</span><span class="sxs-lookup"><span data-stu-id="518fe-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="518fe-220">Depois de identificar as regras inválidas, você pode removê-las usando o cmdlet **Remove-SecOpsOverrideRule** conforme descrito posteriormente [neste artigo](#use-powershell-to-remove-secops-override-rules).</span><span class="sxs-lookup"><span data-stu-id="518fe-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="518fe-221">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="518fe-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="518fe-222">Usar o PowerShell para modificar a política de substituição de SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="518fe-223">Para modificar a política de substituição SecOps, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="518fe-224">Este exemplo adiciona secops2@contoso.com à política de substituição SecOps.</span><span class="sxs-lookup"><span data-stu-id="518fe-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="518fe-225">**Observação**: se existir uma regra de substituição secOps associada e válida, os endereços de email na regra também serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="518fe-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="518fe-226">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="518fe-227">Usar o PowerShell para modificar uma regra de substituição SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="518fe-228">O cmdlet **Set-SecOpsOverrideRule** não modifica os endereços de email na regra de substituição SecOps.</span><span class="sxs-lookup"><span data-stu-id="518fe-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="518fe-229">Para modificar os endereços de email na regra de substituição SecOps, use o cmdlet **Set-SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="518fe-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="518fe-230">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="518fe-231">Use o PowerShell para remover a política de substituição SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="518fe-232">Este exemplo remove a política de Caixa de Correio SecOps e a regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="518fe-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="518fe-233">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="518fe-234">Usar o PowerShell para remover regras de substituição de SecOps</span><span class="sxs-lookup"><span data-stu-id="518fe-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="518fe-235">Para remover uma regra de substituição SecOps, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="518fe-236">Este exemplo remove a regra de substituição SecOps especificada.</span><span class="sxs-lookup"><span data-stu-id="518fe-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="518fe-237">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="518fe-238">Exchange Online Procedimentos do PowerShell para simulações de phishing de terceiros na política de entrega avançada</span><span class="sxs-lookup"><span data-stu-id="518fe-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="518fe-239">No Exchange Online PowerShell, os elementos básicos de simulações de phishing de terceiros na política de entrega avançada são:</span><span class="sxs-lookup"><span data-stu-id="518fe-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="518fe-240">**A política de substituição de simulação de phishing**: Controlada pelos cmdlets **\* -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="518fe-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="518fe-241">**A regra de substituição de simulação de phishing**: Controlada pelos cmdlets **\* -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="518fe-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="518fe-242">Esse comportamento tem os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="518fe-242">This behavior has the following results:</span></span>

- <span data-ttu-id="518fe-243">Primeiro você cria a política e, em seguida, cria a regra que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="518fe-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="518fe-244">Você modifica as configurações da política e da regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="518fe-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="518fe-245">Quando você remove uma política do PowerShell, a regra correspondente também é removida.</span><span class="sxs-lookup"><span data-stu-id="518fe-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="518fe-246">Quando você remove uma regra do PowerShell, a política correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="518fe-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="518fe-247">Você precisa remover a política correspondente manualmente.</span><span class="sxs-lookup"><span data-stu-id="518fe-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="518fe-248">Usar o PowerShell para configurar simulações de phishing de terceiros</span><span class="sxs-lookup"><span data-stu-id="518fe-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="518fe-249">Configurar uma simulação de phishing de terceiros na política de entrega avançada no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="518fe-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="518fe-250">Crie a política de substituição de simulação de phishing.</span><span class="sxs-lookup"><span data-stu-id="518fe-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="518fe-251">Crie a regra de substituição de simulação de phishing que especifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="518fe-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="518fe-252">Etapa 1: Usar o PowerShell para criar a política de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="518fe-253">Este exemplo cria a política de substituição de simulação de phishing.</span><span class="sxs-lookup"><span data-stu-id="518fe-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="518fe-254">**Observação**: independentemente do valor Name especificado, o nome da política será PhishSimOverridePolicy, portanto, é melhor usar esse valor.</span><span class="sxs-lookup"><span data-stu-id="518fe-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="518fe-255">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="518fe-256">Etapa 2: usar o PowerShell para criar a regra de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="518fe-257">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="518fe-258">Independentemente do valor name especificado, o nome da regra será PhishSimOverrideRule, onde é um valor GUID exclusivo \<GUID\> \<GUID\> (por exemplo, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="518fe-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="518fe-259">Uma entrada de endereço IP válida é um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="518fe-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="518fe-260">IP único: por exemplo, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="518fe-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="518fe-261">Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="518fe-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="518fe-262">IP CIDR: Por exemplo, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="518fe-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="518fe-263">Este exemplo cria a regra de substituição de simulação de phishing com as configurações especificadas.</span><span class="sxs-lookup"><span data-stu-id="518fe-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="518fe-264">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="518fe-265">Usar o PowerShell para exibir a política de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="518fe-266">Este exemplo retorna informações detalhadas sobre a política de substituição de simulação de phishing única e única.</span><span class="sxs-lookup"><span data-stu-id="518fe-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="518fe-267">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="518fe-268">Usar o PowerShell para exibir regras de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="518fe-269">Este exemplo retorna informações detalhadas sobre regras de substituição de simulação de phishing.</span><span class="sxs-lookup"><span data-stu-id="518fe-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="518fe-270">Embora o comando anterior deva retornar apenas uma regra, todas as regras que estão pendentes de exclusão também podem ser incluídas nos resultados.</span><span class="sxs-lookup"><span data-stu-id="518fe-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="518fe-271">Este exemplo identifica a regra válida (uma) e quaisquer regras inválidas.</span><span class="sxs-lookup"><span data-stu-id="518fe-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="518fe-272">Depois de identificar as regras inválidas, você pode removê-las usando o cmdlet **Remove-PhisSimOverrideRule** conforme descrito posteriormente [neste artigo](#use-powershell-to-remove-phishing-simulation-override-rules).</span><span class="sxs-lookup"><span data-stu-id="518fe-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="518fe-273">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="518fe-274">Usar o PowerShell para modificar a política de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="518fe-275">Para modificar a política de substituição de simulação de phishing, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="518fe-276">Este exemplo desabilita a política de substituição de simulação de phishing.</span><span class="sxs-lookup"><span data-stu-id="518fe-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="518fe-277">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="518fe-278">Usar o PowerShell para modificar uma regra de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="518fe-279">Para modificar a regra de substituição de simulação de phishing, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="518fe-280">Este exemplo modifica a regra de substituição de simulação de phishing especificada com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="518fe-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="518fe-281">Adicione a entrada de domínio blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="518fe-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="518fe-282">Remova a entrada de endereço IP 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="518fe-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="518fe-283">Observe que essas alterações não afetam entradas existentes.</span><span class="sxs-lookup"><span data-stu-id="518fe-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="518fe-284">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="518fe-285">Usar o PowerShell para remover uma política de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="518fe-286">Este exemplo remove a política de substituição de simulação de phishing e a regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="518fe-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="518fe-287">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="518fe-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="518fe-288">Usar o PowerShell para remover regras de substituição de simulação de phishing</span><span class="sxs-lookup"><span data-stu-id="518fe-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="518fe-289">Para remover uma regra de substituição de simulação de phishing, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="518fe-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="518fe-290">Este exemplo remove a regra de substituição de simulação de phishing especificada.</span><span class="sxs-lookup"><span data-stu-id="518fe-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="518fe-291">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="518fe-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
