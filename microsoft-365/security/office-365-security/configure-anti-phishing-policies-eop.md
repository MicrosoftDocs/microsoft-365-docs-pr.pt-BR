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
ms.openlocfilehash: 9cd006146d8ae41196b63c658ae54e875d730bcc
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932849"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="10e9f-103">Configurar políticas anti-phishing em EOP</span><span class="sxs-lookup"><span data-stu-id="10e9f-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="10e9f-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="10e9f-104">**Applies to**</span></span>
- [<span data-ttu-id="10e9f-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="10e9f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="10e9f-106">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, há uma política anti-phishing padrão que contém um número limitado de recursos antifalsagem habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="10e9f-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="10e9f-107">Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="10e9f-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="10e9f-108">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="10e9f-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="10e9f-109">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="10e9f-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="10e9f-110">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="10e9f-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="10e9f-111">As organizações Exchange Online caixas de correio podem configurar políticas anti-phishing no portal Microsoft 365 Defender ou Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10e9f-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="10e9f-112">As organizações EOP autônomas só podem usar o portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="10e9f-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="10e9f-113">Para obter informações sobre como criar e modificar as políticas anti-phishing mais avançadas disponíveis no Microsoft Defender para Office 365, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="10e9f-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="10e9f-114">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="10e9f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="10e9f-115">**A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.</span><span class="sxs-lookup"><span data-stu-id="10e9f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="10e9f-116">**A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="10e9f-117">A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="10e9f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="10e9f-118">Ao criar uma política anti-phishing, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="10e9f-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="10e9f-119">Quando você modifica uma política anti-phishing, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="10e9f-120">Todas as outras configurações modificam a política anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="10e9f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="10e9f-121">Quando você remove uma política anti-phishing, a regra anti-phishing e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="10e9f-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="10e9f-122">No Exchange Online PowerShell, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="10e9f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="10e9f-123">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell para configurar políticas [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="10e9f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="10e9f-124">Cada organização tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="10e9f-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="10e9f-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="10e9f-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="10e9f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="10e9f-127">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="10e9f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="10e9f-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="10e9f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="10e9f-129">Para aumentar a eficácia da proteção anti-phishing, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="10e9f-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="10e9f-130">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="10e9f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="10e9f-131">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="10e9f-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="10e9f-132">Para ir diretamente para a página **Anti-phishing,** use <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="10e9f-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="10e9f-133">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="10e9f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="10e9f-134">Não é possível gerenciar políticas anti-phishing no EOP PowerShell autônomo.</span><span class="sxs-lookup"><span data-stu-id="10e9f-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="10e9f-135">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="10e9f-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="10e9f-136">Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="10e9f-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="10e9f-137">Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="10e9f-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="10e9f-138">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="10e9f-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="10e9f-139">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="10e9f-139">**Notes**:</span></span>

  - <span data-ttu-id="10e9f-140">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10e9f-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="10e9f-141">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="10e9f-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="10e9f-142">O **grupo de função Gerenciamento da Organização** Somente Exibição [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="10e9f-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="10e9f-143">Para nossas configurações recomendadas para políticas anti-phishing, consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="10e9f-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="10e9f-144">Permitir até 30 minutos para que a política atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="10e9f-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="10e9f-145">Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="10e9f-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="10e9f-146">Usar o Microsoft 365 do Defender para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="10e9f-147">Criar uma política anti-phishing personalizada no portal do Microsoft 365 Defender cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="10e9f-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="10e9f-148">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="10e9f-149">Na página **Anti-phishing,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="10e9f-150">O assistente de política é aberto.</span><span class="sxs-lookup"><span data-stu-id="10e9f-150">The policy wizard opens.</span></span> <span data-ttu-id="10e9f-151">Na página **Nome da** política, configure estas configurações:</span><span class="sxs-lookup"><span data-stu-id="10e9f-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="10e9f-152">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="10e9f-153">**Descrição**: insira uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="10e9f-154">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="10e9f-155">Na página **Usuários, grupos e domínios** exibida, identifique os destinatários internos aos quais a política se aplica (condições do destinatário):</span><span class="sxs-lookup"><span data-stu-id="10e9f-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="10e9f-156">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="10e9f-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="10e9f-157">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="10e9f-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="10e9f-158">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="10e9f-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="10e9f-159">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="10e9f-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="10e9f-160">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="10e9f-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="10e9f-161">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="10e9f-161">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="10e9f-163">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="10e9f-163">next to the value.</span></span>

   <span data-ttu-id="10e9f-164">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="10e9f-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="10e9f-165">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="10e9f-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="10e9f-166">Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="10e9f-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="10e9f-167">Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="10e9f-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="10e9f-168">**Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="10e9f-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="10e9f-169">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="10e9f-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="10e9f-170">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="10e9f-171">Na página de proteção & de **phishing** exibida, use a caixa de seleção Habilitar inteligência de spoof para ativar ou desativar a inteligência de **spoof.**</span><span class="sxs-lookup"><span data-stu-id="10e9f-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="10e9f-172">O valor padrão está em (selecionado) e recomendamos que você o deixe em.</span><span class="sxs-lookup"><span data-stu-id="10e9f-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="10e9f-173">Você configura a ação a ser tomada em mensagens falsas bloqueadas na próxima página.</span><span class="sxs-lookup"><span data-stu-id="10e9f-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="10e9f-174">Para desativar a inteligência de spoof, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="10e9f-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="10e9f-175">Você não precisa desativar a proteção anti-spoofing se seu registro MX não apontar para Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores.</span><span class="sxs-lookup"><span data-stu-id="10e9f-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="10e9f-176">Para obter instruções, [consulte Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="10e9f-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="10e9f-177">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="10e9f-178">Na página **Ações** exibida, de acordo com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="10e9f-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="10e9f-179">**Se a mensagem for detectada como** falsa : essa configuração estará disponível somente se você tiver selecionado Habilitar a inteligência de **spoof** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="10e9f-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="10e9f-180">Selecione uma das seguintes ações na listada para mensagens de envios com spoofed bloqueados:</span><span class="sxs-lookup"><span data-stu-id="10e9f-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="10e9f-181">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="10e9f-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="10e9f-182">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="10e9f-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="10e9f-183">**Dicas de segurança &** indicadores : Essa configuração só estará disponível se você selecionou Habilitar a inteligência de **spoof** na página anterior:</span><span class="sxs-lookup"><span data-stu-id="10e9f-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="10e9f-184">**Mostrar (?)** para remetentes não autenticados para spoof : adiciona um ponto de interrogação à foto do remetente na caixa De em  Outlook se a mensagem não passar verificações SPF ou DKIM e a mensagem não passar DMARC [ou](email-validation-and-authentication.md#composite-authentication)autenticação composta .</span><span class="sxs-lookup"><span data-stu-id="10e9f-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="10e9f-185">Mostrar a marca **"via":** adiciona uma marca via (chris@contoso.com via fabrikam.com) ao endereço From se for diferente do domínio na assinatura DKIM ou no endereço **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="10e9f-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="10e9f-186">Atualmente, a **configuração de marca Mostrar "via"** não está disponível em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="10e9f-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="10e9f-187">Se você não tiver a configuração de marca Mostrar  **"via",** o ponto de interrogação e a marca via serão controlados pela configuração **Mostrar (?)** para envios não autenticados para a configuração de spoof em sua organização.</span><span class="sxs-lookup"><span data-stu-id="10e9f-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="10e9f-188">Para ativar uma configuração, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="10e9f-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="10e9f-189">Para desativar, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="10e9f-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="10e9f-190">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="10e9f-191">Na página **Revisão** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="10e9f-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="10e9f-192">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="10e9f-192">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="10e9f-193">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="10e9f-193">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="10e9f-194">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-194">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="10e9f-195">Na mensagem de confirmação exibida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-195">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="10e9f-196">Usar o portal Microsoft 365 Defender para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-196">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="10e9f-197">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-197">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="10e9f-198">Na página **Anti-phishing,** as seguintes propriedades são exibidas na lista de políticas anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="10e9f-198">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="10e9f-199">**Nome**</span><span class="sxs-lookup"><span data-stu-id="10e9f-199">**Name**</span></span>
   - <span data-ttu-id="10e9f-200">**Status**</span><span class="sxs-lookup"><span data-stu-id="10e9f-200">**Status**</span></span>
   - <span data-ttu-id="10e9f-201">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="10e9f-201">**Priority**</span></span>
   - <span data-ttu-id="10e9f-202">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="10e9f-202">**Last modified**</span></span>

3. <span data-ttu-id="10e9f-203">Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="10e9f-203">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="10e9f-204">Usar o portal Microsoft 365 Defender para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-204">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="10e9f-205">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-205">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="10e9f-206">Na página **Anti-phishing,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="10e9f-206">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="10e9f-207">No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="10e9f-207">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="10e9f-208">Para obter mais informações sobre as configurações, consulte a seção Usar o portal Microsoft 365 Defender para criar políticas [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="10e9f-208">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="10e9f-209">Para a política anti-phishing padrão, a seção Usuários, grupos e **domínios** não está disponível (a política se aplica a todos) e você não pode renomear a política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-209">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="10e9f-210">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="10e9f-210">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="10e9f-211">Habilitar ou desabilitar políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="10e9f-211">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="10e9f-212">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="10e9f-212">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="10e9f-213">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-213">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="10e9f-214">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="10e9f-214">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="10e9f-215">Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="10e9f-215">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="10e9f-216">**Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .</span><span class="sxs-lookup"><span data-stu-id="10e9f-216">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="10e9f-217">**Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-217">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="10e9f-218">Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-218">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="10e9f-219">Clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-219">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="10e9f-220">De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-220">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="10e9f-221">Definir a prioridade de políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="10e9f-221">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="10e9f-222">Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="10e9f-222">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="10e9f-223">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="10e9f-223">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="10e9f-224">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="10e9f-224">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="10e9f-225">Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="10e9f-225">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="10e9f-226">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="10e9f-226">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="10e9f-227">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="10e9f-227">**Notes**:</span></span>

- <span data-ttu-id="10e9f-228">No portal Microsoft 365 Defender, você só pode alterar a prioridade da política anti-phishing após a criação.</span><span class="sxs-lookup"><span data-stu-id="10e9f-228">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="10e9f-229">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="10e9f-229">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="10e9f-230">As políticas anti-phishing são processadas na ordem em que são exibidas (a primeira política tem o **valor priority** 0).</span><span class="sxs-lookup"><span data-stu-id="10e9f-230">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="10e9f-231">A política anti-phishing padrão tem o valor de prioridade **Mais** Baixo e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="10e9f-231">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="10e9f-232">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-232">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="10e9f-233">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="10e9f-233">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="10e9f-234">Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="10e9f-234">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="10e9f-235">A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="10e9f-235">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="10e9f-236">A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="10e9f-236">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="10e9f-237">Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="10e9f-237">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="10e9f-238">Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-238">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="10e9f-239">Quando terminar, clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-239">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="10e9f-240">Usar o portal Microsoft 365 Defender para remover políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="10e9f-240">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="10e9f-241">Quando você usa o portal Microsoft 365 Defender para remover uma política anti-phishing personalizada, a regra anti-phishing e a política anti-phishing correspondente são excluídas.</span><span class="sxs-lookup"><span data-stu-id="10e9f-241">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="10e9f-242">Não é possível remover a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="10e9f-242">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="10e9f-243">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-243">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="10e9f-244">Selecione uma política personalizada na lista clicando no nome da política.</span><span class="sxs-lookup"><span data-stu-id="10e9f-244">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="10e9f-245">Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-245">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="10e9f-246">Na caixa de diálogo de confirmação exibida, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-246">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="10e9f-247">Usar Exchange Online PowerShell para configurar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-247">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="10e9f-248">Conforme descrito anteriormente, uma política anti-phishing consiste em uma política anti-phishing e uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-248">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="10e9f-249">No Exchange Online PowerShell, a diferença entre políticas anti-phishing e regras anti-phishing é aparente.</span><span class="sxs-lookup"><span data-stu-id="10e9f-249">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="10e9f-250">Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="10e9f-250">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="10e9f-251">No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="10e9f-251">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="10e9f-252">No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.</span><span class="sxs-lookup"><span data-stu-id="10e9f-252">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="10e9f-253">Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="10e9f-253">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="10e9f-254">Os procedimentos a seguir do PowerShell não estão disponíveis em organizações EOP autônomas usando Proteção do Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10e9f-254">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="10e9f-255">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-255">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="10e9f-256">Criar uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="10e9f-256">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="10e9f-257">Crie a política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-257">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="10e9f-258">Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="10e9f-258">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="10e9f-259">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="10e9f-259">**Notes**:</span></span>

- <span data-ttu-id="10e9f-260">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="10e9f-260">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="10e9f-261">Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-261">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="10e9f-262">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no portal do Microsoft 365 Defender até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="10e9f-262">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="10e9f-263">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="10e9f-263">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="10e9f-264">De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="10e9f-264">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="10e9f-265">Uma nova política anti-phishing que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-265">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="10e9f-266">Etapa 1: Usar o PowerShell para criar uma política anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-266">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="10e9f-267">Para criar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-267">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="10e9f-268">Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="10e9f-268">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="10e9f-269">A descrição é: Política do departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="10e9f-269">The description is: Research department policy.</span></span>
- <span data-ttu-id="10e9f-270">Altera a ação padrão para a spoofing para Quarentena.</span><span class="sxs-lookup"><span data-stu-id="10e9f-270">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="10e9f-271">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="10e9f-271">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="10e9f-272">Etapa 2: Usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-272">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="10e9f-273">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-273">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="10e9f-274">Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="10e9f-274">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="10e9f-275">A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="10e9f-275">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="10e9f-276">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="10e9f-276">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="10e9f-277">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="10e9f-277">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="10e9f-278">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="10e9f-278">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="10e9f-279">Usar o PowerShell para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-279">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="10e9f-280">Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-280">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="10e9f-281">Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="10e9f-281">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="10e9f-282">Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="10e9f-282">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="10e9f-283">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="10e9f-283">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="10e9f-284">Usar o PowerShell para exibir regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-284">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="10e9f-285">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-285">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="10e9f-286">Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="10e9f-286">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="10e9f-287">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="10e9f-287">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="10e9f-288">Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="10e9f-288">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="10e9f-289">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="10e9f-289">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="10e9f-290">Usar o PowerShell para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-290">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="10e9f-291">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria uma política conforme descrito na Etapa 1: Use o PowerShell para criar uma política [anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="10e9f-291">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="10e9f-292">A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10e9f-292">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="10e9f-293">Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="10e9f-293">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="10e9f-294">Ao renomear uma política anti-phishing no portal Microsoft 365 Defender, você está renomeando apenas a regra _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="10e9f-294">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="10e9f-295">Para modificar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-295">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="10e9f-296">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="10e9f-296">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="10e9f-297">Usar o PowerShell para modificar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-297">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="10e9f-298">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="10e9f-298">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="10e9f-299">Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="10e9f-299">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="10e9f-300">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa 2: Usar o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="10e9f-300">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="10e9f-301">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-301">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="10e9f-302">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="10e9f-302">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="10e9f-303">Usar o PowerShell para habilitar ou desabilitar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-303">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="10e9f-304">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída).</span><span class="sxs-lookup"><span data-stu-id="10e9f-304">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="10e9f-305">Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="10e9f-305">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="10e9f-306">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-306">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="10e9f-307">Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-307">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="10e9f-308">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="10e9f-308">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="10e9f-309">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="10e9f-309">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="10e9f-310">Usar o PowerShell para definir a prioridade das regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-310">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="10e9f-311">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="10e9f-311">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="10e9f-312">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="10e9f-312">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="10e9f-313">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="10e9f-313">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="10e9f-314">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="10e9f-314">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="10e9f-315">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="10e9f-315">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="10e9f-316">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-316">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="10e9f-317">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="10e9f-317">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="10e9f-318">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="10e9f-318">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="10e9f-319">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="10e9f-319">**Notes**:</span></span>

- <span data-ttu-id="10e9f-320">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="10e9f-320">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="10e9f-321">A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-321">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="10e9f-322">Usar o PowerShell para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-322">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="10e9f-323">Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="10e9f-323">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="10e9f-324">Para remover uma política anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-324">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="10e9f-325">Este exemplo remove a política anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-325">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="10e9f-326">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="10e9f-326">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="10e9f-327">Usar o PowerShell para remover regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="10e9f-327">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="10e9f-328">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="10e9f-328">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="10e9f-329">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="10e9f-329">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="10e9f-330">Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="10e9f-330">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="10e9f-331">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="10e9f-331">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="10e9f-332">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="10e9f-332">How do you know these procedures worked?</span></span>

<span data-ttu-id="10e9f-333">Para verificar se você configurou com êxito políticas anti-phishing no EOP, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="10e9f-333">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="10e9f-334">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="10e9f-334">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="10e9f-335">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="10e9f-335">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="10e9f-336">Para exibir mais detalhes, selecione a política na lista clicando no nome e exibindo os detalhes no sobremenu que aparece.</span><span class="sxs-lookup"><span data-stu-id="10e9f-336">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="10e9f-337">No Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="10e9f-337">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
