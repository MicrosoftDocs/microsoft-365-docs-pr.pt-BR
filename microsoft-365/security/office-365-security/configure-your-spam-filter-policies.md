---
title: Configurar políticas de filtro de spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender como criar, modificar e excluir políticas antispam no Exchange Online Protection (EOP).
ms.openlocfilehash: fea1ae4a43ee3002c49bd6511a55a3d490723fc2
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656810"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="c8080-103">Configurar políticas antispam no EOP</span><span class="sxs-lookup"><span data-stu-id="c8080-103">Configure anti-spam policies in EOP</span></span>

<span data-ttu-id="c8080-104">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou um cliente independente do Exchange Online Protection (EOP), ou organizações sem as caixas de correio do Exchange Online, as mensagens de e-mail de entrada serão automaticamente protegidas contra spam por EOP.</span><span class="sxs-lookup"><span data-stu-id="c8080-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="c8080-105">A EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) como parte da defesa geral da sua organização contra spams.</span><span class="sxs-lookup"><span data-stu-id="c8080-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="c8080-106">Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-106">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="c8080-107">Os administradores podem visualizar, editar e configurar (mas não excluir) a política antispam padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="c8080-108">Para maior granularidade, também é possível criar políticas antispam personalizadas aplicadas a determinados usuários, grupos ou domínios na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8080-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="c8080-109">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c8080-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="c8080-110">Você pode configurar políticas anti-spam no Centro de Conformidade e Segurança ou no PowerShell (organizações do Exchange Online PowerShell para Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c8080-110">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="anti-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="c8080-111">Use o Centro de conformidade e segurança para remover políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-111">Anti-spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="c8080-112">Os elementos básicos de uma política antispam na EOP são:</span><span class="sxs-lookup"><span data-stu-id="c8080-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="c8080-113">**A política de filtro de spam**: especifica as ações de vereditos de filtragem de spam e as opções de notificação.</span><span class="sxs-lookup"><span data-stu-id="c8080-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="c8080-114">**A regra de filtro de spam**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="c8080-115">A diferença entre esses dois elementos não é óbvia quando você gerencia as políticas antispam no Centro de Segurança e Conformidade:</span><span class="sxs-lookup"><span data-stu-id="c8080-115">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c8080-116">Quando você cria uma política antispam no Centro de Conformidade e Segurança, você está, na verdade, criando uma regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo, usando o mesmo nome para ambas.</span><span class="sxs-lookup"><span data-stu-id="c8080-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="c8080-117">Quando você modifica uma política antispam no Centro de Conformidade e Segurança, as configurações relacionadas a nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="c8080-118">Todas as demais configurações modificam a política de filtro de spam associada.</span><span class="sxs-lookup"><span data-stu-id="c8080-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="c8080-119">Quando você remove uma política antispam do Centro de Conformidade e Segurança, a regra de filtro de spam e a política de filtro de spam associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="c8080-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="c8080-120">No Exchange Online PowerShell ou no EOP PowerShell autônomo, a diferença entre políticas de filtro de spam e regras de filtro de spam é aparente.</span><span class="sxs-lookup"><span data-stu-id="c8080-120">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="c8080-121">Gerencie políticas de filtro de spam usando os cmdlets **\*-HostedContentFilterPolicy** e gerencie regras de filtro de spam usando os cmdlets **\*-HostedContentFilterRule**.</span><span class="sxs-lookup"><span data-stu-id="c8080-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="c8080-122">No PowerShell, crie primeiro a política de filtro de spam, para depois criar a regra de filtro de spam que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="c8080-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="c8080-123">No PowerShell, modifique as configurações da política de filtro de spam e da regra de filtro de spam separadamente.</span><span class="sxs-lookup"><span data-stu-id="c8080-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="c8080-124">Quando você remove uma política de filtro de spam do PowerShell, a regra de filtro de spam correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="c8080-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="c8080-125">Política antispam padrão</span><span class="sxs-lookup"><span data-stu-id="c8080-125">Default anti-spam policy</span></span>

