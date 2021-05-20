---
title: Configurar políticas anti-phishing no Microsoft Defender para Office 365
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
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing avançadas disponíveis em organizações com o Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3660b9574f4faf4ee9c0602ac23b36f8634650dc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537902"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-103">Configurar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61e42-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="61e42-104">**Applies to**</span></span>
- [<span data-ttu-id="61e42-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="61e42-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61e42-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="61e42-107">As políticas anti-phishing no [Microsoft Defender](defender-for-office-365.md) para Office 365 podem ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="61e42-108">Para obter mais informações sobre as diferenças entre políticas anti-phishing no Proteção do Exchange Online (EOP) e políticas anti-phishing no Microsoft Defender para Office 365, consulte [Proteção anti-phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="61e42-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="61e42-109">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="61e42-110">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="61e42-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="61e42-111">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="61e42-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="61e42-112">Você pode configurar políticas anti-phishing no Centro de Conformidade & Segurança ou Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61e42-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="61e42-113">Para obter informações sobre como configurar o mais limitado em políticas anti-phishing que estão disponíveis em organizações Proteção do Exchange Online (ou seja, organizações sem o Microsoft Defender para Office 365), consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="61e42-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="61e42-114">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="61e42-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="61e42-115">**A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.</span><span class="sxs-lookup"><span data-stu-id="61e42-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="61e42-116">**A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="61e42-117">A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="61e42-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="61e42-118">Ao criar uma política, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="61e42-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="61e42-119">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="61e42-120">Todas as outras configurações modificam a política anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="61e42-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="61e42-121">Quando você remove uma política, a regra anti-phishing e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="61e42-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="61e42-122">No Exchange Online PowerShell, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="61e42-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="61e42-123">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell para configurar políticas [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) no Microsoft Defender para Office 365 mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="61e42-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="61e42-124">Cada organização do Microsoft Defender para Office 365 tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="61e42-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="61e42-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="61e42-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="61e42-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="61e42-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="61e42-127">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="61e42-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="61e42-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="61e42-129">Para aumentar a eficácia da proteção anti-phishing no Microsoft Defender para Office 365, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="61e42-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="61e42-130">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="61e42-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="61e42-131">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="61e42-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="61e42-132">Para ir diretamente para a página **Anti-phishing,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="61e42-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="61e42-133">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="61e42-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="61e42-134">Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="61e42-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="61e42-135">Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="61e42-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="61e42-136">Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** <sup>\*</sup> Segurança.</span><span class="sxs-lookup"><span data-stu-id="61e42-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="61e42-137">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="61e42-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="61e42-138">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="61e42-138">**Notes**:</span></span>

  - <span data-ttu-id="61e42-139">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61e42-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="61e42-140">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="61e42-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="61e42-141">O **grupo de função Gerenciamento da Organização** Somente Exibição [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="61e42-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="61e42-142"><sup>\*</sup> No Centro de Conformidade & segurança, o acesso somente leitura permite aos usuários exibir as configurações de políticas anti-phishing personalizadas.</span><span class="sxs-lookup"><span data-stu-id="61e42-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="61e42-143">Os usuários somente leitura não podem ver as configurações na política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="61e42-144">Para nossas configurações recomendadas para políticas anti-phishing no Microsoft Defender para Office 365, consulte [Política anti-phishing](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)no Defender para Office 365 configurações .</span><span class="sxs-lookup"><span data-stu-id="61e42-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="61e42-145">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="61e42-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="61e42-146">Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="61e42-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-147">Use o Centro de Conformidade & segurança para criar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="61e42-148">A criação de uma política anti-phishing personalizada no Centro de Conformidade e Segurança cria a regra anti-phishing e a política anti-phish & ing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="61e42-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="61e42-149">Ao criar uma política anti-phishing, você só pode especificar o nome da política, a descrição e o filtro de destinatário que identifica a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="61e42-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="61e42-150">Depois de criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="61e42-151">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-152">Na página **Anti-phishing,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="61e42-153">O **assistente Criar uma nova política anti-phishing** é aberto.</span><span class="sxs-lookup"><span data-stu-id="61e42-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="61e42-154">Na página **Nomear sua política,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="61e42-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="61e42-155">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="61e42-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="61e42-156">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="61e42-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="61e42-157">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="61e42-158">Na página **Aplicada à** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="61e42-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="61e42-159">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="61e42-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="61e42-160">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="61e42-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="61e42-161">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="61e42-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="61e42-162">Clique **em Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="61e42-162">Click **Add a condition**.</span></span> <span data-ttu-id="61e42-163">No menu suspenso exibido, selecione uma condição em **Aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="61e42-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="61e42-164">**O destinatário é**: Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="61e42-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="61e42-165">**O destinatário é membro de**: Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="61e42-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="61e42-166">**O domínio do destinatário é**: Especifica destinatários em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="61e42-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="61e42-167">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="61e42-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="61e42-168">Clique na caixa e role a lista de valores a ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="61e42-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="61e42-169">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="61e42-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="61e42-170">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="61e42-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="61e42-171">Para remover entradas individuais, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="61e42-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="61e42-172">Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="61e42-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="61e42-173">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **Applied if**.</span><span class="sxs-lookup"><span data-stu-id="61e42-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="61e42-174">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**.</span><span class="sxs-lookup"><span data-stu-id="61e42-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="61e42-175">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="61e42-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="61e42-176">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="61e42-177">Na página **Revisar suas configurações** que aparece, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="61e42-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="61e42-178">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="61e42-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="61e42-179">Quando terminar, clique em **Criar essa política.**</span><span class="sxs-lookup"><span data-stu-id="61e42-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="61e42-180">Clique **em OK** na caixa de diálogo de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="61e42-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="61e42-181">Depois de criar a política anti-phishing com essas configurações gerais, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="61e42-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-182">Use o Centro de Conformidade & segurança para modificar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="61e42-183">Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalificou.</span><span class="sxs-lookup"><span data-stu-id="61e42-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="61e42-184">Se você ainda não estiver lá, abra o Centro de  Conformidade & Segurança e vá para Política de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-185">Selecione a política anti-phishing personalizada que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="61e42-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="61e42-186">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="61e42-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="61e42-187">O **sobrevoo \<name\>** Editar sua política é exibido.</span><span class="sxs-lookup"><span data-stu-id="61e42-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="61e42-188">Clicar em **Editar** em qualquer seção oferece acesso às configurações nessa seção.</span><span class="sxs-lookup"><span data-stu-id="61e42-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="61e42-189">As etapas a seguir são apresentadas na ordem em que as seções aparecem, mas elas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="61e42-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="61e42-190">Depois de  clicar em Editar em uma seção, as configurações disponíveis são apresentadas em um formato  de assistente, mas  você  pode pular dentro das páginas em qualquer ordem, e você pode clicar em Salvar em qualquer página (ou ![ ](../../media/scc-remove-icon.png) **\<name\>** Cancelar ou Fechar Ícone para retornar à página Editar sua política (não é necessário visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="61e42-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="61e42-191">**Configuração de** política : Clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você criou a [política](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="61e42-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="61e42-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="61e42-192">**Name**</span></span>
   - <span data-ttu-id="61e42-193">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="61e42-193">**Description**</span></span>
   - <span data-ttu-id="61e42-194">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="61e42-194">**Applied to**</span></span>
   - <span data-ttu-id="61e42-195">**Analisar suas configurações**</span><span class="sxs-lookup"><span data-stu-id="61e42-195">**Review your settings**</span></span>

   <span data-ttu-id="61e42-196">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="61e42-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="61e42-197">**Representação**: Clique em **Editar** para modificar os remetentes protegidos e os domínios de remetente protegidos na política.</span><span class="sxs-lookup"><span data-stu-id="61e42-197">**Impersonation**: Click **Edit** to modify the protected senders and protected sender domains in the policy.</span></span> <span data-ttu-id="61e42-198">Essas configurações são uma condição para a política que identifica remetentes específicos a procurar (individualmente ou por domínio) no endereço From de mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="61e42-198">These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="61e42-199">Para obter mais informações, consulte Configurações de representação [em políticas anti-phishing no Microsoft Defender para](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="61e42-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="61e42-200">**Adicionar usuários para proteger**: O valor padrão é **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-200">**Add users to protect**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="61e42-201">Para acioná-lo, deslize a alternância para **On** Toggle On e clique no botão ![ Adicionar ](../../media/scc-toggle-on.png) **usuário** que aparece.</span><span class="sxs-lookup"><span data-stu-id="61e42-201">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="61e42-202">No **flyout Adicionar usuário** exibido, configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="61e42-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="61e42-203">**Endereço de email**:</span><span class="sxs-lookup"><span data-stu-id="61e42-203">**Email address**:</span></span>

       - <span data-ttu-id="61e42-204">Clique na caixa e role a lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="61e42-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="61e42-205">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário.</span><span class="sxs-lookup"><span data-stu-id="61e42-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="61e42-206">Para remover uma entrada, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) usuário.</span><span class="sxs-lookup"><span data-stu-id="61e42-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="61e42-207">**Nome**: Esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="61e42-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="61e42-208">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="61e42-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="61e42-209">Para editar uma entrada existente, selecione o usuário protegido na lista.</span><span class="sxs-lookup"><span data-stu-id="61e42-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="61e42-210">Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente).</span><span class="sxs-lookup"><span data-stu-id="61e42-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="61e42-211">Não é possível especificar o mesmo usuário protegido em várias políticas.</span><span class="sxs-lookup"><span data-stu-id="61e42-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="61e42-212">A proteção de representação do usuário não funcionará se o remetente e o destinatário se comunicarem anteriormente por email.</span><span class="sxs-lookup"><span data-stu-id="61e42-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="61e42-213">Se o remetente e o destinatário nunca se comunicarem por email, a mensagem será identificada como uma tentativa de representação.</span><span class="sxs-lookup"><span data-stu-id="61e42-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="61e42-214">**Adicionar domínios para proteger**: Configurar uma ou ambas as configurações a seguir:</span><span class="sxs-lookup"><span data-stu-id="61e42-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="61e42-215">**Inclua automaticamente os domínios que eu tenho**: O valor padrão é **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-215">**Automatically include the domains I own**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="61e42-216">Para a ativar, deslize a alternância para **On** ![ Toggle On ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-216">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

       <span data-ttu-id="61e42-217">Para exibir os domínios que você possui, selecione **Exibir domínios que eu tenho**.</span><span class="sxs-lookup"><span data-stu-id="61e42-217">To view the domains that you own, select **View domains I own**.</span></span>

     - <span data-ttu-id="61e42-218">**Incluir domínios personalizados**: o valor padrão é **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-218">**Include custom domains**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="61e42-219">Para acioná-lo, deslize a alternância para **On** Toggle On e, na caixa Adicionar domínios, insira o nome de domínio ![ ](../../media/scc-toggle-on.png) (por exemplo, contoso.com),  pressione ENTER e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="61e42-219">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="61e42-220">Você pode ter no máximo 50 domínios em todas as políticas anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-220">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="61e42-221">**Ações**: Clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="61e42-221">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="61e42-222">**Se o email** for enviado por um usuário personificado : Configure uma das seguintes ações para mensagens em que o remetente é um dos usuários protegidos especificados em Adicionar usuários para **proteger**:</span><span class="sxs-lookup"><span data-stu-id="61e42-222">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="61e42-223">**Não aplique nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="61e42-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="61e42-224">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="61e42-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="61e42-225">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="61e42-225">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="61e42-226">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="61e42-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="61e42-227">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="61e42-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="61e42-228">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="61e42-228">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="61e42-229">**Se o email** for enviado por um domínio personificado : Configure uma das seguintes ações para mensagens em que o domínio do remetente está em um dos domínios protegidos especificados em **Adicionar domínios** para proteger :</span><span class="sxs-lookup"><span data-stu-id="61e42-229">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the sender's domain is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="61e42-230">**Não aplique nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="61e42-230">**Don't apply any action**</span></span>
       - <span data-ttu-id="61e42-231">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="61e42-231">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="61e42-232">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="61e42-232">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="61e42-233">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="61e42-233">**Quarantine the message**</span></span>
       - <span data-ttu-id="61e42-234">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="61e42-234">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="61e42-235">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="61e42-235">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="61e42-236">Clique **em Ativar dicas de segurança de** representação e configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="61e42-236">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="61e42-237">**Mostrar dica para usuários personificados**</span><span class="sxs-lookup"><span data-stu-id="61e42-237">**Show tip for impersonated users**</span></span>
     - <span data-ttu-id="61e42-238">**Mostrar dica para domínios personificados**</span><span class="sxs-lookup"><span data-stu-id="61e42-238">**Show tip for impersonated domains**</span></span>
     - <span data-ttu-id="61e42-239">**Mostrar dica para caracteres incomuns**</span><span class="sxs-lookup"><span data-stu-id="61e42-239">**Show tip for unusual characters**</span></span>

     <span data-ttu-id="61e42-240">O valor padrão para todas as dicas é **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-240">The default value for all tips is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="61e42-241">Para ativar qualquer um deles, deslize a alternância para **On** [Toggle On](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="61e42-241">To turn any of them on, slide the toggle to **On** [Toggle On](../../media/scc-toggle-on.png).</span></span>

     <span data-ttu-id="61e42-242">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="61e42-243">**Inteligência de caixa de correio**:</span><span class="sxs-lookup"><span data-stu-id="61e42-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="61e42-244">**Habilitar a inteligência de** caixa de correio? : O valor padrão **é On** [Toggle On](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="61e42-244">**Enable mailbox intelligence?**: The default value is **On** [Toggle On](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="61e42-245">Para desativar, deslize a alternância para **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-245">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     - <span data-ttu-id="61e42-246">**Habilitar a proteção de** representação baseada em inteligência de caixa de correio? : Essa configuração só estará disponível se **Habilitar a** inteligência de caixa de correio? está **ativado**.</span><span class="sxs-lookup"><span data-stu-id="61e42-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="61e42-247">A opção Ativar essa configuração para especificar a ação a ser tomada em mensagens para detecções de representação de resultados de inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="61e42-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="61e42-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span><span class="sxs-lookup"><span data-stu-id="61e42-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="61e42-249">**Não aplique nenhuma** ação : observe que esse valor tem o mesmo resultado de ativar a Inteligência de Caixa de **Correio?** mas desligar Habilitar proteção de representação baseada em inteligência de caixa de **correio?**. .</span><span class="sxs-lookup"><span data-stu-id="61e42-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="61e42-250">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="61e42-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="61e42-251">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="61e42-251">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="61e42-252">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="61e42-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="61e42-253">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="61e42-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="61e42-254">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="61e42-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="61e42-255">**Adicionar senders e domínios confiáveis**: Especifique exceções para a política:</span><span class="sxs-lookup"><span data-stu-id="61e42-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="61e42-256">**Senders confiáveis**:</span><span class="sxs-lookup"><span data-stu-id="61e42-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="61e42-257">Clique na caixa e role a lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="61e42-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="61e42-258">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário.</span><span class="sxs-lookup"><span data-stu-id="61e42-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="61e42-259">Para remover uma entrada, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) usuário.</span><span class="sxs-lookup"><span data-stu-id="61e42-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="61e42-260">**Domínios confiáveis**: insira o nome de domínio (por exemplo, contoso.com), pressione ENTER e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="61e42-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="61e42-261">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="61e42-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="61e42-262">Você pode clicar **em Editar** em cada seção para voltar à página relevante.</span><span class="sxs-lookup"><span data-stu-id="61e42-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="61e42-263">Você pode alternar as seguintes configurações **On** ou **Off** diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="61e42-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="61e42-264">**Usuários protegidos**</span><span class="sxs-lookup"><span data-stu-id="61e42-264">**Protected users**</span></span>
       - <span data-ttu-id="61e42-265">**Domínios protegidos** \> **Incluir domínios que eu tenho**</span><span class="sxs-lookup"><span data-stu-id="61e42-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="61e42-266">**Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)</span><span class="sxs-lookup"><span data-stu-id="61e42-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="61e42-267">**Inteligência da caixa de correio**</span><span class="sxs-lookup"><span data-stu-id="61e42-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="61e42-268">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="61e42-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="61e42-269">**Spoof**:  clique em Editar para ativar ou desativar a inteligência de spoof, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação a ser aplicada a mensagens de remetentes espojados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="61e42-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="61e42-270">Para obter mais informações sobre essas configurações, consulte [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="61e42-270">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="61e42-271">Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.</span><span class="sxs-lookup"><span data-stu-id="61e42-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="61e42-272">**Configurações de filtro de spoofing**: Use a configuração Habilitar a inteligência de **spoof?** para ativar ou desativar a inteligência de spoofing.</span><span class="sxs-lookup"><span data-stu-id="61e42-272">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="61e42-273">O valor padrão é **On** e recomendamos que você o deixe em.</span><span class="sxs-lookup"><span data-stu-id="61e42-273">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="61e42-274">Para desativar, deslize a alternância para **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-274">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="61e42-275">Você não precisa desativar a proteção anti-spoofing se seu registro MX não apontar para Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores.</span><span class="sxs-lookup"><span data-stu-id="61e42-275">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="61e42-276">Para obter instruções, [consulte Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="61e42-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="61e42-277">**Configurações de remetente** não autenticados : Você pode definir as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="61e42-277">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="61e42-278">**Habilitar** o símbolo de ponto de interrogação de remetente não autenticado (?) ? : Adicionar um ponto de interrogação à foto  do remetente na caixa De no Outlook se a mensagem não passar em verificações SPF ou DKIM e a mensagem não passar DMARC ou [autenticação](email-validation-and-authentication.md#composite-authentication)composta .</span><span class="sxs-lookup"><span data-stu-id="61e42-278">**Enable unauthenticated sender question mark (?) symbol?**: Add a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="61e42-279">O valor padrão é **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="61e42-279">The default value is **On**.</span></span> <span data-ttu-id="61e42-280">Para desativar, deslize a alternância para **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-280">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="61e42-281">Habilitar a marca **"via"?**: Adicione a marca via (chris@contoso.com via fabrikam.com) se o endereço de email na caixa De for diferente do domínio na assinatura DKIM ou no **endereço MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="61e42-281">**Enable "via" tag?**: Add the via tag (chris@contoso.com via fabrikam.com) if the email address in the From box is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="61e42-282">O valor padrão é **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="61e42-282">The default value is **On**.</span></span> <span data-ttu-id="61e42-283">Para desativar, deslize a alternância para **Off** ![ Toggle Off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="61e42-283">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="61e42-284">**Ações**: Especifique a ação a ser tomada em mensagens de envios com spoofed bloqueados:</span><span class="sxs-lookup"><span data-stu-id="61e42-284">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="61e42-285">**Se o email for enviado por alguém que não tenha permissão para spoofar seu domínio**:</span><span class="sxs-lookup"><span data-stu-id="61e42-285">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="61e42-286">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="61e42-286">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="61e42-287">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="61e42-287">**Quarantine the message**</span></span>

   - <span data-ttu-id="61e42-288">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="61e42-288">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="61e42-289">Você pode clicar **em Editar** em cada seção para voltar à página relevante.</span><span class="sxs-lookup"><span data-stu-id="61e42-289">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="61e42-290">Você pode alternar as seguintes configurações **On** ou **Off** diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="61e42-290">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="61e42-291">**Configurações de filtro de spoof**</span><span class="sxs-lookup"><span data-stu-id="61e42-291">**Spoof filter settings**</span></span>
       - <span data-ttu-id="61e42-292">**Configurações de remetente não autenticados**</span><span class="sxs-lookup"><span data-stu-id="61e42-292">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="61e42-293">**Actions**</span><span class="sxs-lookup"><span data-stu-id="61e42-293">**Actions**</span></span>

   <span data-ttu-id="61e42-294">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="61e42-294">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="61e42-295">**Configurações avançadas:** clique **em Editar** para configurar os limites avançados de phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-295">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="61e42-296">Para obter mais informações, consulte [Limites avançados de phishing em políticas anti-phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)no Microsoft Defender para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="61e42-296">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="61e42-297">**Limites avançados de phishing:** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="61e42-297">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="61e42-298">**1 - Standard** (Este é o valor padrão.)</span><span class="sxs-lookup"><span data-stu-id="61e42-298">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="61e42-299">**2 - Agressivo**</span><span class="sxs-lookup"><span data-stu-id="61e42-299">**2 - Aggressive**</span></span>
   - <span data-ttu-id="61e42-300">**3 - Mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="61e42-300">**3 - More aggressive**</span></span>
   - <span data-ttu-id="61e42-301">**4 - Mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="61e42-301">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="61e42-302">**Revise suas configurações**: Clique em **Editar** para voltar à **página Limites avançados de phishing.**</span><span class="sxs-lookup"><span data-stu-id="61e42-302">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="61e42-303">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="61e42-303">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="61e42-304">Volte à página **Editar sua política, \<Name\>** revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-304">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-305">Use o Centro de Conformidade & segurança para modificar a política anti-phishing padrão no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-305">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="61e42-306">A política anti-phishing padrão no Microsoft Defender para Office 365 se chama Office365 AntiPhish Default e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="61e42-306">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="61e42-307">Para modificar a política anti-phishing padrão, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="61e42-307">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="61e42-308">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-309">Na página **Anti-phishing,** clique em **Política padrão**.</span><span class="sxs-lookup"><span data-stu-id="61e42-309">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="61e42-310">A **página Editar sua política Padrão do Office365 AntiPhish** é exibida.</span><span class="sxs-lookup"><span data-stu-id="61e42-310">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="61e42-311">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="61e42-311">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="61e42-312">**Representação**</span><span class="sxs-lookup"><span data-stu-id="61e42-312">**Impersonation**</span></span>
   - <span data-ttu-id="61e42-313">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="61e42-313">**Spoof**</span></span>
   - <span data-ttu-id="61e42-314">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="61e42-314">**Advanced settings**</span></span>

   <span data-ttu-id="61e42-315">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="61e42-315">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="61e42-316">Você pode  ver a seção Configuração de Política e valores, mas não há nenhum link **Editar,** portanto, não é possível modificar as configurações (nome da política, descrição e a quem a política se aplica (ela se aplica a todos os destinatários)).</span><span class="sxs-lookup"><span data-stu-id="61e42-316">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="61e42-317">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-317">You can't delete the default policy.</span></span>
   - <span data-ttu-id="61e42-318">Não é possível alterar a prioridade da política padrão (ela sempre é aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="61e42-318">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="61e42-319">Na página **Editar sua política Padrão do Office365 AntiPhish,** revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-319">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-320">Habilitar ou desabilitar políticas anti-phishing personalizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-320">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="61e42-321">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-322">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="61e42-322">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="61e42-323">Deslize a alternância **para Off** ![ Toggle Off para ](../../media/scc-toggle-off.png) desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="61e42-323">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="61e42-324">Deslize a alternância **para On** ![ Toggle On para ](../../media/scc-toggle-on.png) habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="61e42-324">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="61e42-325">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-325">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-326">Definir a prioridade de políticas anti-phishing personalizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-326">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="61e42-327">Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="61e42-327">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="61e42-328">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="61e42-328">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="61e42-329">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="61e42-329">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="61e42-330">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="61e42-330">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="61e42-331">As políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem **o valor priority** 0).</span><span class="sxs-lookup"><span data-stu-id="61e42-331">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="61e42-332">A política anti-phishing padrão chamada Office365 AntiPhish Default tem o valor de prioridade personalizado **Mais** baixo e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="61e42-332">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="61e42-333">**Observação**: no Centro de Conformidade & segurança, você só pode alterar a prioridade da política anti-phishing após a criação.</span><span class="sxs-lookup"><span data-stu-id="61e42-333">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="61e42-334">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="61e42-334">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="61e42-335">Para alterar a prioridade de  uma política, clique em Aumentar prioridade ou Diminuir prioridade  nas propriedades da política (não é possível modificar diretamente o número de prioridade no Centro de Conformidade & Segurança). </span><span class="sxs-lookup"><span data-stu-id="61e42-335">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="61e42-336">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="61e42-336">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="61e42-337">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-337">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-338">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="61e42-338">Select the policy that you want to modify.</span></span> <span data-ttu-id="61e42-339">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="61e42-339">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="61e42-340">O **sobrevoo \<name\>** Editar sua política é exibido.</span><span class="sxs-lookup"><span data-stu-id="61e42-340">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="61e42-341">A política anti-phishing personalizada com o **valor Prioridade** **0** tem apenas o **botão Diminuir** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="61e42-341">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="61e42-342">A política anti-phishing personalizada com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="61e42-342">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="61e42-343">Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas  entre os valores de prioridade mais alta e mais baixa terão os botões **Aumentar** prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="61e42-343">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="61e42-344">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor Priority.**</span><span class="sxs-lookup"><span data-stu-id="61e42-344">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="61e42-345">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="61e42-345">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-346">Use o Centro de Conformidade & segurança para exibir políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-346">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="61e42-347">No Centro de Conformidade & segurança e vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-347">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-348">Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="61e42-348">Do one of the following steps:</span></span>

   - <span data-ttu-id="61e42-349">Selecione uma política anti-phishing personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="61e42-349">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="61e42-350">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="61e42-350">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="61e42-351">Clique **em Política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-351">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="61e42-352">O **flyout \<name\> Editar sua** política é exibido, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="61e42-352">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-353">Use o Centro de Conformidade & segurança para remover políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-353">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="61e42-354">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61e42-355">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="61e42-355">Select the policy that you want to remove.</span></span> <span data-ttu-id="61e42-356">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="61e42-356">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="61e42-357">No **sobrevoo \<name\> Editar sua política** que aparece, clique em **Excluir política** e clique em **Sim** na caixa de diálogo de aviso exibida.</span><span class="sxs-lookup"><span data-stu-id="61e42-357">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="61e42-358">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="61e42-358">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="61e42-359">Use Exchange Online PowerShell para configurar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="61e42-359">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="61e42-360">Conforme descrito anteriormente, uma política anti-spam consiste em uma política anti-phishing e uma regra anti-phish.</span><span class="sxs-lookup"><span data-stu-id="61e42-360">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="61e42-361">No Exchange Online PowerShell, a diferença entre políticas anti-phishing e regras anti-phishing é aparente.</span><span class="sxs-lookup"><span data-stu-id="61e42-361">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="61e42-362">Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="61e42-362">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="61e42-363">No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="61e42-363">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="61e42-364">No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.</span><span class="sxs-lookup"><span data-stu-id="61e42-364">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="61e42-365">Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="61e42-365">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="61e42-366">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-366">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="61e42-367">Criar uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="61e42-367">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="61e42-368">Crie a política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-368">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="61e42-369">Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="61e42-369">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="61e42-370">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="61e42-370">**Notes**:</span></span>

- <span data-ttu-id="61e42-371">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="61e42-371">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="61e42-372">Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-372">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="61e42-373">Você pode configurar as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no Centro de Conformidade de Segurança & até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="61e42-373">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="61e42-374">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="61e42-374">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="61e42-375">De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="61e42-375">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="61e42-376">Uma nova política anti-phishing que você cria no PowerShell não fica visível no Centro de Conformidade & Segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="61e42-376">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="61e42-377">Etapa 1: Usar o PowerShell para criar uma política anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-377">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="61e42-378">Para criar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-378">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="61e42-379">Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="61e42-379">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="61e42-380">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="61e42-380">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="61e42-381">A descrição é: Política do departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="61e42-381">The description is: Research department policy.</span></span>
- <span data-ttu-id="61e42-382">Habilita a proteção de domínios da organização para todos os domínios aceitos e a proteção de domínios direcionados para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="61e42-382">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="61e42-383">Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário a ser protegido contra representação.</span><span class="sxs-lookup"><span data-stu-id="61e42-383">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="61e42-384">Habilita a inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="61e42-384">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="61e42-385">Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.</span><span class="sxs-lookup"><span data-stu-id="61e42-385">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="61e42-386">Habilita dicas de segurança.</span><span class="sxs-lookup"><span data-stu-id="61e42-386">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="61e42-387">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="61e42-387">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="61e42-388">Etapa 2: Usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-388">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="61e42-389">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-389">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="61e42-390">Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="61e42-390">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="61e42-391">A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="61e42-391">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="61e42-392">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="61e42-392">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="61e42-393">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="61e42-393">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="61e42-394">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="61e42-394">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="61e42-395">Usar o PowerShell para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-395">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="61e42-396">Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-396">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="61e42-397">Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="61e42-397">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="61e42-398">Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="61e42-398">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="61e42-399">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="61e42-399">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="61e42-400">Usar o PowerShell para exibir regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-400">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="61e42-401">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-401">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="61e42-402">Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="61e42-402">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="61e42-403">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="61e42-403">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="61e42-404">Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="61e42-404">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="61e42-405">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="61e42-405">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="61e42-406">Usar o PowerShell para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-406">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="61e42-407">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria a política conforme descrito na Etapa [1: Usar o PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) para criar uma seção de política anti-phishing anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="61e42-407">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="61e42-408">A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61e42-408">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="61e42-409">Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="61e42-409">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="61e42-410">Quando você renomeia uma política anti-phish & ing no Centro de Conformidade e Segurança, você só renomeia a regra _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="61e42-410">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="61e42-411">Para modificar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-411">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="61e42-412">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="61e42-412">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="61e42-413">Usar o PowerShell para modificar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-413">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="61e42-414">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="61e42-414">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="61e42-415">Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="61e42-415">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="61e42-416">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61e42-416">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="61e42-417">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na Etapa 2: Use o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="61e42-417">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="61e42-418">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-418">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="61e42-419">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="61e42-419">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="61e42-420">Usar o PowerShell para habilitar ou desabilitar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-420">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="61e42-421">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída).</span><span class="sxs-lookup"><span data-stu-id="61e42-421">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="61e42-422">Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="61e42-422">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="61e42-423">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-423">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="61e42-424">Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="61e42-424">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="61e42-425">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="61e42-425">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="61e42-426">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="61e42-426">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="61e42-427">Usar o PowerShell para definir a prioridade das regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-427">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="61e42-428">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="61e42-428">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="61e42-429">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="61e42-429">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="61e42-430">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="61e42-430">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="61e42-431">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="61e42-431">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="61e42-432">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="61e42-432">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="61e42-433">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-433">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="61e42-434">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="61e42-434">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="61e42-435">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="61e42-435">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="61e42-436">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="61e42-436">**Notes**:</span></span>

- <span data-ttu-id="61e42-437">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="61e42-437">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="61e42-438">A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.</span><span class="sxs-lookup"><span data-stu-id="61e42-438">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="61e42-439">Usar o PowerShell para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-439">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="61e42-440">Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="61e42-440">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="61e42-441">Para remover uma política anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-441">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="61e42-442">Este exemplo remove a política anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="61e42-442">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="61e42-443">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="61e42-443">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="61e42-444">Usar o PowerShell para remover regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="61e42-444">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="61e42-445">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="61e42-445">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="61e42-446">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="61e42-446">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="61e42-447">Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="61e42-447">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="61e42-448">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="61e42-448">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="61e42-449">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="61e42-449">How do you know these procedures worked?</span></span>

<span data-ttu-id="61e42-450">Para verificar se você configurou com êxito políticas anti-phishing no Microsoft Defender para Office 365, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="61e42-450">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="61e42-451">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="61e42-451">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="61e42-452">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="61e42-452">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="61e42-453">Para exibir mais detalhes, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="61e42-453">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="61e42-454">Selecione a política na lista e veja os detalhes no sobremenu.</span><span class="sxs-lookup"><span data-stu-id="61e42-454">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="61e42-455">Clique **em Política padrão** e veja os detalhes no sobremenu.</span><span class="sxs-lookup"><span data-stu-id="61e42-455">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="61e42-456">No Exchange Online PowerShell, substitua pelo nome da política ou regra e execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="61e42-456">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```