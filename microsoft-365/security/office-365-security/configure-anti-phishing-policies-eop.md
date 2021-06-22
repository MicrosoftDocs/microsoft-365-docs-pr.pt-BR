---
title: Configurar políticas anti-phishing em EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing disponíveis em organizações Proteção do Exchange Online (EOP) com ou sem Exchange Online caixas de correio.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8633644ab0380cf2adcf30c006a7d6d141a6040a
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054569"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="08d36-103">Configurar políticas anti-phishing em EOP</span><span class="sxs-lookup"><span data-stu-id="08d36-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="08d36-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="08d36-104">**Applies to**</span></span>
- [<span data-ttu-id="08d36-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08d36-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="08d36-106">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, há uma política anti-phishing padrão que contém um número limitado de recursos antifalsagem habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="08d36-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="08d36-107">Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="08d36-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="08d36-108">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="08d36-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="08d36-109">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="08d36-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="08d36-110">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="08d36-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="08d36-111">As organizações Exchange Online caixas de correio podem configurar políticas anti-phishing no portal Microsoft 365 Defender ou Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08d36-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="08d36-112">As organizações EOP autônomas só podem usar o portal Microsoft 365 Defender autônomo.</span><span class="sxs-lookup"><span data-stu-id="08d36-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="08d36-113">Para obter informações sobre como criar e modificar as políticas anti-phishing mais avançadas disponíveis no Microsoft Defender para Office 365, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="08d36-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

<span data-ttu-id="08d36-114">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="08d36-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="08d36-115">**A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.</span><span class="sxs-lookup"><span data-stu-id="08d36-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="08d36-116">**A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="08d36-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="08d36-117">A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="08d36-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="08d36-118">Ao criar uma política anti-phishing, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="08d36-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="08d36-119">Quando você modifica uma política anti-phishing, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="08d36-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="08d36-120">Todas as outras configurações modificam a política anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="08d36-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="08d36-121">Quando você remove uma política anti-phishing, a regra anti-phishing e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="08d36-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="08d36-122">No Exchange Online PowerShell, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="08d36-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="08d36-123">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell para configurar políticas [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="08d36-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="08d36-124">Cada organização tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="08d36-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="08d36-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="08d36-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="08d36-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="08d36-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="08d36-127">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="08d36-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="08d36-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="08d36-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="08d36-129">Para aumentar a eficácia da proteção anti-phishing, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="08d36-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="08d36-130">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="08d36-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="08d36-131">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="08d36-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="08d36-132">Para ir diretamente para a página **Anti-phishing,** use <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="08d36-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="08d36-133">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="08d36-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="08d36-134">Não é possível gerenciar políticas anti-phishing no EOP PowerShell autônomo.</span><span class="sxs-lookup"><span data-stu-id="08d36-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="08d36-135">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="08d36-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="08d36-136">Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="08d36-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="08d36-137">Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="08d36-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="08d36-138">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="08d36-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="08d36-139">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="08d36-139">**Notes**:</span></span>

  - <span data-ttu-id="08d36-140">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08d36-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="08d36-141">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="08d36-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="08d36-142">O **grupo de função Gerenciamento da Organização** Somente Exibição [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="08d36-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="08d36-143">Para nossas configurações recomendadas para políticas anti-phishing, consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="08d36-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="08d36-144">Permitir até 30 minutos para que a política atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="08d36-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="08d36-145">Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="08d36-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="08d36-146">Usar o portal Microsoft 365 Defender para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="08d36-147">Criar uma política anti-phishing personalizada no portal Microsoft 365 Defender cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="08d36-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="08d36-148">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="08d36-149">Na página **Anti-phishing,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="08d36-150">O assistente de política é aberto.</span><span class="sxs-lookup"><span data-stu-id="08d36-150">The policy wizard opens.</span></span> <span data-ttu-id="08d36-151">Na página **Nome da** política, configure estas configurações:</span><span class="sxs-lookup"><span data-stu-id="08d36-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="08d36-152">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="08d36-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="08d36-153">**Descrição**: insira uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="08d36-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="08d36-154">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="08d36-155">Na página **Usuários, grupos e domínios** exibida, identifique os destinatários internos aos quais a política se aplica (condições do destinatário):</span><span class="sxs-lookup"><span data-stu-id="08d36-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="08d36-156">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="08d36-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="08d36-157">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="08d36-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="08d36-158">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="08d36-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="08d36-159">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="08d36-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="08d36-160">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="08d36-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="08d36-161">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="08d36-161">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="08d36-163">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="08d36-163">next to the value.</span></span>

   <span data-ttu-id="08d36-164">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="08d36-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="08d36-165">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="08d36-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="08d36-166">Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="08d36-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="08d36-167">Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="08d36-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="08d36-168">**Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="08d36-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="08d36-169">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="08d36-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="08d36-170">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="08d36-171">Na página de proteção & de **phishing** exibida, use a caixa de seleção Habilitar inteligência de spoof para ativar ou desativar a inteligência de **spoof.**</span><span class="sxs-lookup"><span data-stu-id="08d36-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="08d36-172">O valor padrão está em (selecionado) e recomendamos que você o deixe em.</span><span class="sxs-lookup"><span data-stu-id="08d36-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="08d36-173">Você configura a ação a ser tomada em mensagens falsas bloqueadas na próxima página.</span><span class="sxs-lookup"><span data-stu-id="08d36-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="08d36-174">Para desativar a inteligência de spoof, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="08d36-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08d36-175">Você não precisa desativar a proteção anti-spoofing se seu registro MX não apontar para Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores.</span><span class="sxs-lookup"><span data-stu-id="08d36-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="08d36-176">Para obter instruções, [consulte Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="08d36-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="08d36-177">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="08d36-178">Na página **Ações** exibida, de acordo com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="08d36-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="08d36-179">**Se a mensagem for detectada como** falsa : essa configuração estará disponível somente se você tiver selecionado Habilitar a inteligência de **spoof** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="08d36-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="08d36-180">Selecione uma das seguintes ações na listada para mensagens de envios com spoofed bloqueados:</span><span class="sxs-lookup"><span data-stu-id="08d36-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="08d36-181">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="08d36-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="08d36-182">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="08d36-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="08d36-183">**Dicas de segurança &** indicadores : Essa configuração só estará disponível se você selecionou Habilitar a inteligência de **spoof** na página anterior:</span><span class="sxs-lookup"><span data-stu-id="08d36-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="08d36-184">**Mostrar (?)** para remetentes não autenticados para spoof : adiciona um ponto de interrogação à foto do remetente na caixa De em  Outlook se a mensagem não passar verificações SPF ou DKIM e a mensagem não passar DMARC [ou](email-validation-and-authentication.md#composite-authentication)autenticação composta .</span><span class="sxs-lookup"><span data-stu-id="08d36-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="08d36-185">Mostrar a marca **"via":** adiciona uma marca via (chris@contoso.com via fabrikam.com) ao endereço From se for diferente do domínio na assinatura DKIM ou no endereço **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="08d36-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

     <span data-ttu-id="08d36-186">Para ativar uma configuração, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="08d36-186">To turn on a setting, select the check box.</span></span> <span data-ttu-id="08d36-187">Para desativar, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="08d36-187">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="08d36-188">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-188">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="08d36-189">Na página **Revisão** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="08d36-189">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="08d36-190">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="08d36-190">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="08d36-191">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="08d36-191">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="08d36-192">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-192">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="08d36-193">Na mensagem de confirmação exibida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="08d36-193">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="08d36-194">Usar o portal Microsoft 365 Defender para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-194">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="08d36-195">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-195">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="08d36-196">Na página **Anti-phishing,** as seguintes propriedades são exibidas na lista de políticas:</span><span class="sxs-lookup"><span data-stu-id="08d36-196">On the **Anti-phishing** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="08d36-197">**Nome**</span><span class="sxs-lookup"><span data-stu-id="08d36-197">**Name**</span></span>
   - <span data-ttu-id="08d36-198">**Status**</span><span class="sxs-lookup"><span data-stu-id="08d36-198">**Status**</span></span>
   - <span data-ttu-id="08d36-199">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="08d36-199">**Priority**</span></span>
   - <span data-ttu-id="08d36-200">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="08d36-200">**Last modified**</span></span>

3. <span data-ttu-id="08d36-201">Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="08d36-201">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="08d36-202">Usar o portal Microsoft 365 Defender para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-202">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="08d36-203">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-203">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="08d36-204">Na página **Anti-phishing,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="08d36-204">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="08d36-205">No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="08d36-205">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="08d36-206">Para obter mais informações sobre as configurações, consulte a seção Usar o portal Microsoft 365 Defender para criar políticas [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="08d36-206">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="08d36-207">Para a política anti-phishing padrão, a seção Usuários, grupos e **domínios** não está disponível (a política se aplica a todos) e você não pode renomear a política.</span><span class="sxs-lookup"><span data-stu-id="08d36-207">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="08d36-208">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="08d36-208">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="08d36-209">Habilitar ou desabilitar políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="08d36-209">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="08d36-210">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="08d36-210">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="08d36-211">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-211">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="08d36-212">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="08d36-212">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="08d36-213">Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="08d36-213">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="08d36-214">**Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .</span><span class="sxs-lookup"><span data-stu-id="08d36-214">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="08d36-215">**Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-215">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="08d36-216">Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="08d36-216">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="08d36-217">Clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="08d36-217">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="08d36-218">De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="08d36-218">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="08d36-219">Definir a prioridade de políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="08d36-219">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="08d36-220">Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="08d36-220">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="08d36-221">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="08d36-221">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="08d36-222">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="08d36-222">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="08d36-223">Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="08d36-223">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="08d36-224">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="08d36-224">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="08d36-225">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="08d36-225">**Notes**:</span></span>

- <span data-ttu-id="08d36-226">No portal Microsoft 365 Defender, você só pode alterar a prioridade da política anti-phishing após a criação.</span><span class="sxs-lookup"><span data-stu-id="08d36-226">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="08d36-227">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="08d36-227">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="08d36-228">As políticas anti-phishing são processadas na ordem em que são exibidas (a primeira política tem o **valor priority** 0).</span><span class="sxs-lookup"><span data-stu-id="08d36-228">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="08d36-229">A política anti-phishing padrão tem o valor de prioridade **Mais** Baixo e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="08d36-229">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="08d36-230">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-230">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="08d36-231">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="08d36-231">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="08d36-232">Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="08d36-232">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="08d36-233">A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="08d36-233">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="08d36-234">A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="08d36-234">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="08d36-235">Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="08d36-235">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="08d36-236">Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="08d36-236">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="08d36-237">Quando terminar, clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="08d36-237">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="08d36-238">Usar o portal Microsoft 365 Defender para remover políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="08d36-238">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="08d36-239">Quando você usa o portal Microsoft 365 Defender para remover uma política anti-phishing personalizada, a regra anti-phishing e a política anti-phishing correspondente são excluídas.</span><span class="sxs-lookup"><span data-stu-id="08d36-239">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="08d36-240">Não é possível remover a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="08d36-240">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="08d36-241">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-241">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="08d36-242">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="08d36-242">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="08d36-243">Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="08d36-243">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="08d36-244">Na caixa de diálogo de confirmação exibida, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="08d36-244">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="08d36-245">Usar Exchange Online PowerShell para configurar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-245">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="08d36-246">Conforme descrito anteriormente, uma política anti-phishing consiste em uma política anti-phishing e uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="08d36-246">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="08d36-247">No Exchange Online PowerShell, a diferença entre políticas anti-phishing e regras anti-phishing é aparente.</span><span class="sxs-lookup"><span data-stu-id="08d36-247">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="08d36-248">Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="08d36-248">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="08d36-249">No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="08d36-249">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="08d36-250">No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.</span><span class="sxs-lookup"><span data-stu-id="08d36-250">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="08d36-251">Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="08d36-251">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="08d36-252">Os procedimentos a seguir do PowerShell não estão disponíveis em organizações EOP autônomas usando Proteção do Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08d36-252">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="08d36-253">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-253">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="08d36-254">Criar uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="08d36-254">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="08d36-255">Crie a política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="08d36-255">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="08d36-256">Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="08d36-256">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="08d36-257">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="08d36-257">**Notes**:</span></span>

- <span data-ttu-id="08d36-258">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="08d36-258">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="08d36-259">Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="08d36-259">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="08d36-260">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="08d36-260">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="08d36-261">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="08d36-261">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="08d36-262">De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="08d36-262">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="08d36-263">Uma nova política anti-phishing que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="08d36-263">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="08d36-264">Etapa 1: Usar o PowerShell para criar uma política anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-264">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="08d36-265">Para criar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-265">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="08d36-266">Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="08d36-266">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="08d36-267">A descrição é: Política do departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="08d36-267">The description is: Research department policy.</span></span>
- <span data-ttu-id="08d36-268">Altera a ação padrão para a spoofing para Quarentena.</span><span class="sxs-lookup"><span data-stu-id="08d36-268">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="08d36-269">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="08d36-269">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="08d36-270">Etapa 2: Usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-270">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="08d36-271">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-271">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="08d36-272">Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="08d36-272">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="08d36-273">A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="08d36-273">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="08d36-274">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="08d36-274">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="08d36-275">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="08d36-275">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="08d36-276">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="08d36-276">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="08d36-277">Usar o PowerShell para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-277">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="08d36-278">Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-278">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="08d36-279">Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="08d36-279">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="08d36-280">Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="08d36-280">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="08d36-281">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="08d36-281">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="08d36-282">Usar o PowerShell para exibir regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-282">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="08d36-283">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-283">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="08d36-284">Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="08d36-284">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="08d36-285">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="08d36-285">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="08d36-286">Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="08d36-286">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="08d36-287">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="08d36-287">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="08d36-288">Usar o PowerShell para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-288">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="08d36-289">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria uma política conforme descrito na Etapa 1: Use o PowerShell para criar uma política [anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="08d36-289">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="08d36-290">A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08d36-290">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="08d36-291">Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="08d36-291">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="08d36-292">Quando você renomeia uma política anti-phishing no portal Microsoft 365 Defender, você só está renomeando a regra _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="08d36-292">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="08d36-293">Para modificar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-293">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="08d36-294">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="08d36-294">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="08d36-295">Usar o PowerShell para modificar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-295">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="08d36-296">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="08d36-296">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="08d36-297">Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="08d36-297">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="08d36-298">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa 2: Usar o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="08d36-298">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="08d36-299">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-299">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="08d36-300">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="08d36-300">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="08d36-301">Usar o PowerShell para habilitar ou desabilitar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-301">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="08d36-302">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída).</span><span class="sxs-lookup"><span data-stu-id="08d36-302">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="08d36-303">Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="08d36-303">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="08d36-304">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-304">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="08d36-305">Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="08d36-305">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="08d36-306">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="08d36-306">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="08d36-307">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="08d36-307">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="08d36-308">Usar o PowerShell para definir a prioridade das regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-308">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="08d36-309">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="08d36-309">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="08d36-310">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="08d36-310">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="08d36-311">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="08d36-311">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="08d36-312">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="08d36-312">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="08d36-313">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="08d36-313">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="08d36-314">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-314">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="08d36-315">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="08d36-315">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="08d36-316">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="08d36-316">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="08d36-317">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="08d36-317">**Notes**:</span></span>

- <span data-ttu-id="08d36-318">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="08d36-318">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="08d36-319">A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.</span><span class="sxs-lookup"><span data-stu-id="08d36-319">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="08d36-320">Usar o PowerShell para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-320">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="08d36-321">Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="08d36-321">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="08d36-322">Para remover uma política anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-322">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="08d36-323">Este exemplo remove a política anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="08d36-323">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="08d36-324">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="08d36-324">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="08d36-325">Usar o PowerShell para remover regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="08d36-325">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="08d36-326">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="08d36-326">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="08d36-327">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="08d36-327">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="08d36-328">Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="08d36-328">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="08d36-329">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="08d36-329">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="08d36-330">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="08d36-330">How do you know these procedures worked?</span></span>

<span data-ttu-id="08d36-331">Para verificar se você configurou com êxito políticas anti-phishing no EOP, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="08d36-331">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="08d36-332">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="08d36-332">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="08d36-333">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="08d36-333">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="08d36-334">Para exibir mais detalhes, selecione a política na lista clicando no nome e exibindo os detalhes no sobremenu que aparece.</span><span class="sxs-lookup"><span data-stu-id="08d36-334">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="08d36-335">No Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="08d36-335">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