<span data-ttu-id="c8080-126">Cada organização tem uma política antispam interna denominada Padrão que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="c8080-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="c8080-127">A política de filtro de spam denominada Padrão é aplicada a todos os destinatários da organização, mesmo que não haja uma regra de filtro de spam (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="c8080-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="c8080-128">A política denominada Padrão tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="c8080-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="c8080-129">As políticas personalizadas que você cria têm sempre uma prioridade mais alta do que a política denominada Padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="c8080-130">A política denominada Padrão é a política padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="c8080-131">Para aumentar a eficácia da filtragem de spam, crie políticas antispam personalizadas com configurações mais estritas aplicadas a usuários específicos ou a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="c8080-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c8080-132">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="c8080-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c8080-133">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c8080-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c8080-134">Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="c8080-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="c8080-135">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8080-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c8080-136">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8080-136">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c8080-137">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="c8080-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="c8080-138">Para adicionar, modificar e excluir políticas anti-spam, você precisa ser membro de um dos seguintes grupos de funções:</span><span class="sxs-lookup"><span data-stu-id="c8080-138">To add, modify, and delete anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c8080-139">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c8080-140">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c8080-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="c8080-141">Para acesso somente leitura às políticas anti-spam, você precisa ser membro de um dos seguintes grupos de funções:</span><span class="sxs-lookup"><span data-stu-id="c8080-141">For read-only access to anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c8080-142">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c8080-143">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c8080-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="c8080-144">Para ver as configurações recomendadas para políticas antimalware, confira [Configurações de política antispam da EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="c8080-144">For our recommended settings for anti-malware policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="c8080-145">Usar o Centro de Conformidade e Segurança para criar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-145">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="c8080-146">Criar uma política antispam personalizada no Centro de Conformidade e Segurança gera uma regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo, com o mesmo nome para ambas.</span><span class="sxs-lookup"><span data-stu-id="c8080-146">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="c8080-147">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-148">Na página **Configurações antispam**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="c8080-148">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="c8080-149">No submenu **Nova política de filtro de spam** que é aberto, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-149">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c8080-150">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="c8080-150">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="c8080-151">Não use os seguintes caracteres: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span><span class="sxs-lookup"><span data-stu-id="c8080-151">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="c8080-152">Caso você tenha criado anteriormente alguma política antispam no EAC (Centro de administração do Exchange) que contenha esses caracteres, renomeie a política no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8080-152">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="c8080-153">Para obter instruções, confira a seção [Usar o PowerShell para modificar regras de filtro de spam](#use-powershell-to-modify-spam-filter-rules) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c8080-153">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="c8080-154">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="c8080-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="c8080-155">(Opcional) Expanda a seção **Ações de spam e em massa** e verifique ou defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-155">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="c8080-156">**Selecionar a ação a ser executada para emails de spam e em massa recebidos**: selecione ou revise a ação a ser realizada em relação às mensagens com base nos seguintes vereditos de filtragem de spam:</span><span class="sxs-lookup"><span data-stu-id="c8080-156">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="c8080-157">**Spam**</span><span class="sxs-lookup"><span data-stu-id="c8080-157">**Spam**</span></span>
     - <span data-ttu-id="c8080-158">**Spam de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="c8080-158">**High confidence spam**</span></span>
     - <span data-ttu-id="c8080-159">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="c8080-159">**Phishing email**</span></span>
     - <span data-ttu-id="c8080-160">**Email de phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="c8080-160">**High confidence phishing email**</span></span>
     - <span data-ttu-id="c8080-161">**Email em massa**</span><span class="sxs-lookup"><span data-stu-id="c8080-161">**Bulk email**</span></span>

     <span data-ttu-id="c8080-162">As ações disponíveis para vereditos de filtragem de spam são descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c8080-162">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="c8080-163">Uma marca de seleção (</span><span class="sxs-lookup"><span data-stu-id="c8080-163">A check mark (</span></span> ![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="c8080-165">) indica que a ação está disponível (nem todas as ações estão disponíveis para todos os vereditos de filtragem de spam).</span><span class="sxs-lookup"><span data-stu-id="c8080-165">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="c8080-166">Um asterisco ( <sup>\*</sup> ) após a marca de seleção indica a ação padrão para o veredito de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-166">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     ****

     |<span>|<span data-ttu-id="c8080-167">Spam</span><span class="sxs-lookup"><span data-stu-id="c8080-167">Spam</span></span>|<span data-ttu-id="c8080-168">Alto</span><span class="sxs-lookup"><span data-stu-id="c8080-168">High</span></span><br/><span data-ttu-id="c8080-169">confiança</span><span class="sxs-lookup"><span data-stu-id="c8080-169">confidence</span></span><br/><span data-ttu-id="c8080-170">spam</span><span class="sxs-lookup"><span data-stu-id="c8080-170">spam</span></span>|<span data-ttu-id="c8080-171">Phishing</span><span class="sxs-lookup"><span data-stu-id="c8080-171">Phishing</span></span><br/><span data-ttu-id="c8080-172">email</span><span class="sxs-lookup"><span data-stu-id="c8080-172">email</span></span>|<span data-ttu-id="c8080-173">Alto</span><span class="sxs-lookup"><span data-stu-id="c8080-173">High</span></span><br/><span data-ttu-id="c8080-174">confiança</span><span class="sxs-lookup"><span data-stu-id="c8080-174">confidence</span></span><br/><span data-ttu-id="c8080-175">phishing</span><span class="sxs-lookup"><span data-stu-id="c8080-175">phishing</span></span><br/><span data-ttu-id="c8080-176">email</span><span class="sxs-lookup"><span data-stu-id="c8080-176">email</span></span>|<span data-ttu-id="c8080-177">Em massa</span><span class="sxs-lookup"><span data-stu-id="c8080-177">Bulk</span></span><br/><span data-ttu-id="c8080-178">email</span><span class="sxs-lookup"><span data-stu-id="c8080-178">email</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="c8080-179">**Mover mensagem para a pasta Lixo Eletrônico**: a mensagem é enviada para a caixa de correio e movida para a pasta Lixo Eletrônico.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-179">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="c8080-180">![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-180">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="c8080-181">![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="c8080-184">![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-184">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="c8080-185">**Adicionar cabeçalho X**: adiciona um cabeçalho X ao cabeçalho da mensagem e entrega a mensagem à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c8080-185">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="c8080-186">Digite o nome do campo do cabeçalho X (não o valor) posteriormente na caixa **Adicionar o texto do cabeçalho X**.</span><span class="sxs-lookup"><span data-stu-id="c8080-186">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="c8080-187">Para vereditos de **Spam** e de **Spam de alta confiança**, a mensagem é movida para a pasta Lixo eletrônico.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-187">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="c8080-191">![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-191">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="c8080-192">**Preceder a linha de assunto com texto**: adiciona o texto ao início da linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8080-192">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="c8080-193">A mensagem é enviada para a caixa de correio e movida para a pasta Lixo Eletrônico.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-193">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="c8080-194">Em seguida, insira o texto na caixa **Prefixar a linha de assunto com este texto**.</span><span class="sxs-lookup"><span data-stu-id="c8080-194">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="c8080-199">**Redirecionar mensagem para endereço de email**: envia a mensagem para outros destinatários em vez de enviá-la aos destinatários pretendidos.</span><span class="sxs-lookup"><span data-stu-id="c8080-199">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="c8080-200">Especifique os destinatários posteriormente na caixa **Redirecionar para este endereço de email**.</span><span class="sxs-lookup"><span data-stu-id="c8080-200">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="c8080-206">**Excluir mensagem**: exclui silenciosamente a mensagem inteira, incluindo todos os anexos.</span><span class="sxs-lookup"><span data-stu-id="c8080-206">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="c8080-211">**Mensagem em quarentena**: envia a mensagem para a quarentena em vez de enviá-la aos destinatários pretendidos.</span><span class="sxs-lookup"><span data-stu-id="c8080-211">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="c8080-212">Especifique por quanto tempo a mensagem deve ser mantida na quarentena mais adiante na caixa **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="c8080-212">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="c8080-215">![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8080-215">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="c8080-218">**Nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="c8080-218">**No action**</span></span>|||||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     > <span data-ttu-id="c8080-220"><sup>1</sup> No Exchange Online, a mensagem será movida para a pasta Lixo Eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (ela é habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="c8080-220"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="c8080-221">Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-221">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="c8080-222">Em ambientes da EOP autônoma, em que a EOP protege as caixas de correio locais do Exchange, é preciso configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP, de modo que a regra do lixo eletrônico possa mover as mensagens para a pasta de Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c8080-222">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="c8080-223">Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-223">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
     >
     > <span data-ttu-id="c8080-224"><sup>2</sup> Você pode usar este valor como uma condição nas regras de fluxo de email (também conhecidas como regras de transporte) para filtrar ou rotear a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8080-224"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="c8080-225">**Selecionar o limite**: especifica o BCL (nível de reclamação em massa) de uma mensagem que dispara a ação especificada para o veredito de filtragem de spam de **Email em massa** (maior que o valor especificado, não superior ou igual a ele).</span><span class="sxs-lookup"><span data-stu-id="c8080-225">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="c8080-226">Um valor mais alto indica que a mensagem é menos desejável (é mais provável que a mensagem pareça um spam).</span><span class="sxs-lookup"><span data-stu-id="c8080-226">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="c8080-227">O valor padrão é 7.</span><span class="sxs-lookup"><span data-stu-id="c8080-227">The default value is 7.</span></span> <span data-ttu-id="c8080-228">Para obter mais informações, confira [BCL (Nível de reclamação em massa) no EOP](bulk-complaint-level-values.md) e [Qual é a diferença entre lixo eletrônico e e-mail em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-228">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="c8080-229">Por padrão, a única configuração _MarkAsSpamBulkMail_ do PowerShell é `On` nas políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="c8080-229">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="c8080-230">Essa configuração afeta significativamente os resultados de um veredito de filtragem de **Email em massa**:</span><span class="sxs-lookup"><span data-stu-id="c8080-230">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="c8080-231">**_MarkAsSpamBulkMail_ está Ativada**: um BCL maior do que o limite é convertido para um SCL 6 que corresponde a um veredito de filtragem de **Spam**, e a ação para o veredito de filtragem de **Email em massa** é executada na mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8080-231">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="c8080-232">**_MarkAsSpamBulkMail_ é Desativada**: a mensagem tem o carimbo do BCL, mas _nenhuma ação_ é realizada para o veredito de filtragem de **Email em massa**.</span><span class="sxs-lookup"><span data-stu-id="c8080-232">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="c8080-233">De fato, o limite do BCL e a ação do veredito de filtragem de **Email em massa** são irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="c8080-233">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="c8080-234">**Quarentena**: especifica por quanto tempo manter a mensagem em quarentena se você selecionar **Colocar mensagem em quarentena** como ação para um veredito de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-234">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="c8080-235">Após o período da quarentena, a mensagem será excluída.</span><span class="sxs-lookup"><span data-stu-id="c8080-235">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="c8080-236">O valor padrão é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c8080-236">The default value is 30 days.</span></span> <span data-ttu-id="c8080-237">O valor válido é de 1 a 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c8080-237">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="c8080-238">Para obter informações sobre quarentena, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c8080-238">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="c8080-239">Mensagens em quarentena no EOP</span><span class="sxs-lookup"><span data-stu-id="c8080-239">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="c8080-240">Gerenciar arquivos e mensagens em quarentena como administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="c8080-240">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="c8080-241">Localizar e liberar mensagens em quarentena como usuário no EOP</span><span class="sxs-lookup"><span data-stu-id="c8080-241">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="c8080-242">**Adicionar o texto do cabeçalho X**: esta caixa é obrigatória e só estará disponível se você tiver selecionado **Adicionar cabeçalho X** como a ação para o veredito de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-242">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="c8080-243">O valor especificado é o campo de cabeçalho *nome* adicionado ao cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8080-243">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="c8080-244">O campo de cabeçalho *valor* é sempre `This message appears to be spam`.</span><span class="sxs-lookup"><span data-stu-id="c8080-244">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="c8080-245">O tamanho máximo é de 255 caracteres, e o valor não pode conter espaços ou dois pontos (:).</span><span class="sxs-lookup"><span data-stu-id="c8080-245">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="c8080-246">Por exemplo, se você inserir o valor `X-This-is-my-custom-header`, o cabeçalho X adicionado à mensagem será `X-This-is-my-custom-header: This message appears to be spam.`</span><span class="sxs-lookup"><span data-stu-id="c8080-246">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="c8080-247">Se você inserir um valor contendo espaços ou dois pontos (:), o valor inserido será ignorado, e o cabeçalho X padrão será adicionado à mensagem (`X-This-Is-Spam: This message appears to be spam.`).</span><span class="sxs-lookup"><span data-stu-id="c8080-247">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="c8080-248">**Preceder a linha de assunto com este texto**: esta caixa é obrigatória e só estará disponível se você selecionar **Preceder a linha de assunto com texto** como a ação para um veredito de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-248">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="c8080-249">Digite o texto a ser adicionado ao início da linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8080-249">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="c8080-250">**Redirecionar para este endereço de email**: esta caixa é obrigatória e só estará disponível se você selecionar **Redirecionar mensagem para o endereço de email** como a ação para um veredito de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-250">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="c8080-251">Digite o endereço de email para o qual você deseja enviar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8080-251">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="c8080-252">É possível inserir diversos valores separados por ponto e vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="c8080-252">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="c8080-253">**Dicas de Segurança**: por padrão, as Dicas de Segurança estão habilitadas, mas é possível desabilitá-las desmarcando a caixa de seleção **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="c8080-253">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="c8080-254">Para obter mais informações sobre as Dicas de Segurança, confira [Dicas de segurança em mensagens de e-mail](safety-tips-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-254">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="c8080-255">Configurações de **Limpeza Automática Zero Hora**: a ZAP detecta e realiza ações em mensagens já enviadas a caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8080-255">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="c8080-256">Para obter mais informações sobre a ZAP, confira [Limpeza Automática Zero Hora – proteção contra spam e malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-256">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="c8080-257">**ZAP de spam**: por padrão, a ZAP é habilitada para detecções de spam, mas é possível desabilitá-la desmarcando a caixa de seleção **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="c8080-257">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="c8080-258">**ZAP de phishing**: por padrão, a ZAP é habilitada para detecções de phishing, mas é possível desabilitá-la desmarcando a caixa de seleção **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="c8080-258">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="c8080-259">(Opcional) Expanda a seção **Listas de permissão** para configurar os remetentes de mensagens por endereço ou domínio de email que podem ignorar a filtragem de spam:</span><span class="sxs-lookup"><span data-stu-id="c8080-259">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   >
   > - <span data-ttu-id="c8080-260">Pense bem antes de adicionar domínios aqui.</span><span class="sxs-lookup"><span data-stu-id="c8080-260">Think very carefully before you add domains here.</span></span> <span data-ttu-id="c8080-261">Para mais informações, consulte [Crie listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-261">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > - <span data-ttu-id="c8080-262">Nunca adicione domínios aceitos (domínios que pertencem a você) ou domínios comuns (por exemplo, microsoft.com ou office.com) à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="c8080-262">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="c8080-263">Isso permitirá que invasores enviem emails que ignorem a filtragem de spam da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8080-263">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="c8080-264">**Permitir remetente**: clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-264">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="c8080-265">No submenu **Lista de remetentes permitidos** exibido:</span><span class="sxs-lookup"><span data-stu-id="c8080-265">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="c8080-266">a.</span><span class="sxs-lookup"><span data-stu-id="c8080-266">a.</span></span> <span data-ttu-id="c8080-267">Insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="c8080-267">Enter the sender's email address.</span></span> <span data-ttu-id="c8080-268">Você pode especificar vários endereços de email separados por ponto e vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="c8080-268">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="c8080-269">b.</span><span class="sxs-lookup"><span data-stu-id="c8080-269">b.</span></span> <span data-ttu-id="c8080-270">Click</span><span class="sxs-lookup"><span data-stu-id="c8080-270">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="c8080-272">para adicionar os remetentes.</span><span class="sxs-lookup"><span data-stu-id="c8080-272">to add the senders.</span></span>

      <span data-ttu-id="c8080-273">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="c8080-273">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="c8080-274">Os remetentes que você adicionou aparecem na seção **Remetente Permitido** no submenu.</span><span class="sxs-lookup"><span data-stu-id="c8080-274">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="c8080-275">Para excluir um remetente, clique em ![ícone Remover](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="c8080-275">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="c8080-276">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-276">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="c8080-277">**Permitir domínio**: clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-277">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="c8080-278">No submenu **Lista de domínios permitidos** exibido, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c8080-278">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="c8080-279">a.</span><span class="sxs-lookup"><span data-stu-id="c8080-279">a.</span></span> <span data-ttu-id="c8080-280">Insira o domínio.</span><span class="sxs-lookup"><span data-stu-id="c8080-280">Enter the domain.</span></span> <span data-ttu-id="c8080-281">Vários domínios podem ser especificados, separados por ponto e vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="c8080-281">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="c8080-282">b.</span><span class="sxs-lookup"><span data-stu-id="c8080-282">b.</span></span> <span data-ttu-id="c8080-283">Click</span><span class="sxs-lookup"><span data-stu-id="c8080-283">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="c8080-285">para adicionar os domínios.</span><span class="sxs-lookup"><span data-stu-id="c8080-285">to add the domains.</span></span>

      <span data-ttu-id="c8080-286">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="c8080-286">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="c8080-287">Os domínios que você adicionou aparecem na seção **Domínio Permitido** no submenu.</span><span class="sxs-lookup"><span data-stu-id="c8080-287">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="c8080-288">Para excluir um domínio, clique em ![ícone Remover](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="c8080-288">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="c8080-289">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-289">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="c8080-290">(Opcional) Expanda a seção **Listas de bloqueios** para configurar os remetentes de mensagens por endereço ou domínio de email que sempre serão marcados como spam de alta confidencialidade:</span><span class="sxs-lookup"><span data-stu-id="c8080-290">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="c8080-291">Bloquear manualmente os domínios não é perigoso, mas pode aumentar sua carga de trabalho administrativa.</span><span class="sxs-lookup"><span data-stu-id="c8080-291">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="c8080-292">Para obter mais informações, confira [Criar listas de bloqueios de remetentes no EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-292">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="c8080-293">**Bloquear remetente**: clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-293">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="c8080-294">No submenu **Lista de remetentes bloqueados** exibido, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c8080-294">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="c8080-295">a.</span><span class="sxs-lookup"><span data-stu-id="c8080-295">a.</span></span> <span data-ttu-id="c8080-296">Insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="c8080-296">Enter the sender's email address.</span></span> <span data-ttu-id="c8080-297">Você pode especificar vários endereços de email separados por ponto e vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="c8080-297">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="c8080-298">Curingas (\*) não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c8080-298">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="c8080-299">b.</span><span class="sxs-lookup"><span data-stu-id="c8080-299">b.</span></span> <span data-ttu-id="c8080-300">Click</span><span class="sxs-lookup"><span data-stu-id="c8080-300">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="c8080-302">para adicionar os remetentes.</span><span class="sxs-lookup"><span data-stu-id="c8080-302">to add the senders.</span></span>

      <span data-ttu-id="c8080-303">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="c8080-303">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="c8080-304">Os remetentes que você adicionou aparecem na seção **Remetente bloqueado** no submenu.</span><span class="sxs-lookup"><span data-stu-id="c8080-304">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="c8080-305">Para excluir um remetente, clique em ![botão Remover](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="c8080-305">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="c8080-306">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-306">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="c8080-307">**Bloquear domínio**: clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-307">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="c8080-308">No submenu **Lista de domínios bloqueados** exibido:</span><span class="sxs-lookup"><span data-stu-id="c8080-308">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="c8080-309">a.</span><span class="sxs-lookup"><span data-stu-id="c8080-309">a.</span></span> <span data-ttu-id="c8080-310">Insira o domínio.</span><span class="sxs-lookup"><span data-stu-id="c8080-310">Enter the domain.</span></span> <span data-ttu-id="c8080-311">Vários domínios podem ser especificados, separados por ponto e vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="c8080-311">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="c8080-312">Curingas (\*) não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c8080-312">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="c8080-313">b.</span><span class="sxs-lookup"><span data-stu-id="c8080-313">b.</span></span> <span data-ttu-id="c8080-314">Click</span><span class="sxs-lookup"><span data-stu-id="c8080-314">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="c8080-316">para adicionar os domínios.</span><span class="sxs-lookup"><span data-stu-id="c8080-316">to add the domains.</span></span>

      <span data-ttu-id="c8080-317">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="c8080-317">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="c8080-318">Os domínios que você adicionou aparecem na lista **Domínio Bloqueado** no submenu.</span><span class="sxs-lookup"><span data-stu-id="c8080-318">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="c8080-319">Para excluir um domínio, clique em ![botão Remover](../../media/scc-remove-icon.png).</span><span class="sxs-lookup"><span data-stu-id="c8080-319">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="c8080-320">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-320">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="c8080-321">(Opcional) Expanda a seção **Spam internacional** para configurar os países de origem ou idiomas de email bloqueados pela filtragem de spam:</span><span class="sxs-lookup"><span data-stu-id="c8080-321">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="c8080-322">**Filtrar mensagens de email escritas nos seguintes idiomas**: esta configuração é exibida por padrão (**Status: DESATIVADO**).</span><span class="sxs-lookup"><span data-stu-id="c8080-322">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="c8080-323">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-323">Click **Edit**.</span></span> <span data-ttu-id="c8080-324">No submenu **Configurações de spam internacionais** exibido, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-324">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="c8080-325">**Filtrar mensagens de email escritas nos seguintes idiomas**: marque a caixa de seleção para habilitar esta configuração.</span><span class="sxs-lookup"><span data-stu-id="c8080-325">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="c8080-326">Desmarque a caixa de seleção para desabilitar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c8080-326">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="c8080-327">Clique na caixa e comece a digitar o *nome* do idioma.</span><span class="sxs-lookup"><span data-stu-id="c8080-327">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="c8080-328">Uma lista filtrada de idiomas com suporte será exibida, juntamente com o código ISO 639-2 de duas letras do idioma correspondente.</span><span class="sxs-lookup"><span data-stu-id="c8080-328">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="c8080-329">Quando encontrar o idioma que está procurando, selecione-o.</span><span class="sxs-lookup"><span data-stu-id="c8080-329">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="c8080-330">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="c8080-330">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="c8080-331">A lista de idiomas selecionados aparecerá no submenu.</span><span class="sxs-lookup"><span data-stu-id="c8080-331">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="c8080-332">Para excluir um idioma, clique em</span><span class="sxs-lookup"><span data-stu-id="c8080-332">To delete a language, click</span></span> ![Botão Remover](../../media/scc-remove-icon.png)<span data-ttu-id="c8080-334">.</span><span class="sxs-lookup"><span data-stu-id="c8080-334">.</span></span>

     <span data-ttu-id="c8080-335">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-335">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="c8080-336">**Filtrar mensagens de email enviadas dos seguintes países ou regiões**: esta configuração é exibida por padrão (**Status: DESATIVADO**).</span><span class="sxs-lookup"><span data-stu-id="c8080-336">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="c8080-337">Para habilitar, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-337">To enable it, click **Edit**.</span></span> <span data-ttu-id="c8080-338">No submenu **Configurações de spam internacionais** exibido, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-338">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="c8080-339">**Filtrar mensagens de email enviadas dos seguintes países ou regiões**: marque a caixa de seleção para habilitar esta configuração.</span><span class="sxs-lookup"><span data-stu-id="c8080-339">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="c8080-340">Desmarque a caixa de seleção para desabilitar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c8080-340">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="c8080-341">Clique na caixa e comece a digitar o *nome* do país ou região.</span><span class="sxs-lookup"><span data-stu-id="c8080-341">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="c8080-342">Uma lista filtrada de países com suporte será exibida, juntamente com o código ISO 3166-1 de duas letras do país correspondente.</span><span class="sxs-lookup"><span data-stu-id="c8080-342">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="c8080-343">Quando encontrar o país ou região que está procurando, selecione-o.</span><span class="sxs-lookup"><span data-stu-id="c8080-343">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="c8080-344">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="c8080-344">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="c8080-345">A lista de países selecionados aparecerá no submenu.</span><span class="sxs-lookup"><span data-stu-id="c8080-345">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="c8080-346">Para excluir um país ou região, clique em</span><span class="sxs-lookup"><span data-stu-id="c8080-346">To delete a country or region, click</span></span> ![Botão Remover](../../media/scc-remove-icon.png)<span data-ttu-id="c8080-348">.</span><span class="sxs-lookup"><span data-stu-id="c8080-348">.</span></span>

     <span data-ttu-id="c8080-349">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-349">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="c8080-350">A seção opcional **Propriedades de spam** contém configurações de ASF (filtragem de spam avançada) que estão desativadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-350">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="c8080-351">As configurações de ASF estão em processo de substituição, e a funcionalidade delas está sendo incorporada a outras partes da pilha de filtragem.</span><span class="sxs-lookup"><span data-stu-id="c8080-351">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="c8080-352">Recomendamos deixar todas essas configurações de ASF desativadas em suas políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="c8080-352">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="c8080-353">Para obter mais detalhes sobre essas configurações, confira [Configurações de filtragem de spam avançadas no EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-353">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="c8080-354">(Obrigatório) Expanda a seção **Aplicada a** para identificar os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="c8080-354">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="c8080-355">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="c8080-355">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c8080-356">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="c8080-356">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="c8080-357">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="c8080-357">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="c8080-358">O mais fácil é clicar em **Adicionar uma condição** três vezes para ver todas as condições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c8080-358">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="c8080-359">Clique em ![botão Remover](../../media/scc-remove-icon.png) para remover condições que você não queira configurar.</span><span class="sxs-lookup"><span data-stu-id="c8080-359">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="c8080-360">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="c8080-360">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="c8080-361">Clique na caixa **Adicionar uma marca** para ver e selecionar um domínio.</span><span class="sxs-lookup"><span data-stu-id="c8080-361">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="c8080-362">Clique novamente na caixa **Adicionar uma marca** para selecionar domínios adicionais se mais de um domínio estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="c8080-362">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="c8080-363">**O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8080-363">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="c8080-364">Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="c8080-364">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="c8080-365">Clique novamente na caixa **Adicionar uma marca** para selecionar destinatários adicionais.</span><span class="sxs-lookup"><span data-stu-id="c8080-365">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="c8080-366">**O destinatário é um membro de**: especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8080-366">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="c8080-367">Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="c8080-367">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="c8080-368">Clique novamente na caixa **Adicionar uma marca** para selecionar destinatários adicionais.</span><span class="sxs-lookup"><span data-stu-id="c8080-368">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="c8080-369">**Exceto se**: para adicionar exceções à regra, clique em **Adicionar uma condição** três vezes para ver todas as exceções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c8080-369">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="c8080-370">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="c8080-370">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="c8080-371">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-371">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="c8080-372">Usar o Centro de Conformidade e Segurança para visualizar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-372">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="c8080-373">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-373">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-374">Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política antispam:</span><span class="sxs-lookup"><span data-stu-id="c8080-374">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="c8080-375">A política padrão chamada **Política de filtro de spam padrão**.</span><span class="sxs-lookup"><span data-stu-id="c8080-375">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="c8080-376">Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.</span><span class="sxs-lookup"><span data-stu-id="c8080-376">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="c8080-377">As configurações de política importantes são exibidas nos detalhes de política expandida que são exibidos.</span><span class="sxs-lookup"><span data-stu-id="c8080-377">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="c8080-378">Para ver mais detalhes, clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="c8080-378">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="c8080-379">Usar o Centro de Conformidade e Segurança para modificar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-379">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="c8080-380">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-380">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-381">Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política antispam:</span><span class="sxs-lookup"><span data-stu-id="c8080-381">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="c8080-382">A política padrão chamada **Política de filtro de spam padrão**.</span><span class="sxs-lookup"><span data-stu-id="c8080-382">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="c8080-383">Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.</span><span class="sxs-lookup"><span data-stu-id="c8080-383">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="c8080-384">Clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="c8080-384">Click **Edit policy**.</span></span>

<span data-ttu-id="c8080-385">Para políticas antispam, as configurações disponíveis no submenu exibido são idênticas às descritas na seção [Usar o Centro de Conformidade e Segurança para criar políticas antispam](#use-the-security--compliance-center-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="c8080-385">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="c8080-386">Para a política antispam padrão chamada **Política de filtragem de spam padrão**, a seção **Aplicada a** não está disponível (a política se aplica a todos), e não é possível renomear a política.</span><span class="sxs-lookup"><span data-stu-id="c8080-386">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="c8080-387">Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c8080-387">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="c8080-388">Habilitar ou desabilitar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-388">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="c8080-389">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-389">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-390">Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política personalizada que você criou (o valor na coluna **Tipo** é **Política antispam personalizada**).</span><span class="sxs-lookup"><span data-stu-id="c8080-390">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="c8080-391">Nos detalhes exibidos da política expandida, observe o valor na coluna **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="c8080-391">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="c8080-392">Mova o botão de alternância para a esquerda para desabilitar a política:</span><span class="sxs-lookup"><span data-stu-id="c8080-392">Move the toggle to the left to disable the policy:</span></span> ![Desativar](../../media/scc-toggle-off.png)

   <span data-ttu-id="c8080-394">Mova o botão de alternância para a direita para habilitar a política:</span><span class="sxs-lookup"><span data-stu-id="c8080-394">Move the toggle to the right to enable the policy:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="c8080-396">Não é possível desabilitar a política antispam padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-396">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="c8080-397">Definir a prioridade das políticas antispam personalizadas</span><span class="sxs-lookup"><span data-stu-id="c8080-397">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="c8080-398">Por padrão, as políticas antispam recebem uma prioridade com base na ordem em que foram criadas (políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="c8080-398">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="c8080-399">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="c8080-399">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c8080-400">Duas políticas não podem ter a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="c8080-400">No two policies can have the same priority.</span></span>

<span data-ttu-id="c8080-401">As políticas antispam personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **Prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="c8080-401">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="c8080-402">A política antispam padrão chamada **Política de filtro de spam padrão** tem o valor de prioridade **Menor**, e isso não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="c8080-402">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="c8080-403">**Observação**: no Centro de Conformidade e Segurança, só é possível alterar a política antispam depois de criá-la.</span><span class="sxs-lookup"><span data-stu-id="c8080-403">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="c8080-404">No PowerShell, é possível substituir a prioridade padrão ao criar a regra de filtro de spam (o que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="c8080-404">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="c8080-405">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="c8080-405">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="c8080-406">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-406">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-407">Na página **Configurações antispam**, encontre as políticas em que o valor na coluna **Tipo** é **Política antispam personalizada**.</span><span class="sxs-lookup"><span data-stu-id="c8080-407">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="c8080-408">Observe os valores na coluna **Prioridade**:</span><span class="sxs-lookup"><span data-stu-id="c8080-408">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="c8080-409">A política antispam personalizada com maior prioridade tem o valor ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="c8080-409">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="c8080-410">A política antispam personalizada com menor prioridade tem o valor ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por exemplo, ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="c8080-410">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="c8080-411">Se você tem três ou mais políticas antispam personalizadas, as políticas entre a maior e menor prioridade têm valores ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png)![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por exemplo, ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png)![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="c8080-411">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="c8080-412">Clique em</span><span class="sxs-lookup"><span data-stu-id="c8080-412">Click</span></span> ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="c8080-414">ou</span><span class="sxs-lookup"><span data-stu-id="c8080-414">or</span></span> ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="c8080-416">para mover a política antispam personalizada na lista de prioridade.</span><span class="sxs-lookup"><span data-stu-id="c8080-416">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="c8080-417">Configurar as notificações de spam para usuário final</span><span class="sxs-lookup"><span data-stu-id="c8080-417">Configure end-user spam notifications</span></span>

<span data-ttu-id="c8080-418">Quando um veredito de filtragem de spam coloca uma mensagem em quarentena, é possível configurar as notificações de spam para usuário final de modo que os destinatários saibam o que houve com as mensagens que foram enviadas para eles.</span><span class="sxs-lookup"><span data-stu-id="c8080-418">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="c8080-419">Para obter mais informações sobre essas notificações, confira [Notificações de spam para usuário final no EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c8080-419">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="c8080-420">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-420">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-421">Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política antispam:</span><span class="sxs-lookup"><span data-stu-id="c8080-421">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="c8080-422">A política padrão chamada **Política de filtro de spam padrão**.</span><span class="sxs-lookup"><span data-stu-id="c8080-422">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="c8080-423">Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.</span><span class="sxs-lookup"><span data-stu-id="c8080-423">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="c8080-424">Nos detalhes da política expandida, clique em **Configurar as notificações de spam para usuário final**.</span><span class="sxs-lookup"><span data-stu-id="c8080-424">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="c8080-425">Na caixa de diálogo **\<Policy Name\>** que se abre, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-425">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c8080-426">**Habilitar as notificações de spam para usuário final**: selecione a caixa de seleção para habilitar as notificações.</span><span class="sxs-lookup"><span data-stu-id="c8080-426">**Enable end-user spam notifications**: Select the checkbox to enable notifications.</span></span> <span data-ttu-id="c8080-427">Desmarque a caixa de seleção para desabilitar as notificações.</span><span class="sxs-lookup"><span data-stu-id="c8080-427">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="c8080-428">**Enviar notificações de spam para usuário final a cada (dias)**: selecione a frequência de envio das notificações.</span><span class="sxs-lookup"><span data-stu-id="c8080-428">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="c8080-429">O valor padrão é de 3 dias.</span><span class="sxs-lookup"><span data-stu-id="c8080-429">The default value is 3 days.</span></span> <span data-ttu-id="c8080-430">Você pode inserir de 1 a 15 dias.</span><span class="sxs-lookup"><span data-stu-id="c8080-430">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="c8080-431">Há três ciclos de notificação de spam para o usuário final dentro de um período de 24 horas que se iniciam nos seguintes horários: 01:00 UTC, 08:00 UTC e 16:00 UTC.</span><span class="sxs-lookup"><span data-stu-id="c8080-431">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c8080-432">Se perdermos uma notificação durante um ciclo anterior, um ciclo subsequente gerará a notificação.</span><span class="sxs-lookup"><span data-stu-id="c8080-432">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="c8080-433">Isso pode dar a impressão da ocorrência de várias notificações dentro do mesmo dia.</span><span class="sxs-lookup"><span data-stu-id="c8080-433">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="c8080-434">**Idioma da notificação**: clique no menu suspenso selecionar um idioma disponível na lista.</span><span class="sxs-lookup"><span data-stu-id="c8080-434">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="c8080-435">O valor padrão é **Padrão**, o que significa inglês.</span><span class="sxs-lookup"><span data-stu-id="c8080-435">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="c8080-436">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8080-436">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="c8080-437">Usar o Centro de Conformidade e Segurança para remover políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-437">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="c8080-438">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="c8080-438">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c8080-439">Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir a política personalizada que você deseja excluir (a coluna **Tipo** é **Política antispam personalizada**).</span><span class="sxs-lookup"><span data-stu-id="c8080-439">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="c8080-440">Nas informações da política expandida, clique em **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="c8080-440">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="c8080-441">Clique em **Sim** na caixa de diálogo exibida.</span><span class="sxs-lookup"><span data-stu-id="c8080-441">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="c8080-442">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-442">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="c8080-443">Use o Exchange Online PowerShell ou EOP PowerShell autônomo para configurar políticas anti-spam</span><span class="sxs-lookup"><span data-stu-id="c8080-443">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="c8080-444">As seguintes configurações de política antispam só estão disponíveis no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8080-444">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="c8080-445">O parâmetro _MarkAsSpamBulkMail_ que é `On` por padrão.</span><span class="sxs-lookup"><span data-stu-id="c8080-445">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="c8080-446">Os efeitos dessa configuração foram explicados anteriormente na seção [Usar o Centro de Conformidade e Segurança para criar políticas antispam](#use-the-security--compliance-center-to-create-anti-spam-policies) deste tópico.</span><span class="sxs-lookup"><span data-stu-id="c8080-446">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="c8080-447">As seguintes configurações de notificações da quarentena de spam para usuário final:</span><span class="sxs-lookup"><span data-stu-id="c8080-447">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="c8080-448">O parâmetro _DownloadLink_, que mostra ou oculta o link para a Ferramenta de Relatórios de Lixo Eletrônico para Outlook.</span><span class="sxs-lookup"><span data-stu-id="c8080-448">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="c8080-449">O parâmetro _EndUserSpamNotificationCustomSubject_, que você pode usar para personalizar a linha de assunto da notificação.</span><span class="sxs-lookup"><span data-stu-id="c8080-449">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="c8080-450">Usar o PowerShell para criar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c8080-450">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="c8080-451">A criação de uma política antispam no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="c8080-451">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c8080-452">Crie a política de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-452">Create the spam filter policy.</span></span>

2. <span data-ttu-id="c8080-453">Crie a regra de filtro de spam que especifica a política de filtro de spam à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="c8080-453">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="c8080-454">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c8080-454">**Notes**:</span></span>

- <span data-ttu-id="c8080-455">você pode criar uma nova regra de filtro de spam e atribuir uma política de filtro de spam existente e não associada a ela.</span><span class="sxs-lookup"><span data-stu-id="c8080-455">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="c8080-456">Não é possível associar uma regra de filtro de spam a mais de uma política de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-456">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="c8080-457">Você pode definir as seguintes configurações em novas políticas de filtro de spam no PowerShell que não estarão disponíveis no Centro de Conformidade e Segurança até que você crie a política:</span><span class="sxs-lookup"><span data-stu-id="c8080-457">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="c8080-458">Crie a nova política como desabilitada (_Habilitada_ `$false` no cmdlet **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="c8080-458">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="c8080-459">Defina a prioridade da política durante a criação (_Prioridade__\<Number\>_) no cmdlet **New-HostedContentFilterRule**).</span><span class="sxs-lookup"><span data-stu-id="c8080-459">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="c8080-460">Uma nova política de filtro de spam criada no PowerShell não ficará visível no Centro de Conformidade e Segurança até você atribua a política a uma regra de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-460">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="c8080-461">Etapa 1: usar o PowerShell para criar uma política de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-461">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="c8080-462">Para criar uma política de filtro de spam, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-462">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="c8080-463">Esse exemplo cria uma política de filtro de spam chamada Contoso Executives com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-463">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="c8080-464">Colocar mensagens em quarentena quando o veredicto de filtragem de spam for spam ou spam de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="c8080-464">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="c8080-465">O BCL 6 dispara a ação para um veredito de filtragem de spam de email em massa.</span><span class="sxs-lookup"><span data-stu-id="c8080-465">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="c8080-466">**New-HostedContentFilterPolicy** e **Set-HostedContentFilterPolicy** contêm um parâmetro _ZapEnabled_ mais antigo, bem como parâmetros _PhishZapEnabled_ e _SpamZapEnabled_ mais novos.</span><span class="sxs-lookup"><span data-stu-id="c8080-466">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="c8080-467">O parâmetro _ZapEnabled_ foi depreciado em fevereiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="c8080-467">The _ZapEnabled_ parameter was deprecated in February 2020.</span></span> <span data-ttu-id="c8080-468">Os parâmetros _PhishZapEnabled_ e _SpamZapEnabled_ herdavam os valores deles do parâmetro _ZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="c8080-468">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="c8080-469">No entanto, se você usar os parâmetros _PhishZapEnabled_ e _SpamZapEnabled_ em um comando ou usar as configurações de **ZAP de spam** ou **ZAP de phishing** na política no Centro de Conformidade e Segurança, o valor do parâmetro _ZapEnabled_ será ignorado.</span><span class="sxs-lookup"><span data-stu-id="c8080-469">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="c8080-470">Em outras palavras, não use o parâmetro _ZapEnabled_; em vez disso, use os parâmetros _PhishZapEnabled_ e _SpamZapEnabled_.</span><span class="sxs-lookup"><span data-stu-id="c8080-470">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="c8080-471">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8080-471">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="c8080-472">Etapa 2: usar o PowerShell para criar uma regra de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-472">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="c8080-473">Para criar uma regra de filtro de spam, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-473">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="c8080-474">Esse exemplo cria uma nova regra de filtro de spam chamada Contoso Executives com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8080-474">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="c8080-475">A política de filtro de spam chamada Contoso Executives é associada à regra.</span><span class="sxs-lookup"><span data-stu-id="c8080-475">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="c8080-476">A regra se aplica aos membros do grupo chamado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="c8080-476">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="c8080-477">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="c8080-477">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="c8080-478">Usar o PowerShell para visualizar políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-478">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="c8080-479">Para retornar uma lista de resumo de todas as políticas de filtro de spam, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="c8080-479">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="c8080-480">Para retornar informações detalhadas sobre uma política de filtro de spam específica, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-480">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="c8080-481">Este exemplo retorna todos os valores de propriedade da política de filtro de spam chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="c8080-481">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="c8080-482">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8080-482">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="c8080-483">Usar o PowerShell para visualizar regras de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-483">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="c8080-484">Para visualizar regras de filtro de spam existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-484">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="c8080-485">Para retornar uma lista de resumo de todas as regras de filtro de spam, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="c8080-485">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="c8080-486">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="c8080-486">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="c8080-487">Para retornar informações detalhadas sobre uma regra de filtro de spam específica, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-487">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="c8080-488">Este exemplo retorna todos os valores de propriedade da regra de filtro de spam chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="c8080-488">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="c8080-489">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="c8080-489">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="c8080-490">Usar o PowerShell para modificar políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-490">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="c8080-491">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política de filtro de malware no PowerShell, como ao criar a política conforme descrito anteriormente na seção [Etapa 1: usar o PowerShell para criar uma política de filtro de spam](#step-1-use-powershell-to-create-a-spam-filter-policy) deste tópico.</span><span class="sxs-lookup"><span data-stu-id="c8080-491">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="c8080-492">A opção _MakeDefault_ que transforma a política especificada em política padrão (aplicada a todos, sempre com a **Menor** prioridade, e que pode ser excluída) só está disponível quando você modifica uma política de filtro de spam no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8080-492">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="c8080-493">Não é possível renomear uma política de filtro de spam (o cmdlet **Set-HostedContentFilterPolicy** não tem o parâmetro _Name_).</span><span class="sxs-lookup"><span data-stu-id="c8080-493">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c8080-494">Quando você renomeia uma política antispam no Centro de Conformidade e Segurança, só é possível renomear a _regra_ do filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c8080-494">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="c8080-495">Para modificar uma política de filtro de spam, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-495">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c8080-496">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8080-496">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="c8080-497">Usar o PowerShell para modificar regras de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-497">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="c8080-498">A única configuração que não está disponível quando você modifica uma regra de filtro de spam no PowerShell é o parâmetro _Enabled_, que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c8080-498">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c8080-499">Para habilitar ou desabilitar regras de filtro de spam existentes, confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="c8080-499">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="c8080-500">Do contrário, nenhuma configuração adicional estará disponível quando você modificar a regra de filtro de spam no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8080-500">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="c8080-501">As mesmas configurações estão disponíveis quando você cria uma regra conforme descrito anteriormente na seção [Etapa 2: usar o PowerShell para criar uma regra de filtro de spam](#step-2-use-powershell-to-create-a-spam-filter-rule) deste tópico.</span><span class="sxs-lookup"><span data-stu-id="c8080-501">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="c8080-502">Para modificar uma regra de filtro de spam, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-502">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c8080-503">Este exemplo renomeia a regra de filtro de spam chamada `{Fabrikam Spam Filter}` que pode causar problemas no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="c8080-503">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="c8080-504">Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="c8080-504">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="c8080-505">Usar o PowerShell para habilitar ou desabilitar regras de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-505">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="c8080-506">Habilitar ou desabilitar uma regra de filtro de spam no PowerShell habilita ou desabilita toda a política antispam (a regra de filtro de spam e a política de filtro de spam atribuída).</span><span class="sxs-lookup"><span data-stu-id="c8080-506">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="c8080-507">Não é possível habilitar ou desabilitar a política antispam padrão (ela é sempre aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="c8080-507">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="c8080-508">Para habilitar ou desabilitar uma regra de filtro de spam no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-508">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="c8080-509">Este exemplo desabilita a regra de filtro de spam chamada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="c8080-509">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="c8080-510">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="c8080-510">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="c8080-511">Para obter informações detalhadas de sintaxe e parâmetro, confira [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) e [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="c8080-511">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="c8080-512">Usar o PowerShell para definir a prioridade das regras de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-512">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="c8080-513">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="c8080-513">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c8080-514">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="c8080-514">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c8080-515">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="c8080-515">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c8080-516">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="c8080-516">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c8080-517">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="c8080-517">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c8080-518">Para definir a prioridade de uma regra de filtro de spam no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-518">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c8080-519">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="c8080-519">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="c8080-520">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="c8080-520">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="c8080-521">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c8080-521">**Notes**:</span></span>

- <span data-ttu-id="c8080-522">para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Prioridade_ no cmdlet **New-HostedContentFilterRule**.</span><span class="sxs-lookup"><span data-stu-id="c8080-522">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="c8080-523">A política de filtro de spam padrão não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade inalterável **Menor**.</span><span class="sxs-lookup"><span data-stu-id="c8080-523">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="c8080-524">Usar o PowerShell para remover políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-524">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="c8080-525">Quando você usa o PowerShell para remover uma política de filtro de spam, a regra de filtro de spam correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="c8080-525">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="c8080-526">Para remover uma política de filtro de spam no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-526">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c8080-527">Este exemplo remove a política de filtro de spam chamada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="c8080-527">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c8080-528">Para obter informações detalhadas de sintaxe e parâmetro, confira [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8080-528">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="c8080-529">Usar o PowerShell para remover regras de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-529">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="c8080-530">Quando você usa o PowerShell para remover uma regra de filtro de spam, a política de filtro de spam correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="c8080-530">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="c8080-531">Para remover uma regra de filtro de spam no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c8080-531">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="c8080-532">Este exemplo remove a regra de filtro de spam chamada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="c8080-532">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="c8080-533">Para obter informações detalhadas de sintaxe e parâmetro, confira [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span><span class="sxs-lookup"><span data-stu-id="c8080-533">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c8080-534">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="c8080-534">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="c8080-535">Enviar uma mensagem do GTUBE para testar as configurações de política de spam</span><span class="sxs-lookup"><span data-stu-id="c8080-535">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="c8080-536">Essas etapas só funcionarão se a organização de email da qual você está enviando a mensagem do GTUBE não tiver verificação de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="c8080-536">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="c8080-537">Se ela tiver, a mensagem de teste não poderá ser enviada.</span><span class="sxs-lookup"><span data-stu-id="c8080-537">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="c8080-538">O GTUBE (teste genérico para email em massa não solicitado) é uma cadeia de caracteres de texto incluída em uma mensagem de texto para verificar as configurações antispam da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8080-538">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="c8080-539">A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.</span><span class="sxs-lookup"><span data-stu-id="c8080-539">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="c8080-540">Inclua o seguinte texto do GTUBE em uma mensagem de email em uma única linha, sem espaços ou quebras de linha:</span><span class="sxs-lookup"><span data-stu-id="c8080-540">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="c8080-541">Listas de permissões/bloqueios</span><span class="sxs-lookup"><span data-stu-id="c8080-541">Allow/Block Lists</span></span>

<span data-ttu-id="c8080-542">De vez em quando, os filtros perdem a mensagem ou nossos sistemas demoram algum tempo para se ajustar.</span><span class="sxs-lookup"><span data-stu-id="c8080-542">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="c8080-543">Nesse caso, a política antispam tem uma lista de permissões e outra de bloqueios, disponíveis para substituir o veredicto atual.</span><span class="sxs-lookup"><span data-stu-id="c8080-543">In this cases, the anti-spam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="c8080-544">Essa opção deve ser usada com moderação, pois as listas podem se tornar temporariamente não gerenciáveis porque a pilha de filtragem deverá executar o que precisa ser feito.</span><span class="sxs-lookup"><span data-stu-id="c8080-544">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="c8080-545">Podem haver situações nas quais a sua organização pode não concordar com o veredicto fornecido pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="c8080-545">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="c8080-546">Nesse caso, talvez você queira manter a Lista de permissões ou bloqueio permanente.</span><span class="sxs-lookup"><span data-stu-id="c8080-546">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="c8080-547">No entanto, se você pretende colocar um domínio na Lista de permissões por longos períodos de tempo, deve informar ao remetente para verificar se o domínio está autenticado e configurar o DMARC para rejeitá-lo, caso não esteja.</span><span class="sxs-lookup"><span data-stu-id="c8080-547">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
