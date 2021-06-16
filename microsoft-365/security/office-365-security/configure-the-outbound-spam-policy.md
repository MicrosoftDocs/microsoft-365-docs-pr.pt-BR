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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de spam de saída no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9dadea740267225ff2df316b96ba7ccef92fe01e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933126"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="e65a4-103">Configurar a filtragem de spam de saída no EOP</span><span class="sxs-lookup"><span data-stu-id="e65a4-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e65a4-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e65a4-104">**Applies to**</span></span>
- [<span data-ttu-id="e65a4-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e65a4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e65a4-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e65a4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e65a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e65a4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e65a4-108">Em organizações Microsoft 365 com caixas de correio no Exchange Online ou organizações de Proteção do Exchange Online (EOP) autônomas sem caixas de correio Exchange Online, as mensagens de email de saída enviadas por meio do EOP são verificadas automaticamente para spam e atividades de envio incomuns.</span><span class="sxs-lookup"><span data-stu-id="e65a4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="e65a4-109">Spam de saída de um usuário em sua organização normalmente indica uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="e65a4-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="e65a4-110">As mensagens de saída suspeitas são marcadas como spam (independentemente do nível de confiança de spam ou SCL) e são roteadas pelo [pool](high-risk-delivery-pool-for-outbound-messages.md) de entrega de alto risco para ajudar a proteger a reputação do serviço (ou seja, Microsoft 365 manter os servidores de email de origem fora das listas de bloqueios de IP).</span><span class="sxs-lookup"><span data-stu-id="e65a4-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="e65a4-111">Os administradores são automaticamente notificados sobre atividades suspeitas de email de saída e os usuários bloqueados por meio de políticas [de alerta.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e65a4-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="e65a4-112">O EOP usa políticas de spam de saída como parte da defesa geral da sua organização contra spam.</span><span class="sxs-lookup"><span data-stu-id="e65a4-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="e65a4-113">Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e65a4-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="e65a4-114">Os administradores podem exibir, editar e configurar (mas não excluir) a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="e65a4-115">Para maior granularidade, você também pode criar políticas de spam de saída personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e65a4-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="e65a4-116">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e65a4-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="e65a4-117">Você pode configurar políticas de spam de saída no portal do Microsoft 365 Microsoft 365 Defender ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="e65a4-117">You can configure outbound spam policies in the Microsoft 365 Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="e65a4-118">Os elementos básicos de uma política de spam de saída no EOP são:</span><span class="sxs-lookup"><span data-stu-id="e65a4-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="e65a4-119">**A política de filtro de spam de** saída : especifica as ações para vereditos de filtragem de spam de saída e as opções de notificação.</span><span class="sxs-lookup"><span data-stu-id="e65a4-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="e65a4-120">**A regra de filtro de spam** de saída : especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="e65a4-121">A diferença entre esses dois elementos não é óbvia quando você gerencia as polícias de spam de saída no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="e65a4-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="e65a4-122">Ao criar uma política, você está realmente criando uma regra de filtro de spam de saída e a política de filtro de spam de saída associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="e65a4-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e65a4-123">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="e65a4-124">Todas as outras configurações modificam a política de filtro de spam de saída associada.</span><span class="sxs-lookup"><span data-stu-id="e65a4-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="e65a4-125">Quando você remove uma política, a regra de filtro de spam de saída e a política de filtro de spam de saída associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="e65a4-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="e65a4-126">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="e65a4-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e65a4-127">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) autônomo para configurar políticas de spam de saída posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e65a4-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="e65a4-128">Cada organização tem uma política de spam de saída interna chamada Default que tem essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="e65a4-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="e65a4-129">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de filtro de spam de saída (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="e65a4-130">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="e65a4-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="e65a4-131">As políticas personalizadas que você cria têm sempre uma prioridade mais alta do que a política denominada Padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="e65a4-132">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="e65a4-133">Para aumentar a eficácia da filtragem de spam de saída, você pode criar políticas de spam de saída personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="e65a4-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e65a4-134">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="e65a4-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e65a4-135">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="e65a4-135">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="e65a4-136">Para ir diretamente à página de **Configurações antispam**, use <https://security.microsoft.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="e65a4-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="e65a4-137">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e65a4-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e65a4-138">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e65a4-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e65a4-139">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="e65a4-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e65a4-140">Para adicionar, modificar e excluir políticas de spam de saída, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="e65a4-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e65a4-141">Para acesso somente leitura a políticas de spam de saída, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="e65a4-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e65a4-142">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e65a4-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e65a4-143">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="e65a4-143">**Notes**:</span></span>

  - <span data-ttu-id="e65a4-144">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e65a4-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e65a4-145">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e65a4-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e65a4-146">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="e65a4-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e65a4-147">Para nossas configurações recomendadas para políticas de spam de saída, consulte Configurações de política de filtro de spam de saída do [EOP](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="e65a4-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="e65a4-148">As [](../../compliance/alert-policies.md) políticas de alerta padrão denominadas Limite de envio  de email excederam **,** padrões suspeitos de envio de email detectados **e** o Usuário impedido de enviar emails já envia notificações de email para membros do grupo **TenantAdmins** ( Administradores globais ) sobre atividade de email de saída incomum e usuários **bloqueados** devido ao spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="e65a4-149">Para obter mais informações, [consulte Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="e65a4-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="e65a4-150">Recomendamos que você use essas políticas de alerta em vez das opções de notificação em políticas de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a><span data-ttu-id="e65a4-151">Usar o portal Microsoft 365 Defender para criar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-151">Use the Microsoft 365 Defender portal to create outbound spam policies</span></span>

<span data-ttu-id="e65a4-152">A criação de uma política de spam de saída personalizada no portal Microsoft 365 Defender cria a regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="e65a4-152">Creating a custom outbound spam policy in the Microsoft 365 Defender portal creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="e65a4-153">No Microsoft 365 Defender, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **Políticas** seção \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-153">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e65a4-154">Na página **Políticas anti-spam,** clique em Criar ícone Criar política e ![ selecione ](../../media/m365-cc-sc-create-icon.png)  **Saída** na listada.</span><span class="sxs-lookup"><span data-stu-id="e65a4-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="e65a4-155">O assistente de política é aberto.</span><span class="sxs-lookup"><span data-stu-id="e65a4-155">The policy wizard opens.</span></span> <span data-ttu-id="e65a4-156">Na **página Nomear política**, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e65a4-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="e65a4-157">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="e65a4-158">**Descrição**: insira uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e65a4-159">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e65a4-160">Na página **Usuários, grupos e domínios** exibida, identifique os destinatários internos aos quais a política se aplica (condições do destinatário):</span><span class="sxs-lookup"><span data-stu-id="e65a4-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="e65a4-161">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="e65a4-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e65a4-162">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="e65a4-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="e65a4-163">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="e65a4-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="e65a4-164">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="e65a4-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="e65a4-165">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="e65a4-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="e65a4-166">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="e65a4-166">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e65a4-168">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="e65a4-168">next to the value.</span></span>

   <span data-ttu-id="e65a4-169">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="e65a4-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="e65a4-170">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e65a4-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="e65a4-171">Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e65a4-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e65a4-172">Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e65a4-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="e65a4-173">**Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="e65a4-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="e65a4-174">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="e65a4-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e65a4-175">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e65a4-176">Na página **Configurações de Proteção** que é aberta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e65a4-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="e65a4-177">**Limites de mensagem**: As configurações desta seção configuram os limites para mensagens de email de saída **de** Exchange Online caixas de correio:</span><span class="sxs-lookup"><span data-stu-id="e65a4-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="e65a4-178">**Definir um limite de mensagem externo:** o número máximo de destinatários externos por hora.</span><span class="sxs-lookup"><span data-stu-id="e65a4-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="e65a4-179">**Definir um limite de mensagem interno**: O número máximo de destinatários internos por hora.</span><span class="sxs-lookup"><span data-stu-id="e65a4-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="e65a4-180">**Definir um limite diário de mensagem:** O número total máximo de destinatários por dia.</span><span class="sxs-lookup"><span data-stu-id="e65a4-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="e65a4-181">Um valor válido é de 0 a 10.000.</span><span class="sxs-lookup"><span data-stu-id="e65a4-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="e65a4-182">O valor padrão é 0, o que significa que os padrões de serviço são usados.</span><span class="sxs-lookup"><span data-stu-id="e65a4-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="e65a4-183">Para obter mais informações, consulte [Enviando limites](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="e65a4-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="e65a4-184">Insira um valor na caixa ou use as setas de aumento/diminuição na caixa.</span><span class="sxs-lookup"><span data-stu-id="e65a4-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="e65a4-185">**Restrição colocada em usuários que** atingem o limite de mensagens : Selecione uma ação na listada quando qualquer um dos limites na seção Configurações de Proteção for **excedido.**</span><span class="sxs-lookup"><span data-stu-id="e65a4-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="e65a4-186">Para todas as ações, os  destinatários especificados na política de alerta de email restritos ao usuário (e agora redundantes Notificar esses usuários e grupos se um remetente estiver bloqueado devido ao envio da configuração de **spam** de saída mais adiante nesta página) receberão notificações de email.</span><span class="sxs-lookup"><span data-stu-id="e65a4-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="e65a4-187">**Restringir o usuário de enviar emails até o dia seguinte:** esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="e65a4-188">As notificações por email são enviadas e o usuário não poderá enviar mais mensagens até o dia seguinte, com base no horário UTC.</span><span class="sxs-lookup"><span data-stu-id="e65a4-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="e65a4-189">Não há como o administrador substituir esse bloco.</span><span class="sxs-lookup"><span data-stu-id="e65a4-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="e65a4-190">O alerta de atividade denominado **Usuário impedido de enviar emails** notifica os administradores (por email e na página Exibir **alertas).**</span><span class="sxs-lookup"><span data-stu-id="e65a4-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="e65a4-191">Todos os destinatários especificados na notificação de pessoas específicas se um remetente for bloqueado devido ao envio de **configuração** de spam de saída na política também serão notificados.</span><span class="sxs-lookup"><span data-stu-id="e65a4-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="e65a4-192">O usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC.</span><span class="sxs-lookup"><span data-stu-id="e65a4-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="e65a4-193">Não há como o administrador substituir esse bloco.</span><span class="sxs-lookup"><span data-stu-id="e65a4-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="e65a4-194">Restringir o usuário de enviar emails **:** as notificações  de email são enviadas, o usuário é adicionado a usuários restritos no portal do Microsoft 365 Defender e o usuário não pode enviar emails até que eles sejam removidos de usuários restritos por um <https://security.microsoft.com/restrictedusers> administrador.  Depois que um administrador remover o usuário da lista, o usuário não será restrito novamente para esse dia.</span><span class="sxs-lookup"><span data-stu-id="e65a4-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the Microsoft 365 Defender portal, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="e65a4-195">Para obter instruções, [consulte Removendo um usuário do portal Usuários Restritos depois de enviar emails de spam](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="e65a4-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="e65a4-196">**Nenhuma ação, alerta somente**: As notificações de email são enviadas.</span><span class="sxs-lookup"><span data-stu-id="e65a4-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="e65a4-197">**Regras de encaminhamento**: Use as configurações desta seção para controlar o encaminhamento automático de email por meio Exchange Online **caixas** de correio para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="e65a4-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="e65a4-198">Para obter mais informações, consulte [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="e65a4-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="e65a4-199">Quando o encaminhamento automático estiver desabilitado, o destinatário receberá um relatório de não entrega (também conhecido como NDR ou mensagem de rejeição) se os destinatários externos enviarem emails para uma caixa de correio que tenha encaminhamento no local.</span><span class="sxs-lookup"><span data-stu-id="e65a4-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="e65a4-200">Se a mensagem for enviada  por um remetente interno e o método de encaminhamento for encaminhamento de caixa de correio [(também](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) conhecido como encaminhamento _SMTP),_ o remetente interno receberá a NDR.</span><span class="sxs-lookup"><span data-stu-id="e65a4-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="e65a4-201">O remetente interno não obterá uma NOTR se o encaminhamento ocorreu devido a uma regra de caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="e65a4-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="e65a4-202">Selecione uma das seguintes ações na lista de listadas de regras **de** encaminhamento automático:</span><span class="sxs-lookup"><span data-stu-id="e65a4-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="e65a4-203">**Automático - Controlado pelo sistema**: Permite a filtragem de spam de saída para controlar o encaminhamento automático de email externo.</span><span class="sxs-lookup"><span data-stu-id="e65a4-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="e65a4-204">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-204">This is the default value.</span></span>
     - <span data-ttu-id="e65a4-205">**On**: O encaminhamento automático de email externo não está desabilitado pela política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="e65a4-206">**Desativado**: Todo o encaminhamento automático de email externo está desabilitado pela política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="e65a4-207">**Notificações**: Use as configurações da seção para configurar destinatários adicionais que devem receber cópias e notificações de mensagens de email de saída suspeitas:</span><span class="sxs-lookup"><span data-stu-id="e65a4-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="e65a4-208">**Enviar uma cópia de** saída suspeita que exceda esses limites a esses usuários e grupos : Essa configuração adiciona os destinatários especificados ao campo Cc de mensagens de saída suspeitas.</span><span class="sxs-lookup"><span data-stu-id="e65a4-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="e65a4-209">Essa configuração só funciona na política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="e65a4-210">Ele não funciona em políticas de spam de saída personalizadas que você cria.</span><span class="sxs-lookup"><span data-stu-id="e65a4-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="e65a4-211">Para habilitar essa configuração, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="e65a4-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="e65a4-212">Na caixa exibida, clique na caixa, insira um endereço de email válido e pressione Enter ou selecione o valor completo exibido abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="e65a4-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="e65a4-213">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="e65a4-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="e65a4-214">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="e65a4-214">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="e65a4-216">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="e65a4-216">next to the value.</span></span>

   - <span data-ttu-id="e65a4-217">**Notificar esses usuários e grupos se um remetente estiver bloqueado devido ao envio de spam de saída**</span><span class="sxs-lookup"><span data-stu-id="e65a4-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="e65a4-218">Essa configuração está em processo de preterido das políticas de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="e65a4-219">A [política](../../compliance/alert-policies.md) de alerta padrão denominada Usuário restrito ao envio de **emails** já envia notificações por email aos membros do grupo  **TenantAdmins** (**Administradores** globais ) quando os usuários são bloqueados devido a exceder os limites na seção Limites do Destinatário.</span><span class="sxs-lookup"><span data-stu-id="e65a4-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="e65a4-220">Recomendamos que você use a política de alerta em vez dessa configuração na política de spam de saída para notificar **administradores e outros usuários.**</span><span class="sxs-lookup"><span data-stu-id="e65a4-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="e65a4-221">Para obter instruções, [consulte Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="e65a4-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="e65a4-222">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e65a4-223">Na página **Revisão** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="e65a4-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="e65a4-224">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="e65a4-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e65a4-225">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="e65a4-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="e65a4-226">Quando terminar, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="e65a4-227">Na mensagem de confirmação exibida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a><span data-ttu-id="e65a4-228">Usar o portal Microsoft 365 Defender para exibir políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-228">Use the Microsoft 365 Defender portal to view outbound spam policies</span></span>

1. <span data-ttu-id="e65a4-229">No Microsoft 365 Defender, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **Políticas** seção \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-229">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e65a4-230">Na página **Políticas anti-spam**, procure um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e65a4-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="e65a4-231">O **valor Type** é Política de spam de saída **personalizada**</span><span class="sxs-lookup"><span data-stu-id="e65a4-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="e65a4-232">O **valor Name** é Política de saída **anti-spam (Padrão)**</span><span class="sxs-lookup"><span data-stu-id="e65a4-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="e65a4-233">As propriedades a seguir são exibidas na lista de políticas antispam:</span><span class="sxs-lookup"><span data-stu-id="e65a4-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="e65a4-234">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e65a4-234">**Name**</span></span>
   - <span data-ttu-id="e65a4-235">**Status**</span><span class="sxs-lookup"><span data-stu-id="e65a4-235">**Status**</span></span>
   - <span data-ttu-id="e65a4-236">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="e65a4-236">**Priority**</span></span>
   - <span data-ttu-id="e65a4-237">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e65a4-237">**Type**</span></span>

3. <span data-ttu-id="e65a4-238">Quando você seleciona uma política de spam de saída clicando no nome, as configurações de política são exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="e65a4-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a><span data-ttu-id="e65a4-239">Usar o portal Microsoft 365 Defender para modificar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-239">Use the Microsoft 365 Defender portal to modify outbound spam policies</span></span>

1. <span data-ttu-id="e65a4-240">No Microsoft 365 Defender, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **Políticas** seção \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-240">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e65a4-241">Na página **Políticas anti-spam,** selecione uma política de spam de saída na lista clicando no nome:</span><span class="sxs-lookup"><span data-stu-id="e65a4-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="e65a4-242">Uma política personalizada criada onde o valor na coluna **Tipo** é Política de spam de **saída personalizada.**</span><span class="sxs-lookup"><span data-stu-id="e65a4-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="e65a4-243">A política padrão denominada **Política de saída anti-spam (Padrão)**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="e65a4-244">No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="e65a4-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="e65a4-245">Para obter mais informações sobre as configurações, consulte a seção [anterior Usar](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) o portal Microsoft 365 Defender para criar políticas de spam de saída neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e65a4-245">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create outbound spam policies](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="e65a4-246">Para a política de spam de saída padrão, a seção **Aplicado** a não está disponível (a política se aplica a todos) e você não pode renomear a política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="e65a4-247">Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="e65a4-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="e65a4-248">Habilitar ou desabilitar políticas de spam de saída personalizadas</span><span class="sxs-lookup"><span data-stu-id="e65a4-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="e65a4-249">Não é possível desabilitar a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="e65a4-250">No Microsoft 365 Defender, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **Políticas** seção \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-250">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e65a4-251">Na página **Políticas anti-spam,** selecione uma política com o valor **Tipo** da política de **spam** de saída personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="e65a4-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e65a4-252">Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e65a4-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="e65a4-253">**Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .</span><span class="sxs-lookup"><span data-stu-id="e65a4-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="e65a4-254">**Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="e65a4-255">Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="e65a4-256">Clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="e65a4-257">De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="e65a4-258">Definir a prioridade de políticas de spam de saída personalizadas</span><span class="sxs-lookup"><span data-stu-id="e65a4-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="e65a4-259">Por padrão, as políticas de spam de saída têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="e65a4-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="e65a4-260">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="e65a4-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e65a4-261">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="e65a4-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e65a4-262">Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="e65a4-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="e65a4-263">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="e65a4-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="e65a4-264">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="e65a4-264">**Notes**:</span></span>

- <span data-ttu-id="e65a4-265">No portal Microsoft 365 Defender, você só pode alterar a prioridade da política de spam de saída após a criação.</span><span class="sxs-lookup"><span data-stu-id="e65a4-265">In the Microsoft 365 Defender portal, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="e65a4-266">No PowerShell, é possível substituir a prioridade padrão ao criar a regra de filtro de spam (o que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="e65a4-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="e65a4-267">As políticas de spam de saída são processadas na ordem em que são exibidas (a primeira política tem o **valor priority** 0).</span><span class="sxs-lookup"><span data-stu-id="e65a4-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="e65a4-268">A política de spam de saída padrão tem o valor de prioridade **Mais** Baixo e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="e65a4-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="e65a4-269">No Microsoft 365 Defender, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **Políticas** seção \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-269">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e65a4-270">Na página **Políticas anti-spam,** selecione uma  política de seleção com o valor Tipo da política de **spam** de saída personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="e65a4-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="e65a4-271">Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="e65a4-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="e65a4-272">A política de spam de saída com **o valor Prioridade** **0** tem apenas a **opção Diminuir** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="e65a4-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="e65a4-273">A política de spam de saída com o menor valor **priority** (por exemplo, **3**) tem apenas a **opção Aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="e65a4-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="e65a4-274">Se você tiver três ou mais políticas de spam de saída, as políticas entre os valores de prioridade mais alta e mais baixa terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e65a4-274">If you have three or more outbound spam policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="e65a4-275">Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="e65a4-276">Quando terminar, clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="e65a4-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="e65a4-277">Use o portal Microsoft 365 Defender para remover políticas de spam de saída personalizadas</span><span class="sxs-lookup"><span data-stu-id="e65a4-277">Use the Microsoft 365 Defender portal to remove custom outbound spam policies</span></span>

<span data-ttu-id="e65a4-278">Quando você usa o portal Microsoft 365 Defender para remover uma política de spam de saída personalizada, a regra de filtro de spam e a política de filtro de spam correspondente são excluídas.</span><span class="sxs-lookup"><span data-stu-id="e65a4-278">When you use the Microsoft 365 Defender portal to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="e65a4-279">Não é possível remover a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="e65a4-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="e65a4-280">No Microsoft 365 Defender, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **Políticas** seção \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-280">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e65a4-281">Na página **Políticas anti-spam,** selecione uma política com o valor **Tipo** da política de **spam** de saída personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="e65a4-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="e65a4-282">Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="e65a4-283">Na caixa de diálogo de confirmação exibida, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="e65a4-284">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="e65a4-285">Conforme descrito anteriormente, uma política de spam de saída consiste em uma política de filtro de spam de saída e uma regra de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="e65a4-286">No Exchange Online PowerShell ou no EOP PowerShell autônomo, a diferença entre políticas de filtro de spam de saída e regras de filtro de spam de saída é aparente.</span><span class="sxs-lookup"><span data-stu-id="e65a4-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="e65a4-287">Você gerencia políticas de filtro de spam de saída usando os cmdlets **\* -HostedOutboundSpamFilterPolicy** e gerencia as regras de filtro de spam de saída usando os cmdlets **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="e65a4-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="e65a4-288">No PowerShell, primeiro você cria a política de filtro de spam de saída e, em seguida, cria a regra de filtro de spam de saída que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="e65a4-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e65a4-289">No PowerShell, você modifica as configurações na política de filtro de spam de saída e na regra de filtro de spam de saída separadamente.</span><span class="sxs-lookup"><span data-stu-id="e65a4-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="e65a4-290">Quando você remove uma política de filtro de spam de saída do PowerShell, a regra de filtro de spam de saída correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e65a4-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="e65a4-291">Usar o PowerShell para criar políticas de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="e65a4-292">Criar uma política de spam de saída no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="e65a4-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e65a4-293">Crie a política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="e65a4-294">Crie a regra de filtro de spam de saída que especifica a política de filtro de spam de saída à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="e65a4-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="e65a4-295">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="e65a4-295">**Notes**:</span></span>

   - <span data-ttu-id="e65a4-296">Você pode criar uma nova regra de filtro de spam de saída e atribuir uma política de filtro de spam de saída existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="e65a4-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="e65a4-297">Uma regra de filtro de spam de saída não pode ser associada a mais de uma política de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="e65a4-298">Você pode definir as seguintes configurações em novas políticas de filtro de spam de saída no PowerShell que não estão disponíveis no portal do Microsoft 365 Defender até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="e65a4-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
     - <span data-ttu-id="e65a4-299">Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="e65a4-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="e65a4-300">Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="e65a4-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="e65a4-301">Uma nova política de filtro de spam de saída que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra de filtro de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="e65a4-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="e65a4-302">Etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="e65a4-303">Para criar uma política de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="e65a4-304">Este exemplo cria uma nova política de filtro de spam de saída chamada Contoso Executives com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e65a4-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="e65a4-305">Os limites de taxa de destinatário são restritos a valores menores que os padrões.</span><span class="sxs-lookup"><span data-stu-id="e65a4-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="e65a4-306">Para obter mais informações, consulte [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="e65a4-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="e65a4-307">Depois que um dos limites é atingido, o usuário é impedido de enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="e65a4-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="e65a4-308">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="e65a4-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="e65a4-309">Etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="e65a4-310">Para criar uma regra de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="e65a4-311">Este exemplo cria uma nova regra de filtro de spam de saída chamada Contoso Executives com estas configurações:</span><span class="sxs-lookup"><span data-stu-id="e65a4-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="e65a4-312">A política de filtro de spam de saída chamada Contoso Executives está associada à regra.</span><span class="sxs-lookup"><span data-stu-id="e65a4-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="e65a4-313">A regra se aplica aos membros do grupo chamado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="e65a4-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="e65a4-314">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="e65a4-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="e65a4-315">Usar o PowerShell para exibir políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="e65a4-316">Para retornar uma lista resumida de todas as políticas de filtro de spam de saída, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="e65a4-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="e65a4-317">Para retornar informações detalhadas sobre uma política de filtro de spam de saída específica, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="e65a4-318">Este exemplo retorna todos os valores de propriedade da política de filtro de spam de saída chamada Executivos.</span><span class="sxs-lookup"><span data-stu-id="e65a4-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="e65a4-319">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="e65a4-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="e65a4-320">Usar o PowerShell para exibir regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="e65a4-321">Para exibir as regras de filtro de spam de saída existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="e65a4-322">Para retornar uma lista resumida de todas as regras de filtro de spam de saída, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="e65a4-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="e65a4-323">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e65a4-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="e65a4-324">Para retornar informações detalhadas sobre uma regra específica de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="e65a4-325">Este exemplo retorna todos os valores de propriedade da regra de filtro de spam de saída chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e65a4-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="e65a4-326">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="e65a4-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="e65a4-327">Usar o PowerShell para modificar políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="e65a4-328">As mesmas configurações estão disponíveis quando você modifica uma política de filtro de malware no PowerShell como quando você cria a política conforme descrito na Etapa [1: Use](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) o PowerShell para criar uma seção de política de filtro de spam de saída anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e65a4-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="e65a4-329">Não é possível renomear uma política de filtro de spam de saída (o cmdlet **Set-HostedOutboundSpamFilterPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="e65a4-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e65a4-330">Quando você renomeia uma política de spam de saída no portal do Microsoft 365 Defender, você só está renomeando a regra de filtro de spam de _saída._</span><span class="sxs-lookup"><span data-stu-id="e65a4-330">When you rename an outbound spam policy in the Microsoft 365 Defender portal, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="e65a4-331">Para modificar uma política de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e65a4-332">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="e65a4-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="e65a4-333">Usar o PowerShell para modificar regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="e65a4-334">A única configuração que não está disponível quando você modifica uma regra de filtro de spam de saída no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e65a4-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e65a4-335">Para habilitar ou desabilitar as regras de filtro de spam de saída existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="e65a4-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="e65a4-336">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra de filtro de spam de saída no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e65a4-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="e65a4-337">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) o PowerShell para criar uma seção de regra de filtro de spam de saída anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e65a4-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="e65a4-338">Para modificar uma regra de filtro de spam de saída, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e65a4-339">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="e65a4-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="e65a4-340">Usar o PowerShell para habilitar ou desabilitar regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="e65a4-341">Habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell habilita ou desabilita toda a política de spam de saída (a regra de filtro de spam de saída e a política de filtro de spam de saída atribuída).</span><span class="sxs-lookup"><span data-stu-id="e65a4-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="e65a4-342">Não é possível habilitar ou desabilitar a política de spam de saída padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="e65a4-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="e65a4-343">Para habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="e65a4-344">Este exemplo desabilita a regra de filtro de spam de saída chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="e65a4-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="e65a4-345">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="e65a4-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="e65a4-346">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="e65a4-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="e65a4-347">Usar o PowerShell para definir a prioridade das regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="e65a4-348">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="e65a4-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e65a4-349">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="e65a4-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e65a4-350">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="e65a4-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e65a4-351">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="e65a4-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e65a4-352">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="e65a4-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e65a4-353">Para definir a prioridade de uma regra de filtro de spam de saída no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e65a4-354">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="e65a4-354">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="e65a4-355">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="e65a4-355">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e65a4-356">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="e65a4-356">**Notes**:</span></span>

- <span data-ttu-id="e65a4-357">Para definir a prioridade de uma nova regra ao cria-la, use o parâmetro _Priority_ no cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="e65a4-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="e65a4-358">A política de filtro de spam padrão de saída não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade nãomodificável **Mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="e65a4-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="e65a4-359">Usar o PowerShell para remover políticas de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="e65a4-360">Quando você usa o PowerShell para remover uma política de filtro de spam de saída, a regra de filtro de spam de saída correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="e65a4-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="e65a4-361">Para remover uma política de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e65a4-362">Este exemplo remove a política de filtro de spam de saída chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="e65a4-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e65a4-363">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="e65a4-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="e65a4-364">Usar o PowerShell para remover regras de filtro de spam de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="e65a4-365">Quando você usa o PowerShell para remover uma regra de filtro de spam de saída, a política de filtro de spam de saída correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="e65a4-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="e65a4-366">Para remover uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e65a4-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="e65a4-367">Este exemplo remove a regra de filtro de spam de saída chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="e65a4-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="e65a4-368">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="e65a4-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e65a4-369">Para saber mais</span><span class="sxs-lookup"><span data-stu-id="e65a4-369">For more information</span></span>

[<span data-ttu-id="e65a4-370">Remover usuários bloqueados do portal Usuários Restritos</span><span class="sxs-lookup"><span data-stu-id="e65a4-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="e65a4-371">Pool de entrega de alto risco para mensagens de saída</span><span class="sxs-lookup"><span data-stu-id="e65a4-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="e65a4-372">Perguntas frequentes sobre a proteção antispam</span><span class="sxs-lookup"><span data-stu-id="e65a4-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="e65a4-373">Relatório de encaminhamento automático de mensagens</span><span class="sxs-lookup"><span data-stu-id="e65a4-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
