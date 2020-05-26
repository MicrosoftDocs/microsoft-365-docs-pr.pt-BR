---
title: Configurar a filtragem de spam de saída
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de spam de saída na proteção do Exchange Online (EOP).
ms.openlocfilehash: e035fe26cea0fcd1f3051f7464722ae1c7a3b56f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351994"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="fed83-103">Configurar a filtragem de spam de saída no EOP</span><span class="sxs-lookup"><span data-stu-id="fed83-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="fed83-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, mensagens de email de saída enviadas por meio do EOP são verificadas automaticamente quanto ao spam e à atividade de envio incomum.</span><span class="sxs-lookup"><span data-stu-id="fed83-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="fed83-105">O spam de saída de um usuário em sua organização normalmente indica uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="fed83-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="fed83-106">Mensagens de saída suspeitas são marcadas como spam (independentemente do nível de confiança de spam ou SCL) e são roteadas através do [pool de entrega de alto risco](high-risk-delivery-pool-for-outbound-messages.md) para ajudar a proteger a reputação do serviço (ou seja, manter os servidores de email de origem do Microsoft 365 fora das listas de bloqueios de IP).</span><span class="sxs-lookup"><span data-stu-id="fed83-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="fed83-107">Os administradores são notificados automaticamente sobre atividade de email de saída suspeita e usuários bloqueados por meio de [políticas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fed83-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="fed83-108">O EOP usa políticas de spam de saída como parte da defesa geral da sua organização contra spam.</span><span class="sxs-lookup"><span data-stu-id="fed83-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="fed83-109">Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fed83-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="fed83-110">Os administradores podem exibir, editar e configurar (mas não excluir) a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="fed83-111">Para maior granularidade, você também pode criar políticas personalizadas de spam de saída que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fed83-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="fed83-112">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fed83-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="fed83-113">Você pode configurar políticas de spam de saída no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="fed83-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="fed83-114">Políticas de spam de saída no centro de conformidade e segurança & vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="fed83-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="fed83-115">Os elementos básicos de uma política de spam de saída no EOP são:</span><span class="sxs-lookup"><span data-stu-id="fed83-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="fed83-116">**A política de filtro de spam de saída**: especifica as ações para verdicts de filtragem de spam de saída e as opções de notificação.</span><span class="sxs-lookup"><span data-stu-id="fed83-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="fed83-117">**A regra de filtro de spam de saída**: especifica a prioridade e os filtros de destinatário (aos quais a política se aplica) para uma política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="fed83-118">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de spam de saída no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="fed83-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fed83-119">Ao criar uma política de spam de saída no centro de conformidade de & de segurança, você está realmente criando uma regra de filtro de spam de saída e a política de filtro de spam de saída associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="fed83-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="fed83-120">Quando você modifica uma política de spam de saída no centro de conformidade de & de segurança, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="fed83-121">Todas as outras configurações modificam a política de filtro de spam de saída associada.</span><span class="sxs-lookup"><span data-stu-id="fed83-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="fed83-122">Quando você remove uma política de spam de saída do centro de conformidade & segurança, a regra de filtro de spam de saída e a política de filtro de spam de saída associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="fed83-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="fed83-123">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a diferença entre políticas de filtro de spam de saída e regras de filtro de spam de saída é aparente.</span><span class="sxs-lookup"><span data-stu-id="fed83-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="fed83-124">Você gerencia as políticas de filtro de spam de saída usando os cmdlets \*\* \* -HostedOutboundSpamFilterPolicy\*\* e gerencia as regras de filtro de spam de saída usando os cmdlets \*\* \* -HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="fed83-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="fed83-125">No PowerShell, você cria primeiro a política de filtro de spam de saída e, em seguida, cria a regra de filtro de spam de saída que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="fed83-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="fed83-126">No PowerShell, você modifica as configurações da política de filtro de spam de saída e a regra de filtro de spam de saída separadamente.</span><span class="sxs-lookup"><span data-stu-id="fed83-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="fed83-127">Quando você remove uma política de filtro de spam de saída do PowerShell, a regra de filtro de spam de saída correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="fed83-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="fed83-128">Política de spam de saída padrão</span><span class="sxs-lookup"><span data-stu-id="fed83-128">Default outbound spam policy</span></span>

<span data-ttu-id="fed83-129">Todas as organizações têm uma política interna de spam de saída chamada Default que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="fed83-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="fed83-130">A política de filtro de spam de saída chamada default é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de filtro de spam de saída (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="fed83-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="fed83-131">A política denominada Padrão tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="fed83-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="fed83-132">As políticas personalizadas que você cria têm sempre uma prioridade mais alta do que a política denominada Padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="fed83-133">A política denominada Padrão é a política padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="fed83-134">Para aumentar a eficácia da filtragem de spam de saída, você pode criar políticas personalizadas de spam de saída com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="fed83-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fed83-135">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="fed83-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fed83-136">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fed83-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fed83-137">Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="fed83-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="fed83-138">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fed83-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fed83-139">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fed83-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fed83-140">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="fed83-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="fed83-141">Para adicionar, modificar e excluir políticas de spam de saída, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .</span><span class="sxs-lookup"><span data-stu-id="fed83-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="fed83-142">Para acesso somente leitura às políticas de spam de saída, você precisa ser membro do grupo de função **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="fed83-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="fed83-143">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fed83-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="fed83-144">Para obter as configurações recomendadas para políticas de spam de saída, confira [configurações de política de filtro de spam de saída do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="fed83-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="fed83-145">As [políticas de alerta](../../compliance/alert-policies.md) padrão denominadas limite de envio de **emails excedidos**, os **padrões de envio de emails suspeitos detectados**e o **usuário impedido de enviar emails** já enviar notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**) sobre atividade de email de saída incomum e usuários bloqueados devido ao spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="fed83-146">Para obter mais informações, consulte [verify the Alert Settings for Restricted Users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="fed83-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="fed83-147">Recomendamos que você use essas políticas de alerta em vez das opções de notificação em políticas de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="fed83-148">Usar o centro de conformidade de & de segurança para criar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="fed83-149">Criar uma política de spam de saída personalizada no centro de conformidade de & de segurança cria a regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="fed83-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fed83-150">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="fed83-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fed83-151">Na página **configurações antispam** , clique em **criar uma política de saída**.</span><span class="sxs-lookup"><span data-stu-id="fed83-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="fed83-152">Na **política de filtro de spam de saída** , retire-o, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fed83-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="fed83-153">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="fed83-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="fed83-154">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="fed83-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="fed83-155">Opcion Expanda a seção **notificações** para configurar usuários adicionais que devem receber cópias e notificações de mensagens de email de saída suspeitas:</span><span class="sxs-lookup"><span data-stu-id="fed83-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="fed83-156">**Enviar uma cópia de mensagens de email de saída suspeitas para pessoas específicas**: essa configuração adiciona os usuários especificados como destinatários Cco às mensagens de saída suspeitas.</span><span class="sxs-lookup"><span data-stu-id="fed83-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="fed83-157">Essa configuração só funciona na política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-157">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="fed83-158">Não funciona em políticas personalizadas de spam de saída que você cria.</span><span class="sxs-lookup"><span data-stu-id="fed83-158">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="fed83-159">Para habilitar essa configuração:</span><span class="sxs-lookup"><span data-stu-id="fed83-159">To enable this setting:</span></span>

     <span data-ttu-id="fed83-160">a.</span><span class="sxs-lookup"><span data-stu-id="fed83-160">a.</span></span> <span data-ttu-id="fed83-161">Marque a caixa de seleção para habilitar a configuração.</span><span class="sxs-lookup"><span data-stu-id="fed83-161">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="fed83-162">b.</span><span class="sxs-lookup"><span data-stu-id="fed83-162">b.</span></span> <span data-ttu-id="fed83-163">Clique em **adicionar pessoas**.</span><span class="sxs-lookup"><span data-stu-id="fed83-163">Click **Add people**.</span></span> <span data-ttu-id="fed83-164">No submenu **Adicionar ou remover destinatários** que aparece:</span><span class="sxs-lookup"><span data-stu-id="fed83-164">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="fed83-165">c.</span><span class="sxs-lookup"><span data-stu-id="fed83-165">c.</span></span> <span data-ttu-id="fed83-166">Insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="fed83-166">Enter the sender's email address.</span></span> <span data-ttu-id="fed83-167">Você pode especificar vários endereços de email separados por ponto-e-vírgula (;) ou um destinatário por linha.</span><span class="sxs-lookup"><span data-stu-id="fed83-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="fed83-168">d.</span><span class="sxs-lookup"><span data-stu-id="fed83-168">d.</span></span> <span data-ttu-id="fed83-169">Click</span><span class="sxs-lookup"><span data-stu-id="fed83-169">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="fed83-171">para adicionar os destinatários.</span><span class="sxs-lookup"><span data-stu-id="fed83-171">to add the recipients.</span></span>

        <span data-ttu-id="fed83-172">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="fed83-172">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="fed83-173">Os destinatários adicionados aparecem na seção **lista de destinatários** do submenu.</span><span class="sxs-lookup"><span data-stu-id="fed83-173">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="fed83-174">Para excluir um destinatário, clique no ![ botão Remover ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="fed83-174">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="fed83-175">e.</span><span class="sxs-lookup"><span data-stu-id="fed83-175">e.</span></span> <span data-ttu-id="fed83-176">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fed83-176">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="fed83-177">Para desabilitar essa configuração, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="fed83-177">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="fed83-178">**Notificar pessoas específicas se um remetente estiver bloqueado devido ao envio de spam de saída**:</span><span class="sxs-lookup"><span data-stu-id="fed83-178">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="fed83-179">A [política de alerta](../../compliance/alert-policies.md) padrão chamada **usuário Restricted do envio de emails** já envia notificações por email para os membros do grupo **TenantAdmins** (**administradores globais**) quando os usuários são bloqueados devido a exceder os limites na seção **limites de destinatários** .</span><span class="sxs-lookup"><span data-stu-id="fed83-179">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="fed83-180">Recomendamos que você use a política de alerta em vez da configuração da política de spam de saída para notificar os administradores e outros usuários.</span><span class="sxs-lookup"><span data-stu-id="fed83-180">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="fed83-181">Para obter instruções, consulte [verificar as configurações de alerta para usuários restritos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="fed83-181">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="fed83-182">Essa configuração só funciona na política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-182">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="fed83-183">Não funciona em políticas personalizadas de spam de saída que você cria.</span><span class="sxs-lookup"><span data-stu-id="fed83-183">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="fed83-184">Para habilitar essa configuração:</span><span class="sxs-lookup"><span data-stu-id="fed83-184">To enable this setting:</span></span>

     <span data-ttu-id="fed83-185">a.</span><span class="sxs-lookup"><span data-stu-id="fed83-185">a.</span></span> <span data-ttu-id="fed83-186">Marque a caixa de seleção para habilitar a configuração.</span><span class="sxs-lookup"><span data-stu-id="fed83-186">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="fed83-187">b.</span><span class="sxs-lookup"><span data-stu-id="fed83-187">b.</span></span> <span data-ttu-id="fed83-188">Clique em **adicionar pessoas**.</span><span class="sxs-lookup"><span data-stu-id="fed83-188">Click **Add people**.</span></span> <span data-ttu-id="fed83-189">No submenu **Adicionar ou remover destinatários** que aparece:</span><span class="sxs-lookup"><span data-stu-id="fed83-189">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="fed83-190">c.</span><span class="sxs-lookup"><span data-stu-id="fed83-190">c.</span></span> <span data-ttu-id="fed83-191">Insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="fed83-191">Enter the sender's email address.</span></span> <span data-ttu-id="fed83-192">Você pode especificar vários endereços de email separados por ponto-e-vírgula (;) ou um destinatário por linha.</span><span class="sxs-lookup"><span data-stu-id="fed83-192">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="fed83-193">d.</span><span class="sxs-lookup"><span data-stu-id="fed83-193">d.</span></span> <span data-ttu-id="fed83-194">Click</span><span class="sxs-lookup"><span data-stu-id="fed83-194">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="fed83-196">para adicionar os destinatários.</span><span class="sxs-lookup"><span data-stu-id="fed83-196">to add the recipients.</span></span>

        <span data-ttu-id="fed83-197">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="fed83-197">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="fed83-198">Os destinatários adicionados aparecem na seção **lista de destinatários** do submenu.</span><span class="sxs-lookup"><span data-stu-id="fed83-198">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="fed83-199">Para excluir um destinatário, clique no ![ botão Remover ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="fed83-199">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="fed83-200">e.</span><span class="sxs-lookup"><span data-stu-id="fed83-200">e.</span></span> <span data-ttu-id="fed83-201">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fed83-201">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="fed83-202">Para desabilitar essa configuração, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="fed83-202">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="fed83-203">Opcion Expanda a seção **limites de destinatário** para configurar os limites e as ações para mensagens de email de saída suspeitas:</span><span class="sxs-lookup"><span data-stu-id="fed83-203">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="fed83-204">Essas configurações só são aplicáveis às caixas de correio baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="fed83-204">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="fed83-205">**Número máximo de destinatários por usuário**</span><span class="sxs-lookup"><span data-stu-id="fed83-205">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="fed83-206">Um valor válido é de 0 a 10000.</span><span class="sxs-lookup"><span data-stu-id="fed83-206">A valid value is 0 to 10000.</span></span> <span data-ttu-id="fed83-207">O valor padrão é 0, o que significa que os padrões de serviço são usados.</span><span class="sxs-lookup"><span data-stu-id="fed83-207">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="fed83-208">Para obter mais informações, consulte [enviando limites nas opções do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="fed83-208">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="fed83-209">**Limite por hora externo**: o número máximo de destinatários externos por hora.</span><span class="sxs-lookup"><span data-stu-id="fed83-209">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="fed83-210">**Limite por hora interno**: o número máximo de destinatários internos por hora.</span><span class="sxs-lookup"><span data-stu-id="fed83-210">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="fed83-211">**Limite diário**: o número total máximo de destinatários por dia.</span><span class="sxs-lookup"><span data-stu-id="fed83-211">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="fed83-212">**Ação quando um usuário exceder os limites acima**: Configure a ação a ser tomada quando qualquer um dos **limites de destinatário** for excedido.</span><span class="sxs-lookup"><span data-stu-id="fed83-212">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="fed83-213">Para todas as ações, os destinatários especificados na política de alerta do usuário que está **impedido de enviar emails** (e, na agora, **pessoas de notificar-se um remetente está bloqueado devido ao envio de spam** de saída na política de spam receber notificações por email.</span><span class="sxs-lookup"><span data-stu-id="fed83-213">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="fed83-214">**Impedir que o usuário envie email até o dia seguinte**: Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-214">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="fed83-215">As notificações por email são enviadas e o usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC.</span><span class="sxs-lookup"><span data-stu-id="fed83-215">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="fed83-216">Não há como o administrador substituir esse bloco.</span><span class="sxs-lookup"><span data-stu-id="fed83-216">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="fed83-217">O alerta de atividade chamado **usuário impedido de enviar email** notifica os administradores (por email e na página **exibir alertas** ).</span><span class="sxs-lookup"><span data-stu-id="fed83-217">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="fed83-218">Qualquer destinatário especificado em **notificar pessoas específicas se um remetente estiver bloqueado devido ao envio** da configuração de spam de saída na política também é notificado.</span><span class="sxs-lookup"><span data-stu-id="fed83-218">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="fed83-219">O usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC.</span><span class="sxs-lookup"><span data-stu-id="fed83-219">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="fed83-220">Não há como o administrador substituir esse bloco.</span><span class="sxs-lookup"><span data-stu-id="fed83-220">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="fed83-221">**Impedir que o usuário envie emails**: as notificações por email são enviadas, o usuário é adicionado ao portal **[ <https://sip.protection.office.com/restrictedusers> Restricted Users]** no centro de conformidade do & de segurança e o usuário não pode enviar emails até que sejam removidos do portal de **usuários restritos** por um administrador. Depois que um administrador remover o usuário da lista, o usuário não será restringido novamente nesse dia.</span><span class="sxs-lookup"><span data-stu-id="fed83-221">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="fed83-222">Para obter instruções, consulte [removendo um usuário do portal de usuários restritos após o envio de email de spam](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="fed83-222">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="fed83-223">**Nenhuma ação, somente alerta**: as notificações por email são enviadas.</span><span class="sxs-lookup"><span data-stu-id="fed83-223">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="fed83-224">Precisam Expanda a seção **aplicado a** para identificar os remetentes internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="fed83-224">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="fed83-225">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="fed83-225">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="fed83-226">Vários valores da mesma condição ou uso de exceção ou lógica (por exemplo, _ \< sender1 \> _ ou _ \< sender2 \> _).</span><span class="sxs-lookup"><span data-stu-id="fed83-226">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="fed83-227">Condições ou uso de exceções diferentes ou lógicas (por exemplo, _ \< sender1 \> _ e _ \< membro do \> grupo 1_).</span><span class="sxs-lookup"><span data-stu-id="fed83-227">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="fed83-228">O mais fácil é clicar em **Adicionar uma condição** três vezes para ver todas as condições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fed83-228">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="fed83-229">Clique em ![botão Remover](../../media/scc-remove-icon.png) para remover condições que você não queira configurar.</span><span class="sxs-lookup"><span data-stu-id="fed83-229">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="fed83-230">**O domínio do remetente é**: especifica remetentes em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="fed83-230">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="fed83-231">Clique na caixa **Adicionar uma marca** para ver e selecionar um domínio.</span><span class="sxs-lookup"><span data-stu-id="fed83-231">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="fed83-232">Clique novamente na caixa **Adicionar uma marca** para selecionar domínios adicionais se mais de um domínio estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="fed83-232">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="fed83-233">O **remetente é**: especifica um ou mais usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fed83-233">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="fed83-234">Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="fed83-234">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="fed83-235">Clique novamente na caixa **Adicionar uma marca** para selecionar outros remetentes.</span><span class="sxs-lookup"><span data-stu-id="fed83-235">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="fed83-236">**O remetente é um membro de**: especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="fed83-236">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="fed83-237">Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="fed83-237">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="fed83-238">Clique novamente na caixa **Adicionar uma marca** para selecionar outros remetentes.</span><span class="sxs-lookup"><span data-stu-id="fed83-238">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="fed83-239">**Exceto se**: para adicionar exceções à regra, clique em **Adicionar uma condição** três vezes para ver todas as exceções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fed83-239">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="fed83-240">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="fed83-240">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="fed83-241">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fed83-241">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="fed83-242">Usar o centro de conformidade de & de segurança para exibir políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-242">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="fed83-243">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="fed83-243">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fed83-244">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política de spam de saída:</span><span class="sxs-lookup"><span data-stu-id="fed83-244">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="fed83-245">A política padrão denominada **política de filtro de spam de saída**.</span><span class="sxs-lookup"><span data-stu-id="fed83-245">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="fed83-246">Uma política personalizada que você criou onde o valor na coluna **tipo** é a **política de spam de saída personalizada**.</span><span class="sxs-lookup"><span data-stu-id="fed83-246">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="fed83-247">As configurações de política são exibidas nos detalhes da política expandida que aparecem ou você pode clicar em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="fed83-247">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="fed83-248">Usar o centro de conformidade de & de segurança para modificar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-248">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="fed83-249">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="fed83-249">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fed83-250">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política de spam de saída:</span><span class="sxs-lookup"><span data-stu-id="fed83-250">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="fed83-251">A política padrão denominada **política de filtro de spam de saída**.</span><span class="sxs-lookup"><span data-stu-id="fed83-251">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="fed83-252">Uma política personalizada que você criou onde o valor na coluna **tipo** é a **política de spam de saída personalizada**.</span><span class="sxs-lookup"><span data-stu-id="fed83-252">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="fed83-253">Clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="fed83-253">Click **Edit policy**.</span></span>

<span data-ttu-id="fed83-254">Para políticas de spam de saída personalizadas, as configurações disponíveis no submenu que aparecem são idênticas àquelas descritas na seção [usar o centro de conformidade de & de segurança para criar políticas de spam de saída](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="fed83-254">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="fed83-255">Para a política de spam de saída padrão chamada **política de filtro de spam de saída**, a seção **aplicado à** não está disponível (a política se aplica a todos) e não é possível renomear a política.</span><span class="sxs-lookup"><span data-stu-id="fed83-255">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="fed83-256">Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="fed83-256">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="fed83-257">Habilitar ou desabilitar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-257">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="fed83-258">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="fed83-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fed83-259">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política personalizada que você criou (o valor na coluna **tipo** é a política de **spam de saída personalizada**).</span><span class="sxs-lookup"><span data-stu-id="fed83-259">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="fed83-260">Nos detalhes exibidos da política expandida, observe o valor na coluna **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="fed83-260">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="fed83-261">Mova o botão de alternância para a esquerda para desabilitar a política:</span><span class="sxs-lookup"><span data-stu-id="fed83-261">Move the toggle to the left to disable the policy:</span></span> ![Desativar](../../media/scc-toggle-off.png)

   <span data-ttu-id="fed83-263">Mova o botão de alternância para a direita para habilitar a política:</span><span class="sxs-lookup"><span data-stu-id="fed83-263">Move the toggle to the right to enable the policy:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="fed83-265">Não é possível desabilitar a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-265">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="fed83-266">Definir a prioridade das políticas personalizadas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-266">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="fed83-267">Por padrão, as políticas de spam de saída recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="fed83-267">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="fed83-268">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="fed83-268">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fed83-269">Duas políticas não podem ter a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="fed83-269">No two policies can have the same priority.</span></span>

<span data-ttu-id="fed83-270">As políticas de spam de saída personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="fed83-270">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="fed83-271">A política de spam de saída padrão chamada **política de filtro de spam de saída** tem o valor de prioridade **mais baixo**e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="fed83-271">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="fed83-272">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="fed83-272">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="fed83-273">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="fed83-273">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fed83-274">Na página **configurações antispam** , encontre as políticas nas quais o valor na coluna **tipo** é a política de **spam de saída personalizada**.</span><span class="sxs-lookup"><span data-stu-id="fed83-274">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="fed83-275">Observe os valores na coluna **Prioridade**:</span><span class="sxs-lookup"><span data-stu-id="fed83-275">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="fed83-276">A política de spam de saída personalizada com a prioridade mais alta tem o ![ ícone de seta para baixo ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="fed83-276">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="fed83-277">A política de spam de saída personalizada com a prioridade mais baixa tem o ![ ícone de seta para cima ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por exemplo, ![ ícone de seta para cima ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="fed83-277">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="fed83-278">Se você tiver três ou mais políticas de spam de saída personalizadas, as políticas entre a prioridade mais alta e a mais baixa terão valores para cima ícone de seta para ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ baixo ícone ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por exemplo, seta para cima ícone de seta ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ para baixo ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="fed83-278">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="fed83-279">Clique em</span><span class="sxs-lookup"><span data-stu-id="fed83-279">Click</span></span> ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="fed83-281">ou</span><span class="sxs-lookup"><span data-stu-id="fed83-281">or</span></span> ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="fed83-283">para mover a política de spam de saída personalizada para cima ou para baixo na lista de prioridades.</span><span class="sxs-lookup"><span data-stu-id="fed83-283">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="fed83-284">Usar o centro de conformidade de & de segurança para remover políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-284">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="fed83-285">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="fed83-285">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fed83-286">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir a política personalizada que você deseja excluir (a coluna **tipo** é **personalizada spam de saída**).</span><span class="sxs-lookup"><span data-stu-id="fed83-286">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="fed83-287">Nas informações da política expandida, clique em **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="fed83-287">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="fed83-288">Clique em **Sim** na caixa de diálogo exibida.</span><span class="sxs-lookup"><span data-stu-id="fed83-288">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="fed83-289">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-289">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="fed83-290">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="fed83-291">Usar o PowerShell para criar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="fed83-292">A criação de uma política de spam de saída no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="fed83-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fed83-293">Criar a política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-293">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="fed83-294">Crie a regra de filtro de spam de saída que especifica a política de filtro de spam de saída à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="fed83-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="fed83-295">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="fed83-295">**Notes**:</span></span>

- <span data-ttu-id="fed83-296">Você pode criar uma nova regra de filtro de spam de saída e atribuir uma diretiva de filtro de spam de saída não associada existente a ela.</span><span class="sxs-lookup"><span data-stu-id="fed83-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="fed83-297">Uma regra de filtro de spam de saída não pode ser associada a mais de uma política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="fed83-298">Você pode definir as seguintes configurações em novas políticas de filtro de spam de saída no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="fed83-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="fed83-299">Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="fed83-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="fed83-300">Definir a prioridade da política durante a criação (_Priority_ _ \< número \> _de prioridade) no cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="fed83-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="fed83-301">Uma nova política de filtro de spam de saída que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="fed83-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="fed83-302">Etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="fed83-303">Para criar uma política de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="fed83-304">Este exemplo cria uma nova política de filtro de spam de saída chamada contoso executivos com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fed83-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="fed83-305">Os limites de taxa de destinatários são restritos a valores menores que o padrão.</span><span class="sxs-lookup"><span data-stu-id="fed83-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="fed83-306">Para obter mais informações, consulte [enviando limites nas opções do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="fed83-306">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="fed83-307">Depois que um dos limites é alcançado, o usuário é impedido de enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="fed83-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="fed83-308">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="fed83-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="fed83-309">Etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="fed83-310">Para criar uma regra de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="fed83-311">Este exemplo cria uma nova regra de filtro de spam de saída chamada contoso executivos com estas configurações:</span><span class="sxs-lookup"><span data-stu-id="fed83-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="fed83-312">A política de filtro de spam de saída chamada contoso executivos está associada à regra.</span><span class="sxs-lookup"><span data-stu-id="fed83-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="fed83-313">A regra se aplica aos membros do grupo chamado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="fed83-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="fed83-314">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="fed83-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="fed83-315">Usar o PowerShell para exibir políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="fed83-316">Para retornar uma lista resumida de todas as políticas de filtro de spam de saída, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="fed83-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="fed83-317">Para retornar informações detalhadas sobre uma política de filtro de spam de saída específica, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="fed83-318">Este exemplo retorna todos os valores de propriedade da política de filtro de spam de saída chamada executivos.</span><span class="sxs-lookup"><span data-stu-id="fed83-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="fed83-319">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="fed83-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="fed83-320">Usar o PowerShell para exibir regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="fed83-321">Para exibir as regras de filtro de spam de saída existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="fed83-322">Para retornar uma lista resumida de todas as regras de filtro de spam de saída, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="fed83-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="fed83-323">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fed83-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="fed83-324">Para retornar informações detalhadas sobre uma regra de filtro de spam de saída específica, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="fed83-325">Este exemplo retorna todos os valores de propriedade da regra de filtro de spam de saída chamada contoso executivos.</span><span class="sxs-lookup"><span data-stu-id="fed83-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="fed83-326">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="fed83-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="fed83-327">Usar o PowerShell para modificar as políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="fed83-328">As mesmas configurações estão disponíveis quando você modifica uma política de filtro de malware no PowerShell quando cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="fed83-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="fed83-329">**Observação**: não é possível renomear uma política de filtro de spam de saída (o cmdlet **set-HostedOutboundSpamFilterPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="fed83-329">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fed83-330">Ao renomear uma política de spam de saída no centro de conformidade & segurança, você estará apenas renomeando a _regra_de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="fed83-330">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="fed83-331">Para modificar uma política de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fed83-332">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="fed83-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="fed83-333">Usar o PowerShell para modificar as regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="fed83-334">A única configuração que não está disponível quando você modifica uma regra de filtro de spam de saída no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="fed83-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fed83-335">Para habilitar ou desabilitar regras de filtro de spam de saída existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="fed83-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="fed83-336">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra de filtro de spam de saída no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fed83-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="fed83-337">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="fed83-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="fed83-338">Para modificar uma regra de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fed83-339">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="fed83-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="fed83-340">Usar o PowerShell para habilitar ou desabilitar as regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="fed83-341">Habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell habilita ou desabilita toda a política de spam de saída (a regra de filtro de spam de saída e a política de filtro de spam de saída atribuída).</span><span class="sxs-lookup"><span data-stu-id="fed83-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="fed83-342">Você não pode habilitar ou desabilitar a política de spam de saída padrão (sempre é sempre aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="fed83-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="fed83-343">Para habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="fed83-344">Este exemplo desabilita a regra de filtro de spam de saída chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="fed83-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="fed83-345">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="fed83-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="fed83-346">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="fed83-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="fed83-347">Usar o PowerShell para definir a prioridade das regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="fed83-348">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="fed83-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fed83-349">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="fed83-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fed83-350">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="fed83-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fed83-351">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="fed83-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fed83-352">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="fed83-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fed83-353">Para definir a prioridade de uma regra de filtro de spam de saída no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fed83-354">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="fed83-354">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="fed83-355">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="fed83-355">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="fed83-356">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="fed83-356">**Notes**:</span></span>

- <span data-ttu-id="fed83-357">Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="fed83-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="fed83-358">A política de filtro de spam padrão de saída não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="fed83-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="fed83-359">Usar o PowerShell para remover as políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="fed83-360">Quando você usa o PowerShell para remover uma política de filtro de spam de saída, a regra de filtro de spam de saída correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="fed83-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="fed83-361">Para remover uma política de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fed83-362">Este exemplo remove a política de filtro de spam de saída chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="fed83-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fed83-363">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="fed83-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="fed83-364">Usar o PowerShell para remover as regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="fed83-365">Quando você usa o PowerShell para remover uma regra de filtro de spam de saída, a política de filtro de spam de saída correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="fed83-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="fed83-366">Para remover uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fed83-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="fed83-367">Este exemplo remove a regra de filtro de spam de saída chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="fed83-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="fed83-368">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="fed83-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="fed83-369">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="fed83-369">For more information</span></span>

[<span data-ttu-id="fed83-370">Remover usuários bloqueados do portal Usuários restritos</span><span class="sxs-lookup"><span data-stu-id="fed83-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="fed83-371">Pool de entrega de alto risco para mensagens de saída</span><span class="sxs-lookup"><span data-stu-id="fed83-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="fed83-372">Perguntas frequentes sobre a proteção antispam</span><span class="sxs-lookup"><span data-stu-id="fed83-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
