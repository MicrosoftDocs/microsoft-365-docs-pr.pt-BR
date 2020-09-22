---
title: Configurar a filtragem de spam de saída
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: 2c7a48280487944352f4ee8afc1e7f0596186a3d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203294"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="77532-103">Configurar a filtragem de spam de saída no EOP</span><span class="sxs-lookup"><span data-stu-id="77532-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="77532-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, mensagens de email de saída enviadas por meio do EOP são verificadas automaticamente quanto ao spam e à atividade de envio incomum.</span><span class="sxs-lookup"><span data-stu-id="77532-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="77532-105">O spam de saída de um usuário em sua organização normalmente indica uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="77532-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="77532-106">Mensagens de saída suspeitas são marcadas como spam (independentemente do nível de confiança de spam ou SCL) e são roteadas através do [pool de entrega de alto risco](high-risk-delivery-pool-for-outbound-messages.md) para ajudar a proteger a reputação do serviço (ou seja, manter os servidores de email de origem do Microsoft 365 fora das listas de bloqueios de IP).</span><span class="sxs-lookup"><span data-stu-id="77532-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="77532-107">Os administradores são notificados automaticamente sobre atividade de email de saída suspeita e usuários bloqueados por meio de [políticas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="77532-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="77532-108">O EOP usa políticas de spam de saída como parte da defesa geral da sua organização contra spam.</span><span class="sxs-lookup"><span data-stu-id="77532-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="77532-109">Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="77532-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="77532-110">Os administradores podem exibir, editar e configurar (mas não excluir) a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="77532-111">Para maior granularidade, você também pode criar políticas personalizadas de spam de saída que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="77532-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="77532-112">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="77532-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="77532-113">Você pode configurar políticas de spam de saída no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="77532-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="77532-114">Os elementos básicos de uma política de spam de saída no EOP são:</span><span class="sxs-lookup"><span data-stu-id="77532-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="77532-115">**A política de filtro de spam de saída**: especifica as ações para verdicts de filtragem de spam de saída e as opções de notificação.</span><span class="sxs-lookup"><span data-stu-id="77532-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="77532-116">**A regra de filtro de spam de saída**: especifica a prioridade e os filtros de destinatário (aos quais a política se aplica) para uma política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="77532-117">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de spam de saída no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="77532-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="77532-118">Ao criar uma política, você realmente está criando uma regra de filtro de spam de saída e a política de filtro de spam de saída associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="77532-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="77532-119">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="77532-120">Todas as outras configurações modificam a política de filtro de spam de saída associada.</span><span class="sxs-lookup"><span data-stu-id="77532-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="77532-121">Quando você remover uma política, a regra de filtro de spam de saída e a política de filtro de spam de saída associada serão removidas.</span><span class="sxs-lookup"><span data-stu-id="77532-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="77532-122">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="77532-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="77532-123">Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de spam de saída](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) , posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="77532-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="77532-124">Todas as organizações têm uma política interna de spam de saída chamada Default que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="77532-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="77532-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de filtro de spam de saída (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="77532-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="77532-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="77532-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="77532-127">As políticas personalizadas que você cria têm sempre uma prioridade mais alta do que a política denominada Padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="77532-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="77532-129">Para aumentar a eficácia da filtragem de spam de saída, você pode criar políticas personalizadas de spam de saída com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="77532-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="77532-130">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="77532-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="77532-131">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="77532-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="77532-132">Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="77532-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="77532-133">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="77532-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="77532-134">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="77532-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="77532-135">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="77532-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="77532-136">Para adicionar, modificar e excluir políticas de spam de saída, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="77532-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="77532-137">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="77532-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="77532-138">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="77532-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="77532-139">Para acesso somente leitura às políticas de spam de saída, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="77532-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="77532-140">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="77532-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="77532-141">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="77532-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="77532-142">Para obter as configurações recomendadas para políticas de spam de saída, confira [configurações de política de filtro de spam de saída do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="77532-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="77532-143">As [políticas de alerta](../../compliance/alert-policies.md) padrão denominadas limite de envio de **emails excedidos**, os **padrões de envio de emails suspeitos detectados**e o **usuário impedido de enviar emails** já enviar notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**) sobre atividade de email de saída incomum e usuários bloqueados devido ao spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="77532-144">Para obter mais informações, consulte [verify the Alert Settings for Restricted Users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="77532-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="77532-145">Recomendamos que você use essas políticas de alerta em vez das opções de notificação em políticas de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="77532-146">Usar o centro de conformidade de & de segurança para criar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="77532-147">Criar uma política de spam de saída personalizada no centro de conformidade de & de segurança cria a regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="77532-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="77532-148">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="77532-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="77532-149">Na página **configurações antispam** , clique em **criar uma política de saída**.</span><span class="sxs-lookup"><span data-stu-id="77532-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="77532-150">Na **política de filtro de spam de saída** , retire-o, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="77532-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="77532-151">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="77532-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="77532-152">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="77532-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="77532-153">Opcion Expanda a seção **notificações** para configurar usuários adicionais que devem receber cópias e notificações de mensagens de email de saída suspeitas:</span><span class="sxs-lookup"><span data-stu-id="77532-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="77532-154">**Enviar uma cópia de mensagens de email de saída suspeitas para pessoas específicas**: essa configuração adiciona os usuários especificados como destinatários Cco às mensagens de saída suspeitas.</span><span class="sxs-lookup"><span data-stu-id="77532-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="77532-155">Essa configuração só funciona na política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="77532-156">Não funciona em políticas personalizadas de spam de saída que você cria.</span><span class="sxs-lookup"><span data-stu-id="77532-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="77532-157">Para habilitar essa configuração:</span><span class="sxs-lookup"><span data-stu-id="77532-157">To enable this setting:</span></span>

     1. <span data-ttu-id="77532-158">Marque a caixa de seleção para habilitar a configuração.</span><span class="sxs-lookup"><span data-stu-id="77532-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="77532-159">Clique em **adicionar pessoas**.</span><span class="sxs-lookup"><span data-stu-id="77532-159">Click **Add people**.</span></span> <span data-ttu-id="77532-160">No submenu **Adicionar ou remover destinatários** que aparece:</span><span class="sxs-lookup"><span data-stu-id="77532-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="77532-161">Insira o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="77532-161">Enter the sender's email address.</span></span> <span data-ttu-id="77532-162">Você pode especificar vários endereços de email separados por ponto-e-vírgula (;) ou um destinatário por linha.</span><span class="sxs-lookup"><span data-stu-id="77532-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="77532-163">Click</span><span class="sxs-lookup"><span data-stu-id="77532-163">Click</span></span> ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="77532-165">para adicionar os destinatários.</span><span class="sxs-lookup"><span data-stu-id="77532-165">to add the recipients.</span></span>

        <span data-ttu-id="77532-166">Repita essas etapas quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="77532-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="77532-167">Os destinatários adicionados aparecem na seção **lista de destinatários** do submenu.</span><span class="sxs-lookup"><span data-stu-id="77532-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="77532-168">Para excluir um destinatário, clique no ![ botão Remover ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="77532-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="77532-169">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="77532-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="77532-170">Para desabilitar essa configuração, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="77532-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="77532-171">**Notificar pessoas específicas se um remetente estiver bloqueado devido ao envio de spam de saída**:</span><span class="sxs-lookup"><span data-stu-id="77532-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="77532-172">Essa configuração está no processo de ser preterido das políticas de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="77532-173">A [política de alerta](../../compliance/alert-policies.md) padrão chamada **usuário Restricted do envio de emails** já envia notificações por email para os membros do grupo **TenantAdmins** (**administradores globais**) quando os usuários são bloqueados devido a exceder os limites na seção **limites de destinatários** .</span><span class="sxs-lookup"><span data-stu-id="77532-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="77532-174">É **altamente recomendável que você use a política de alerta em vez da configuração da política de spam de saída para notificar os administradores e outros usuários**.</span><span class="sxs-lookup"><span data-stu-id="77532-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="77532-175">Para obter instruções, consulte [verificar as configurações de alerta para usuários restritos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="77532-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="77532-176">Opcion Expanda a seção **limites de destinatário** para configurar os limites e as ações para mensagens de email de saída suspeitas:</span><span class="sxs-lookup"><span data-stu-id="77532-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="77532-177">Essas configurações só são aplicáveis às caixas de correio baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="77532-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="77532-178">**Número máximo de destinatários por usuário**</span><span class="sxs-lookup"><span data-stu-id="77532-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="77532-179">Um valor válido é de 0 a 10000.</span><span class="sxs-lookup"><span data-stu-id="77532-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="77532-180">O valor padrão é 0, o que significa que os padrões de serviço são usados.</span><span class="sxs-lookup"><span data-stu-id="77532-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="77532-181">Para obter mais informações, consulte [enviando limites](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="77532-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="77532-182">**Limite por hora externo**: o número máximo de destinatários externos por hora.</span><span class="sxs-lookup"><span data-stu-id="77532-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="77532-183">**Limite por hora interno**: o número máximo de destinatários internos por hora.</span><span class="sxs-lookup"><span data-stu-id="77532-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="77532-184">**Limite diário**: o número total máximo de destinatários por dia.</span><span class="sxs-lookup"><span data-stu-id="77532-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="77532-185">**Ação quando um usuário exceder os limites acima**: Configure a ação a ser tomada quando qualquer um dos **limites de destinatário** for excedido.</span><span class="sxs-lookup"><span data-stu-id="77532-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="77532-186">Para todas as ações, os destinatários especificados na política de alerta do usuário que está **impedido de enviar emails** (e, na agora, **pessoas de notificar-se um remetente está bloqueado devido ao envio de spam** de saída na política de spam receber notificações por email.</span><span class="sxs-lookup"><span data-stu-id="77532-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="77532-187">**Impedir que o usuário envie email até o dia seguinte**: Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="77532-188">As notificações por email são enviadas e o usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC.</span><span class="sxs-lookup"><span data-stu-id="77532-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="77532-189">Não há como o administrador substituir esse bloco.</span><span class="sxs-lookup"><span data-stu-id="77532-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="77532-190">O alerta de atividade chamado **usuário impedido de enviar email** notifica os administradores (por email e na página **exibir alertas** ).</span><span class="sxs-lookup"><span data-stu-id="77532-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="77532-191">Qualquer destinatário especificado em **notificar pessoas específicas se um remetente estiver bloqueado devido ao envio** da configuração de spam de saída na política também é notificado.</span><span class="sxs-lookup"><span data-stu-id="77532-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="77532-192">O usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC.</span><span class="sxs-lookup"><span data-stu-id="77532-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="77532-193">Não há como o administrador substituir esse bloco.</span><span class="sxs-lookup"><span data-stu-id="77532-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="77532-194">**Impedir que o usuário envie emails**: as notificações por email são enviadas, o usuário é adicionado ao portal **[ <https://sip.protection.office.com/restrictedusers> Restricted Users]** no centro de conformidade do & de segurança e o usuário não pode enviar emails até que sejam removidos do portal de **usuários restritos** por um administrador. Depois que um administrador remover o usuário da lista, o usuário não será restringido novamente nesse dia.</span><span class="sxs-lookup"><span data-stu-id="77532-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="77532-195">Para obter instruções, consulte [removendo um usuário do portal de usuários restritos após o envio de email de spam](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="77532-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="77532-196">**Nenhuma ação, somente alerta**: as notificações por email são enviadas.</span><span class="sxs-lookup"><span data-stu-id="77532-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="77532-197">Opcion Expanda a seção de **encaminhamento automático** para controlar o encaminhamento automático de emails de usuários para remetentes externos.</span><span class="sxs-lookup"><span data-stu-id="77532-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="77532-198">Para obter mais informações sobre o encaminhamento automático, consulte [Configure e-mail Forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="77532-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="77532-199">Antes de setembro de 2020, essas configurações estão disponíveis, mas não são impostas.</span><span class="sxs-lookup"><span data-stu-id="77532-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="77532-200">Essas configurações se aplicam apenas às caixas de correio baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="77532-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="77532-201">O encaminhamento automático para destinatários internos não é afetado por essas configurações.</span><span class="sxs-lookup"><span data-stu-id="77532-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="77532-202">Os valores disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="77532-202">The available values are:</span></span>

   - <span data-ttu-id="77532-203">**Controlado automaticamente pelo sistema**: permite a filtragem de spam de saída para controlar o encaminhamento de email externo automático.</span><span class="sxs-lookup"><span data-stu-id="77532-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="77532-204">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-204">This is the default value.</span></span>

   - <span data-ttu-id="77532-205">**Ativado**: o encaminhamento de email externo automático não está desabilitado pela política.</span><span class="sxs-lookup"><span data-stu-id="77532-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="77532-206">**Off**: todo o encaminhamento de email externo automático é desabilitado pela política.</span><span class="sxs-lookup"><span data-stu-id="77532-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="77532-207">Precisam Expanda a seção **aplicado a** para identificar os remetentes internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="77532-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="77532-208">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="77532-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="77532-209">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<sender1\>_ ou _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="77532-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="77532-210">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<sender1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="77532-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="77532-211">O mais fácil é clicar em **Adicionar uma condição** três vezes para ver todas as condições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="77532-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="77532-212">Clique em ![botão Remover](../../media/scc-remove-icon.png) para remover condições que você não queira configurar.</span><span class="sxs-lookup"><span data-stu-id="77532-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="77532-213">**O domínio do remetente é**: especifica remetentes em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="77532-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="77532-214">Clique na caixa **Adicionar uma marca** para ver e selecionar um domínio.</span><span class="sxs-lookup"><span data-stu-id="77532-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="77532-215">Clique novamente na caixa **Adicionar uma marca** para selecionar domínios adicionais se mais de um domínio estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="77532-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="77532-216">O **remetente é**: especifica um ou mais usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="77532-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="77532-217">Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="77532-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="77532-218">Clique novamente na caixa **Adicionar uma marca** para selecionar outros remetentes.</span><span class="sxs-lookup"><span data-stu-id="77532-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="77532-219">**O remetente é um membro de**: especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="77532-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="77532-220">Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="77532-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="77532-221">Clique novamente na caixa **Adicionar uma marca** para selecionar outros remetentes.</span><span class="sxs-lookup"><span data-stu-id="77532-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="77532-222">**Exceto se**: para adicionar exceções à regra, clique em **Adicionar uma condição** três vezes para ver todas as exceções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="77532-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="77532-223">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="77532-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="77532-224">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="77532-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="77532-225">Usar o centro de conformidade de & de segurança para exibir políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="77532-226">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="77532-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="77532-227">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política de spam de saída:</span><span class="sxs-lookup"><span data-stu-id="77532-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="77532-228">A política padrão denominada **política de filtro de spam de saída**.</span><span class="sxs-lookup"><span data-stu-id="77532-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="77532-229">Uma política personalizada que você criou onde o valor na coluna **tipo** é a **política de spam de saída personalizada**.</span><span class="sxs-lookup"><span data-stu-id="77532-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="77532-230">As configurações de política são exibidas nos detalhes da política expandida que aparecem ou você pode clicar em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="77532-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="77532-231">Usar o centro de conformidade de & de segurança para modificar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="77532-232">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="77532-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="77532-233">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política de spam de saída:</span><span class="sxs-lookup"><span data-stu-id="77532-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="77532-234">A política padrão denominada **política de filtro de spam de saída**.</span><span class="sxs-lookup"><span data-stu-id="77532-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="77532-235">Uma política personalizada que você criou onde o valor na coluna **tipo** é a **política de spam de saída personalizada**.</span><span class="sxs-lookup"><span data-stu-id="77532-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="77532-236">Clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="77532-236">Click **Edit policy**.</span></span>

<span data-ttu-id="77532-237">Para políticas de spam de saída personalizadas, as configurações disponíveis no submenu que aparecem são idênticas àquelas descritas na seção [usar o centro de conformidade de & de segurança para criar políticas de spam de saída](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="77532-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="77532-238">Para a política de spam de saída padrão chamada **política de filtro de spam de saída**, a seção **aplicado à** não está disponível (a política se aplica a todos) e não é possível renomear a política.</span><span class="sxs-lookup"><span data-stu-id="77532-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="77532-239">Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="77532-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="77532-240">Habilitar ou desabilitar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="77532-241">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="77532-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="77532-242">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política personalizada que você criou (o valor na coluna **tipo** é a política de **spam de saída personalizada**).</span><span class="sxs-lookup"><span data-stu-id="77532-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="77532-243">Nos detalhes exibidos da política expandida, observe o valor na coluna **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="77532-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="77532-244">Mova o botão de alternância para a esquerda para desabilitar a política:</span><span class="sxs-lookup"><span data-stu-id="77532-244">Move the toggle to the left to disable the policy:</span></span> ![Desativar](../../media/scc-toggle-off.png)

   <span data-ttu-id="77532-246">Mova o botão de alternância para a direita para habilitar a política:</span><span class="sxs-lookup"><span data-stu-id="77532-246">Move the toggle to the right to enable the policy:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="77532-248">Não é possível desabilitar a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="77532-249">Definir a prioridade das políticas personalizadas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="77532-250">Por padrão, as políticas de spam de saída recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="77532-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="77532-251">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="77532-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="77532-252">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="77532-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="77532-253">As políticas de spam de saída personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="77532-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="77532-254">A política de spam de saída padrão chamada **política de filtro de spam de saída** tem o valor de prioridade **mais baixo**e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="77532-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="77532-255">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="77532-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="77532-256">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="77532-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="77532-257">Na página **configurações antispam** , encontre as políticas nas quais o valor na coluna **tipo** é a política de **spam de saída personalizada**.</span><span class="sxs-lookup"><span data-stu-id="77532-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="77532-258">Observe os valores na coluna **Prioridade**:</span><span class="sxs-lookup"><span data-stu-id="77532-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="77532-259">A política de spam de saída personalizada com a prioridade mais alta tem o ![ ícone de seta para baixo ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="77532-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="77532-260">A política de spam de saída personalizada com a prioridade mais baixa tem o ![ ícone de seta para cima ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por exemplo, ![ ícone de seta para cima ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="77532-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="77532-261">Se você tiver três ou mais políticas de spam de saída personalizadas, as políticas entre a prioridade mais alta e a mais baixa terão valores para cima ícone de seta para ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ baixo ícone ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por exemplo, seta para cima ícone de seta ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ para baixo ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="77532-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="77532-262">Clique em</span><span class="sxs-lookup"><span data-stu-id="77532-262">Click</span></span> ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="77532-264">ou</span><span class="sxs-lookup"><span data-stu-id="77532-264">or</span></span> ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="77532-266">para mover a política de spam de saída personalizada para cima ou para baixo na lista de prioridades.</span><span class="sxs-lookup"><span data-stu-id="77532-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="77532-267">Usar o centro de conformidade de & de segurança para remover políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="77532-268">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="77532-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="77532-269">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir a política personalizada que você deseja excluir (a coluna **tipo** é **personalizada spam de saída**).</span><span class="sxs-lookup"><span data-stu-id="77532-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="77532-270">Nas informações da política expandida, clique em **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="77532-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="77532-271">Clique em **Sim** na caixa de diálogo exibida.</span><span class="sxs-lookup"><span data-stu-id="77532-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="77532-272">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="77532-273">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="77532-274">Conforme descrito anteriormente, uma política de spam de saída consiste em uma política de filtro de spam de saída e uma regra de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="77532-275">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a diferença entre políticas de filtro de spam de saída e regras de filtro de spam de saída é aparente.</span><span class="sxs-lookup"><span data-stu-id="77532-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="77532-276">Você gerencia as políticas de filtro de spam de saída usando os cmdlets \*\* \* -HostedOutboundSpamFilterPolicy\*\* e gerencia as regras de filtro de spam de saída usando os cmdlets \*\* \* -HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="77532-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="77532-277">No PowerShell, você cria primeiro a política de filtro de spam de saída e, em seguida, cria a regra de filtro de spam de saída que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="77532-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="77532-278">No PowerShell, você modifica as configurações da política de filtro de spam de saída e a regra de filtro de spam de saída separadamente.</span><span class="sxs-lookup"><span data-stu-id="77532-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="77532-279">Quando você remove uma política de filtro de spam de saída do PowerShell, a regra de filtro de spam de saída correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="77532-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="77532-280">Usar o PowerShell para criar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="77532-281">A criação de uma política de spam de saída no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="77532-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="77532-282">Criar a política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="77532-283">Crie a regra de filtro de spam de saída que especifica a política de filtro de spam de saída à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="77532-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="77532-284">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="77532-284">**Notes**:</span></span>

- <span data-ttu-id="77532-285">Você pode criar uma nova regra de filtro de spam de saída e atribuir uma diretiva de filtro de spam de saída não associada existente a ela.</span><span class="sxs-lookup"><span data-stu-id="77532-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="77532-286">Uma regra de filtro de spam de saída não pode ser associada a mais de uma política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="77532-287">Você pode definir as seguintes configurações em novas políticas de filtro de spam de saída no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="77532-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="77532-288">Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="77532-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="77532-289">Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="77532-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="77532-290">Uma nova política de filtro de spam de saída que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="77532-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="77532-291">Etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="77532-292">Para criar uma política de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="77532-293">Este exemplo cria uma nova política de filtro de spam de saída chamada contoso executivos com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="77532-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="77532-294">Os limites de taxa de destinatários são restritos a valores menores que o padrão.</span><span class="sxs-lookup"><span data-stu-id="77532-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="77532-295">Para obter mais informações, consulte [enviando limites nas opções do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="77532-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="77532-296">Depois que um dos limites é alcançado, o usuário é impedido de enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="77532-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="77532-297">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="77532-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="77532-298">Etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="77532-299">Para criar uma regra de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="77532-300">Este exemplo cria uma nova regra de filtro de spam de saída chamada contoso executivos com estas configurações:</span><span class="sxs-lookup"><span data-stu-id="77532-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="77532-301">A política de filtro de spam de saída chamada contoso executivos está associada à regra.</span><span class="sxs-lookup"><span data-stu-id="77532-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="77532-302">A regra se aplica aos membros do grupo chamado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="77532-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="77532-303">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="77532-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="77532-304">Usar o PowerShell para exibir políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="77532-305">Para retornar uma lista resumida de todas as políticas de filtro de spam de saída, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="77532-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="77532-306">Para retornar informações detalhadas sobre uma política de filtro de spam de saída específica, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="77532-307">Este exemplo retorna todos os valores de propriedade da política de filtro de spam de saída chamada executivos.</span><span class="sxs-lookup"><span data-stu-id="77532-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="77532-308">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="77532-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="77532-309">Usar o PowerShell para exibir regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="77532-310">Para exibir as regras de filtro de spam de saída existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="77532-311">Para retornar uma lista resumida de todas as regras de filtro de spam de saída, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="77532-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="77532-312">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="77532-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="77532-313">Para retornar informações detalhadas sobre uma regra de filtro de spam de saída específica, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="77532-314">Este exemplo retorna todos os valores de propriedade da regra de filtro de spam de saída chamada contoso executivos.</span><span class="sxs-lookup"><span data-stu-id="77532-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="77532-315">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="77532-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="77532-316">Usar o PowerShell para modificar as políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="77532-317">As mesmas configurações estão disponíveis quando você modifica uma política de filtro de malware no PowerShell quando cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="77532-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="77532-318">Não é possível renomear uma política de filtro de spam de saída (o cmdlet **set-HostedOutboundSpamFilterPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="77532-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="77532-319">Ao renomear uma política de spam de saída no centro de conformidade & segurança, você estará apenas renomeando a _regra_de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="77532-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="77532-320">Para modificar uma política de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="77532-321">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="77532-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="77532-322">Usar o PowerShell para modificar as regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="77532-323">A única configuração que não está disponível quando você modifica uma regra de filtro de spam de saída no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="77532-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="77532-324">Para habilitar ou desabilitar regras de filtro de spam de saída existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="77532-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="77532-325">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra de filtro de spam de saída no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77532-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="77532-326">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="77532-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="77532-327">Para modificar uma regra de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="77532-328">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="77532-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="77532-329">Usar o PowerShell para habilitar ou desabilitar as regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="77532-330">Habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell habilita ou desabilita toda a política de spam de saída (a regra de filtro de spam de saída e a política de filtro de spam de saída atribuída).</span><span class="sxs-lookup"><span data-stu-id="77532-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="77532-331">Você não pode habilitar ou desabilitar a política de spam de saída padrão (sempre é sempre aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="77532-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="77532-332">Para habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="77532-333">Este exemplo desabilita a regra de filtro de spam de saída chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="77532-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="77532-334">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="77532-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="77532-335">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="77532-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="77532-336">Usar o PowerShell para definir a prioridade das regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="77532-337">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="77532-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="77532-338">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="77532-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="77532-339">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="77532-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="77532-340">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="77532-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="77532-341">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="77532-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="77532-342">Para definir a prioridade de uma regra de filtro de spam de saída no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="77532-343">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="77532-343">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="77532-344">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="77532-344">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="77532-345">Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="77532-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="77532-346">A política de filtro de spam padrão de saída não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="77532-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="77532-347">Usar o PowerShell para remover as políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="77532-348">Quando você usa o PowerShell para remover uma política de filtro de spam de saída, a regra de filtro de spam de saída correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="77532-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="77532-349">Para remover uma política de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="77532-350">Este exemplo remove a política de filtro de spam de saída chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="77532-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="77532-351">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="77532-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="77532-352">Usar o PowerShell para remover as regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="77532-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="77532-353">Quando você usa o PowerShell para remover uma regra de filtro de spam de saída, a política de filtro de spam de saída correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="77532-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="77532-354">Para remover uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77532-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="77532-355">Este exemplo remove a regra de filtro de spam de saída chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="77532-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="77532-356">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="77532-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="77532-357">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="77532-357">For more information</span></span>

[<span data-ttu-id="77532-358">Remover usuários bloqueados do portal Usuários restritos</span><span class="sxs-lookup"><span data-stu-id="77532-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="77532-359">Pool de entrega de alto risco para mensagens de saída</span><span class="sxs-lookup"><span data-stu-id="77532-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="77532-360">Perguntas frequentes sobre a proteção antispam</span><span class="sxs-lookup"><span data-stu-id="77532-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="77532-361">Relatório de encaminhamento automático de mensagens</span><span class="sxs-lookup"><span data-stu-id="77532-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
