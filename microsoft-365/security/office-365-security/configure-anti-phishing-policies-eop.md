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
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing disponíveis em organizações do Exchange Online Protection (EOP) com ou sem caixas de correio do Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c277558bad32e1926030483d202b70ae3c910315
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203138"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="a3be1-103">Configurar políticas anti-phishing em EOP</span><span class="sxs-lookup"><span data-stu-id="a3be1-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3be1-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a3be1-104">**Applies to**</span></span>
- [<span data-ttu-id="a3be1-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3be1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="a3be1-106">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há uma política anti-phishing padrão que contém um número limitado de recursos antifalsagem habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="a3be1-107">Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="a3be1-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="a3be1-108">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="a3be1-109">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3be1-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a3be1-110">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a3be1-111">As organizações com caixas de correio do Exchange Online podem configurar políticas anti-phishing no Centro de Conformidade & Segurança ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3be1-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="a3be1-112">As organizações EOP autônomas só podem usar o Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="a3be1-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="a3be1-113">Para obter informações sobre como criar e modificar as políticas anti-phishing mais avançadas no Microsoft Defender para Office 365 que estão disponíveis no Defender para Office 365, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a3be1-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="a3be1-114">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="a3be1-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="a3be1-115">**A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.</span><span class="sxs-lookup"><span data-stu-id="a3be1-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="a3be1-116">**A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="a3be1-117">A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="a3be1-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a3be1-118">Ao criar uma política anti-phishing, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="a3be1-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a3be1-119">Quando você modifica uma política anti-phishing, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="a3be1-120">Todas as outras configurações modificam a política anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="a3be1-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="a3be1-121">Quando você remove uma política anti-phishing, a regra anti-phishing e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="a3be1-122">No PowerShell do Exchange Online, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a3be1-123">Para obter mais informações, consulte [a seção Usar o PowerShell do Exchange Online para configurar políticas anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a3be1-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="a3be1-124">Cada organização tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="a3be1-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="a3be1-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="a3be1-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a3be1-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="a3be1-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a3be1-127">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="a3be1-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="a3be1-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a3be1-129">Para aumentar a eficácia da proteção anti-phishing, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="a3be1-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3be1-130">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a3be1-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3be1-131">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a3be1-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a3be1-132">Para ir diretamente para a página **Anti-phishing,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="a3be1-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="a3be1-133">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a3be1-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="a3be1-134">Não é possível gerenciar políticas anti-phishing no EOP PowerShell autônomo.</span><span class="sxs-lookup"><span data-stu-id="a3be1-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="a3be1-135">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="a3be1-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a3be1-136">Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="a3be1-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a3be1-137">Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** <sup>\*</sup> Segurança.</span><span class="sxs-lookup"><span data-stu-id="a3be1-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="a3be1-138">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a3be1-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a3be1-139">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a3be1-139">**Notes**:</span></span>

  - <span data-ttu-id="a3be1-140">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3be1-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a3be1-141">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a3be1-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a3be1-142">O **grupo de função Gerenciamento de Organização** Somente Exibição no Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="a3be1-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="a3be1-143"><sup>\*</sup> No Centro de Conformidade & segurança, o acesso somente leitura permite aos usuários exibir as configurações de políticas anti-phishing personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="a3be1-144">Os usuários somente leitura não podem ver as configurações na política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="a3be1-145">Para criar e modificar políticas anti-phishing no EOP autônomo, você precisa fazer algo que exija _a hidratação_ para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="a3be1-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="a3be1-146">Por exemplo, no Centro de administração do Exchange  (EAC), você pode ir até a guia Permissões, selecionar um grupo de função existente, clicar em **Editar** ícone editar e remover uma função (que você adicionará ![ ](../../media/ITPro-EAC-EditIcon.png) novamente).</span><span class="sxs-lookup"><span data-stu-id="a3be1-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="a3be1-147">Se o locatário nunca tiver sido hidratado, você obterá uma caixa de diálogo chamada **Atualizar** Configurações da Organização com uma barra de progresso que deve ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="a3be1-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="a3be1-148">Para obter mais informações sobre a hidratação, consulte o cmdlet [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (que não está disponível no EOP PowerShell autônomo ou no Centro de Conformidade & Segurança).</span><span class="sxs-lookup"><span data-stu-id="a3be1-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="a3be1-149">Para nossas configurações recomendadas para políticas anti-phishing, consulte Configurações de política [anti-phishing](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)padrão do EOP.</span><span class="sxs-lookup"><span data-stu-id="a3be1-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="a3be1-150">Permitir até 30 minutos para que a política atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="a3be1-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="a3be1-151">Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="a3be1-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="a3be1-152">Usar o Centro de Conformidade & segurança para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="a3be1-153">A criação de uma política anti-phishing personalizada no Centro de Conformidade e Segurança cria a regra anti-phishing e a política anti-phish & ing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="a3be1-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="a3be1-154">Ao criar uma política anti-phishing, você só pode especificar o nome da política, a descrição e o filtro de destinatário que identifica a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="a3be1-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="a3be1-155">Depois de criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="a3be1-156">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-157">Na página **Anti-phishing,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="a3be1-158">O **assistente Criar uma nova política anti-phishing** é aberto.</span><span class="sxs-lookup"><span data-stu-id="a3be1-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="a3be1-159">Na página **Nomear sua política,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a3be1-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="a3be1-160">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="a3be1-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="a3be1-161">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="a3be1-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a3be1-162">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a3be1-163">Na página **Aplicada à** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="a3be1-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="a3be1-164">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="a3be1-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a3be1-165">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a3be1-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a3be1-166">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a3be1-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="a3be1-167">Clique **em Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-167">Click **Add a condition**.</span></span> <span data-ttu-id="a3be1-168">No menu suspenso exibido, selecione uma condição em **Aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="a3be1-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="a3be1-169">**O destinatário é**: Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3be1-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a3be1-170">**O destinatário é membro de**: Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3be1-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="a3be1-171">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="a3be1-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="a3be1-172">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="a3be1-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="a3be1-173">Clique na caixa e role a lista de valores a ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="a3be1-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="a3be1-174">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="a3be1-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="a3be1-175">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="a3be1-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="a3be1-176">Para remover entradas individuais, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="a3be1-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="a3be1-177">Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="a3be1-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="a3be1-178">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **Applied if**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="a3be1-179">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="a3be1-180">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="a3be1-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a3be1-181">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a3be1-182">Na página **Revisar suas configurações** que aparece, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="a3be1-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="a3be1-183">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="a3be1-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="a3be1-184">Quando terminar, clique em **Criar essa política.**</span><span class="sxs-lookup"><span data-stu-id="a3be1-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="a3be1-185">Clique **em OK** na caixa de diálogo de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="a3be1-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="a3be1-186">Depois de criar a política anti-phishing com essas configurações gerais de política, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="a3be1-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="a3be1-187">Use o Centro de Conformidade & segurança para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="a3be1-188">Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalificou.</span><span class="sxs-lookup"><span data-stu-id="a3be1-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="a3be1-189">Se você ainda não estiver lá, abra o Centro de  Conformidade & Segurança e vá para Política de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-190">Selecione a política anti-phishing personalizada que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a3be1-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="a3be1-191">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a3be1-192">O **sobrevoo \<name\>** Editar sua política é exibido.</span><span class="sxs-lookup"><span data-stu-id="a3be1-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="a3be1-193">Clicar em **Editar** em qualquer seção oferece acesso às configurações nessa seção.</span><span class="sxs-lookup"><span data-stu-id="a3be1-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="a3be1-194">As etapas a seguir são apresentadas na ordem em que as seções aparecem, mas elas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="a3be1-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="a3be1-195">Depois de  clicar em Editar em uma seção, as configurações disponíveis são apresentadas em um formato  de assistente, mas  você  pode pular dentro das páginas em qualquer ordem, e você pode clicar em Salvar em qualquer página (ou ![ ](../../media/scc-remove-icon.png) **\<name\>** Cancelar ou Fechar Ícone para retornar à página Editar sua política (não é necessário visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="a3be1-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="a3be1-196">**Configuração de** política : Clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você criou a [política](#use-the-security--compliance-center-to-create-anti-phishing-policies) na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="a3be1-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="a3be1-197">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a3be1-197">**Name**</span></span>
   - <span data-ttu-id="a3be1-198">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a3be1-198">**Description**</span></span>
   - <span data-ttu-id="a3be1-199">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="a3be1-199">**Applied to**</span></span>
   - <span data-ttu-id="a3be1-200">**Analisar suas configurações**</span><span class="sxs-lookup"><span data-stu-id="a3be1-200">**Review your settings**</span></span>

   <span data-ttu-id="a3be1-201">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="a3be1-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="a3be1-202">**Spoof**:  clique em Editar para ativar ou desativar a inteligência de spoof, ativar ou desativar a identificação do remetente não autenticado no Outlook e configurar a ação a ser aplicada a mensagens de remetentes espojados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="a3be1-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="a3be1-203">Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="a3be1-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="a3be1-204">Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3be1-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="a3be1-205">**Configurações de filtro de spoofing**: O valor padrão é **On**, e recomendamos que você o deixe em.</span><span class="sxs-lookup"><span data-stu-id="a3be1-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="a3be1-206">Para desativar, deslize a alternância para **Off**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="a3be1-207">Para obter mais informações, [consulte Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="a3be1-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="a3be1-208">Você não precisa desabilitar a proteção anti-spoofing se seu registro MX não apontar para o Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores.</span><span class="sxs-lookup"><span data-stu-id="a3be1-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="a3be1-209">Para obter instruções, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="a3be1-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="a3be1-210">**Habilitar o recurso Remetente Não Autenticado**: O valor padrão é **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="a3be1-211">Para desativar, deslize a alternância para **Off**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="a3be1-212">**Ações**: Especifique a ação a ser tomada em mensagens que falham na inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="a3be1-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="a3be1-213">**Se o email for enviado por alguém que não tenha permissão para spoofar seu domínio**:</span><span class="sxs-lookup"><span data-stu-id="a3be1-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="a3be1-214">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="a3be1-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="a3be1-215">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="a3be1-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="a3be1-216">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="a3be1-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="a3be1-217">Você pode clicar **em Editar** em cada seção para voltar à página relevante.</span><span class="sxs-lookup"><span data-stu-id="a3be1-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="a3be1-218">Você pode alternar as seguintes configurações **On** ou **Off** diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="a3be1-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="a3be1-219">**Habilitar proteção antispoofing**</span><span class="sxs-lookup"><span data-stu-id="a3be1-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="a3be1-220">**Habilitar o recurso Remetente Não Autenticado**</span><span class="sxs-lookup"><span data-stu-id="a3be1-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="a3be1-221">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="a3be1-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="a3be1-222">Volte à página **Editar sua política, \<Name\>** revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="a3be1-223">Use o Centro de Conformidade & segurança para modificar a política anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="a3be1-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="a3be1-224">A política anti-phishing padrão chama-se Office365 AntiPhish Default e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="a3be1-225">Para modificar a política anti-phishing padrão, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a3be1-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="a3be1-226">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-227">Na página **Anti-phishing,** clique em **Política padrão**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="a3be1-228">A **página Editar sua política Padrão do Office365 AntiPhish** é exibida.</span><span class="sxs-lookup"><span data-stu-id="a3be1-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="a3be1-229">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="a3be1-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="a3be1-230">**Representação**</span><span class="sxs-lookup"><span data-stu-id="a3be1-230">**Impersonation**</span></span>
   - <span data-ttu-id="a3be1-231">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="a3be1-231">**Spoof**</span></span>
   - <span data-ttu-id="a3be1-232">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="a3be1-232">**Advanced settings**</span></span>

   <span data-ttu-id="a3be1-233">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="a3be1-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="a3be1-234">Você pode  ver a seção Configuração de Política e valores, mas não há nenhum link **Editar,** portanto, não é possível modificar as configurações (nome da política, descrição e a quem a política se aplica (ela se aplica a todos os destinatários)).</span><span class="sxs-lookup"><span data-stu-id="a3be1-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="a3be1-235">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="a3be1-236">Não é possível alterar a prioridade da política padrão (ela sempre é aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="a3be1-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="a3be1-237">Na página **Editar sua política Padrão do Office365 AntiPhish,** revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="a3be1-238">Habilitar ou desabilitar políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="a3be1-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="a3be1-239">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-240">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="a3be1-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="a3be1-241">Deslize a alternância **para Off** para desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="a3be1-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="a3be1-242">Deslize a alternância para **Ativado** para habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="a3be1-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="a3be1-243">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="a3be1-244">Definir a prioridade de políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="a3be1-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="a3be1-245">Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="a3be1-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a3be1-246">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="a3be1-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a3be1-247">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="a3be1-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a3be1-248">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="a3be1-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="a3be1-249">As políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem **o valor priority** 0).</span><span class="sxs-lookup"><span data-stu-id="a3be1-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a3be1-250">A política anti-phishing padrão chamada Office365 AntiPhish Default tem o valor de prioridade personalizado **Mais** baixo e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="a3be1-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="a3be1-251">**Observação**: no Centro de Conformidade & segurança, você só pode alterar a prioridade da política anti-phishing após a criação.</span><span class="sxs-lookup"><span data-stu-id="a3be1-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="a3be1-252">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="a3be1-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="a3be1-253">Para alterar a prioridade de  uma política, clique em Aumentar prioridade ou Diminuir prioridade  nas propriedades da política (não é possível modificar diretamente o número de prioridade no Centro de Conformidade & Segurança). </span><span class="sxs-lookup"><span data-stu-id="a3be1-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="a3be1-254">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="a3be1-255">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-256">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a3be1-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="a3be1-257">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a3be1-258">O **sobrevoo \<name\>** Editar sua política é exibido.</span><span class="sxs-lookup"><span data-stu-id="a3be1-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="a3be1-259">A política anti-phishing personalizada com o **valor Prioridade** **0** tem apenas o **botão Diminuir** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="a3be1-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="a3be1-260">A política anti-phishing personalizada com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="a3be1-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="a3be1-261">Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas  entre os valores de prioridade mais alta e mais baixa terão os botões **Aumentar** prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a3be1-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="a3be1-262">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor Priority.**</span><span class="sxs-lookup"><span data-stu-id="a3be1-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="a3be1-263">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="a3be1-264">Use o Centro de Conformidade & segurança para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="a3be1-265">No Centro de Conformidade & segurança e vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-266">Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a3be1-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="a3be1-267">Selecione uma política anti-phishing personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="a3be1-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="a3be1-268">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="a3be1-269">Clique **em Política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="a3be1-270">O **flyout \<name\> Editar sua** política é exibido, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="a3be1-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="a3be1-271">Use o Centro de Conformidade & segurança para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="a3be1-272">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a3be1-273">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="a3be1-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="a3be1-274">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a3be1-275">No **sobrevoo \<name\> Editar sua política** que aparece, clique em **Excluir política** e clique em **Sim** na caixa de diálogo de aviso exibida.</span><span class="sxs-lookup"><span data-stu-id="a3be1-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="a3be1-276">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="a3be1-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="a3be1-277">Usar o PowerShell do Exchange Online para configurar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="a3be1-278">Conforme descrito anteriormente, uma política anti-phishing consiste em uma política anti-phishing e uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="a3be1-279">No PowerShell do Exchange Online, a diferença entre políticas anti-phishing e regras anti-phishing é aparente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="a3be1-280">Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="a3be1-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="a3be1-281">No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="a3be1-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a3be1-282">No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.</span><span class="sxs-lookup"><span data-stu-id="a3be1-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="a3be1-283">Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="a3be1-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="a3be1-284">Os procedimentos a seguir do PowerShell não estão disponíveis em organizações autônomas do EOP usando o PowerShell de Proteção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3be1-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="a3be1-285">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="a3be1-286">Criar uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="a3be1-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a3be1-287">Crie a política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="a3be1-288">Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="a3be1-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="a3be1-289">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a3be1-289">**Notes**:</span></span>

- <span data-ttu-id="a3be1-290">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="a3be1-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="a3be1-291">Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="a3be1-292">Você pode configurar as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no Centro de Conformidade de Segurança & até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="a3be1-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="a3be1-293">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="a3be1-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="a3be1-294">De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="a3be1-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="a3be1-295">Uma nova política anti-phishing que você cria no PowerShell não fica visível no Centro de Conformidade & Segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="a3be1-296">Etapa 1: Usar o PowerShell para criar uma política anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="a3be1-297">Para criar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="a3be1-298">Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a3be1-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="a3be1-299">A descrição é: Política do departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3be1-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="a3be1-300">Altera a ação padrão para a spoofing para Quarentena.</span><span class="sxs-lookup"><span data-stu-id="a3be1-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="a3be1-301">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a3be1-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="a3be1-302">Etapa 2: Usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="a3be1-303">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a3be1-304">Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="a3be1-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="a3be1-305">A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3be1-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="a3be1-306">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3be1-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="a3be1-307">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="a3be1-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="a3be1-308">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="a3be1-308">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="a3be1-309">Usar o PowerShell para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="a3be1-310">Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a3be1-311">Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="a3be1-312">Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="a3be1-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="a3be1-313">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a3be1-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="a3be1-314">Usar o PowerShell para exibir regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="a3be1-315">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a3be1-316">Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a3be1-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="a3be1-317">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a3be1-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="a3be1-318">Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="a3be1-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="a3be1-319">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="a3be1-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="a3be1-320">Usar o PowerShell para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="a3be1-321">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria uma política conforme descrito na Etapa 1: Use o PowerShell para criar uma política [anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a3be1-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="a3be1-322">A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3be1-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="a3be1-323">Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="a3be1-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a3be1-324">Quando você renomeia uma política anti-phish & ing no Centro de Conformidade e Segurança, você só renomeia a regra _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="a3be1-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="a3be1-325">Para modificar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a3be1-326">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a3be1-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="a3be1-327">Usar o PowerShell para modificar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="a3be1-328">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a3be1-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a3be1-329">Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="a3be1-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="a3be1-330">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa 2: Usar o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a3be1-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="a3be1-331">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a3be1-332">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="a3be1-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="a3be1-333">Usar o PowerShell para habilitar ou desabilitar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="a3be1-334">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída).</span><span class="sxs-lookup"><span data-stu-id="a3be1-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="a3be1-335">Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="a3be1-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="a3be1-336">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="a3be1-337">Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a3be1-338">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="a3be1-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a3be1-339">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="a3be1-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="a3be1-340">Usar o PowerShell para definir a prioridade das regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="a3be1-341">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="a3be1-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a3be1-342">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="a3be1-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a3be1-343">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="a3be1-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a3be1-344">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="a3be1-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a3be1-345">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="a3be1-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a3be1-346">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a3be1-347">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="a3be1-347">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a3be1-348">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="a3be1-348">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a3be1-349">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a3be1-349">**Notes**:</span></span>

- <span data-ttu-id="a3be1-350">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="a3be1-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="a3be1-351">A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="a3be1-352">Usar o PowerShell para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="a3be1-353">Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="a3be1-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="a3be1-354">Para remover uma política anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a3be1-355">Este exemplo remove a política anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a3be1-356">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a3be1-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="a3be1-357">Usar o PowerShell para remover regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a3be1-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="a3be1-358">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="a3be1-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="a3be1-359">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a3be1-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="a3be1-360">Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="a3be1-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a3be1-361">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="a3be1-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a3be1-362">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="a3be1-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="a3be1-363">Para verificar se você configurou com êxito políticas anti-phishing no Microsoft Defender para Office 365, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a3be1-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="a3be1-364">No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a3be1-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="a3be1-365">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="a3be1-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a3be1-366">Para exibir mais detalhes, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a3be1-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="a3be1-367">Selecione a política na lista e veja os detalhes no sobremenu.</span><span class="sxs-lookup"><span data-stu-id="a3be1-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="a3be1-368">Clique **em Política padrão** e veja os detalhes no sobremenu.</span><span class="sxs-lookup"><span data-stu-id="a3be1-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="a3be1-369">No PowerShell do Exchange Online, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="a3be1-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```