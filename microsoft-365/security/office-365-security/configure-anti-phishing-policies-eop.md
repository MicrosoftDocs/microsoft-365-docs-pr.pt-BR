---
title: Configurar políticas anti-phishing no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing disponíveis nas organizações do Exchange Online Protection (EOP) com ou sem caixas de correio do Exchange Online.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726780"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="d61cd-103">Configurar políticas anti-phishing no EOP</span><span class="sxs-lookup"><span data-stu-id="d61cd-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="d61cd-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há uma política anti-phishing padrão que contém um número limitado de recursos anti-falsificação habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="d61cd-105">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d61cd-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="d61cd-106">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="d61cd-107">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d61cd-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d61cd-108">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d61cd-109">As organizações com caixas de correio do Exchange Online podem configurar políticas anti-phishing no centro de conformidade & segurança ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d61cd-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="d61cd-110">As organizações do EOP autônomos só podem usar o centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="d61cd-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="d61cd-111">Para obter informações sobre como criar e modificar as políticas anti-phishing mais avançadas da ATP disponíveis no Office 365 Advanced Threat Protection (Office 365 ATP), consulte [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d61cd-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="d61cd-112">Políticas anti-phishing no centro de conformidade & segurança do vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="d61cd-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="d61cd-113">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="d61cd-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="d61cd-114">**A política de anti-golpe**: especifica as proteções de phishing a serem habilitadas ou desabilitadas e as ações para aplicar as opções.</span><span class="sxs-lookup"><span data-stu-id="d61cd-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="d61cd-115">**A regra anti-Phish**: especifica a prioridade e os filtros de destinatário (com quem a política se aplica) para uma política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="d61cd-116">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas anti-phishing no centro de conformidade & segurança:</span><span class="sxs-lookup"><span data-stu-id="d61cd-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d61cd-117">Ao criar uma política anti-phishing no centro de conformidade & segurança, na verdade você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="d61cd-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="d61cd-118">Quando você modifica uma política anti-phishing no centro de conformidade & segurança, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-Phish.</span><span class="sxs-lookup"><span data-stu-id="d61cd-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="d61cd-119">Todas as outras configurações modificam a política de anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="d61cd-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="d61cd-120">Quando você remove uma política anti-phishing do centro de conformidade & segurança, a regra anti-Phish e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="d61cd-121">No PowerShell do Exchange Online, a diferença entre políticas de anti-phishing e regras antiphish é aparente.</span><span class="sxs-lookup"><span data-stu-id="d61cd-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="d61cd-122">Você gerencia as políticas de anti-phishing usando os cmdlets \*\* \* -AntiPhishPolicy\*\* e gerencia regras de anti-phishing usando os cmdlets \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="d61cd-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="d61cd-123">No PowerShell, você cria a política de anti-phishing primeiro e, em seguida, cria a regra anti-Phish que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="d61cd-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="d61cd-124">No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-Phish separadamente.</span><span class="sxs-lookup"><span data-stu-id="d61cd-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="d61cd-125">Política anti-phishing padrão ATP</span><span class="sxs-lookup"><span data-stu-id="d61cd-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="d61cd-126">Cada organização tem uma política anti-phishing interna chamada Office365 antiphishing default que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="d61cd-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="d61cd-127">A política chamada padrão do Office365 antiphish é aplicada a todos os destinatários na organização, mesmo que não exista regra de anti-phishing (filtros de destinatário) associados à política.</span><span class="sxs-lookup"><span data-stu-id="d61cd-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="d61cd-128">A política chamada padrão do Office365 antiphish tem o valor de prioridade personalizado **mais baixo** que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="d61cd-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d61cd-129">Qualquer política personalizada que você criar sempre terá uma prioridade maior do que a política denominada padrão do Office365 antiphishing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="d61cd-130">A política denominada padrão do Office365 antiphish é a política padrão (a propriedade **IsDefault** tem o valor `True` ) e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d61cd-131">Para aumentar a eficácia da proteção contra phishing, você pode criar políticas anti-phishing personalizadas com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="d61cd-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d61cd-132">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="d61cd-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d61cd-133">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d61cd-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d61cd-134">Para ir diretamente para a página **anti-phishing** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="d61cd-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="d61cd-135">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d61cd-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="d61cd-136">Você não pode gerenciar políticas anti-phishing no PowerShell autônomo do EOP.</span><span class="sxs-lookup"><span data-stu-id="d61cd-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="d61cd-137">Você precisa receber permissões antes de executar os procedimentos deste tópico:</span><span class="sxs-lookup"><span data-stu-id="d61cd-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d61cd-138">Para adicionar, modificar e excluir políticas anti-phishing, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="d61cd-138">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d61cd-139">**Gerenciamento da organização** ou **administrador de segurança** no centro de conformidade de & de [segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d61cd-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d61cd-140">Gerenciamento da **organização** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d61cd-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d61cd-141">Para acesso somente leitura às políticas anti-phishing, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="d61cd-141">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d61cd-142">**Leitor de segurança** no [centro de conformidade & segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d61cd-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d61cd-143">**Gerenciamento de organização somente para exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d61cd-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d61cd-144">Para poder criar e modificar políticas antispam no EOP autônomo, você precisa fazer algo que exija o _hidratação_ para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d61cd-144">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="d61cd-145">Por exemplo, no centro de administração do Exchange (Eat), você pode ir para a guia **permissões** , selecionar um grupo de função existente, clicar em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) e remover uma função (que, por fim, será adicionada novamente).</span><span class="sxs-lookup"><span data-stu-id="d61cd-145">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="d61cd-146">Se seu locatário nunca tiver sido alimentado, você receberá uma caixa de diálogo chamada **Atualizar configurações da organização** com uma barra de progresso que deve ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="d61cd-146">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="d61cd-147">Para obter mais informações sobre o hidratação, consulte o cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (que não está disponível no EOP PowerShell autônomo ou no centro de conformidade & segurança).</span><span class="sxs-lookup"><span data-stu-id="d61cd-147">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="d61cd-148">Para obter as configurações recomendadas para políticas anti-phishing, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="d61cd-148">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="d61cd-149">Aguarde até 30 minutos para que a política atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="d61cd-149">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="d61cd-150">Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="d61cd-150">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="d61cd-151">Usar o centro de conformidade de & de segurança para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-151">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="d61cd-152">A criação de uma política anti-phishing personalizada no centro de conformidade & segurança cria a regra anti-phishing e a política de anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="d61cd-152">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="d61cd-153">Ao criar uma política anti-phishing, você só poderá especificar o nome da política, a descrição e o filtro de destinatário que identifique a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="d61cd-153">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="d61cd-154">Após criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-154">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="d61cd-155">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-156">Na página **anti-phishing** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-156">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="d61cd-157">O assistente para **criar uma nova política** de anti-phishing é aberto.</span><span class="sxs-lookup"><span data-stu-id="d61cd-157">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="d61cd-158">Na página **nomear sua política** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d61cd-158">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d61cd-159">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="d61cd-159">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d61cd-160">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="d61cd-160">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d61cd-161">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d61cd-162">Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="d61cd-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d61cd-163">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="d61cd-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d61cd-164">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d61cd-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d61cd-165">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d61cd-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d61cd-166">Clique em **Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-166">Click **Add a condition**.</span></span> <span data-ttu-id="d61cd-167">Na lista suspensa exibida, selecione uma condição em **aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="d61cd-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d61cd-168">**O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d61cd-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d61cd-169">**O destinatário é um membro de**: especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="d61cd-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d61cd-170">**O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="d61cd-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="d61cd-171">Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d61cd-172">Clique na caixa e role pela lista de valores para selecionar.</span><span class="sxs-lookup"><span data-stu-id="d61cd-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d61cd-173">Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d61cd-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d61cd-174">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="d61cd-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d61cd-175">Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="d61cd-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d61cd-176">Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="d61cd-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d61cd-177">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d61cd-178">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d61cd-179">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="d61cd-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d61cd-180">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-180">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d61cd-181">Na página **revise suas configurações** exibidas, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="d61cd-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d61cd-182">Você pode clicar em **Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="d61cd-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d61cd-183">Quando tiver concluído, clique em **criar esta política**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-183">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="d61cd-184">Clique em **OK** na caixa de diálogo de confirmação que aparece.</span><span class="sxs-lookup"><span data-stu-id="d61cd-184">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="d61cd-185">Após criar a política anti-phishing com essas configurações de política geral, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="d61cd-185">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="d61cd-186">Usar o centro de conformidade de & de segurança para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-186">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="d61cd-187">Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalizou.</span><span class="sxs-lookup"><span data-stu-id="d61cd-187">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="d61cd-188">Se ainda não estiver lá, abra o centro de conformidade & segurança e vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-188">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-189">Selecione a política anti-phishing personalizada que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="d61cd-189">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="d61cd-190">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="d61cd-190">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d61cd-191">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="d61cd-191">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="d61cd-192">Clicar em **Editar** em qualquer seção fornece acesso às configurações dessa seção.</span><span class="sxs-lookup"><span data-stu-id="d61cd-192">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="d61cd-193">As etapas a seguir são apresentadas na ordem em que as seções são exibidas, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="d61cd-193">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="d61cd-194">Depois de clicar em **Editar** em uma seção, as configurações disponíveis são apresentadas em um formato de assistente, mas você pode saltar dentro das páginas em qualquer ordem, e você pode clicar em **salvar** em qualquer página (ou **Cancelar** ou **fechar** ![ o ícone fechar ](../../media/scc-remove-icon.png) para retornar à página \*\*editar sua política \<name\> \*\* (não é necessário visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="d61cd-194">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="d61cd-195">**Configuração de política**: clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você [criou a política](#use-the-security--compliance-center-to-create-anti-phishing-policies) na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="d61cd-195">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="d61cd-196">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d61cd-196">**Name**</span></span>
   - <span data-ttu-id="d61cd-197">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d61cd-197">**Description**</span></span>
   - <span data-ttu-id="d61cd-198">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="d61cd-198">**Applied to**</span></span>
   - <span data-ttu-id="d61cd-199">**Revisar suas configurações**</span><span class="sxs-lookup"><span data-stu-id="d61cd-199">**Review your settings**</span></span>

   <span data-ttu-id="d61cd-200">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="d61cd-200">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="d61cd-201">**Spoof**: clique em **Editar** para ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação a ser aplicada às mensagens de remetentes falsificados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="d61cd-201">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="d61cd-202">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d61cd-202">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="d61cd-203">Observe que essas mesmas configurações também estão disponíveis nas políticas anti-phishing da ATP.</span><span class="sxs-lookup"><span data-stu-id="d61cd-203">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="d61cd-204">**Falsificação de configurações de filtro**: o valor padrão é **ativado**e recomendamos que você o deixe ligado.</span><span class="sxs-lookup"><span data-stu-id="d61cd-204">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="d61cd-205">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-205">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="d61cd-206">Para obter mais informações, consulte [Configure spoof Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="d61cd-206">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d61cd-207">Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores.</span><span class="sxs-lookup"><span data-stu-id="d61cd-207">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="d61cd-208">Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="d61cd-208">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="d61cd-209">**Habilitar o recurso de remetente não autenticado**: o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-209">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="d61cd-210">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-210">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="d61cd-211">**Ações**: Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="d61cd-211">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="d61cd-212">**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio**:</span><span class="sxs-lookup"><span data-stu-id="d61cd-212">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="d61cd-213">**Mover mensagem para pastas de lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="d61cd-213">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="d61cd-214">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="d61cd-214">**Quarantine the message**</span></span>

   - <span data-ttu-id="d61cd-215">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="d61cd-215">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="d61cd-216">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="d61cd-216">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="d61cd-217">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="d61cd-217">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="d61cd-218">**Habilitar proteção contra falsificação**</span><span class="sxs-lookup"><span data-stu-id="d61cd-218">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="d61cd-219">**Habilitar o recurso de remetente não autenticado**</span><span class="sxs-lookup"><span data-stu-id="d61cd-219">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="d61cd-220">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="d61cd-220">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="d61cd-221">Novamente na página \*\*editar sua política \<Name\> \*\* , revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-221">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="d61cd-222">Usar o centro de conformidade de & de segurança para modificar a política anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="d61cd-222">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="d61cd-223">A política anti-phishing padrão é chamada de padrão do Office365 antiphish e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-223">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="d61cd-224">Para modificar a política anti-phishing padrão, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d61cd-224">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="d61cd-225">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-225">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-226">Na página **anti-phishing** , clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-226">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="d61cd-227">A página **editar sua política padrão do Office365 antiphishing** é exibida.</span><span class="sxs-lookup"><span data-stu-id="d61cd-227">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="d61cd-228">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="d61cd-228">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="d61cd-229">**Representação**</span><span class="sxs-lookup"><span data-stu-id="d61cd-229">**Impersonation**</span></span>
   - <span data-ttu-id="d61cd-230">**Simulação**</span><span class="sxs-lookup"><span data-stu-id="d61cd-230">**Spoof**</span></span>
   - <span data-ttu-id="d61cd-231">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="d61cd-231">**Advanced settings**</span></span>

   <span data-ttu-id="d61cd-232">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="d61cd-232">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="d61cd-233">Você pode ver a seção e os valores da **configuração de política** , mas não há nenhum link de **edição** , portanto, não é possível modificar as configurações (nome da diretiva, descrição e a qual a política se aplica (ela se aplica a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="d61cd-233">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="d61cd-234">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-234">You can't delete the default policy.</span></span>
   - <span data-ttu-id="d61cd-235">Você não pode alterar a prioridade da política padrão (ela é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="d61cd-235">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="d61cd-236">Na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-236">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="d61cd-237">Habilitar ou desabilitar políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="d61cd-237">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="d61cd-238">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-239">Observe o valor na coluna **status** :</span><span class="sxs-lookup"><span data-stu-id="d61cd-239">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d61cd-240">Deslize o botão de **alternância para desativar** a política.</span><span class="sxs-lookup"><span data-stu-id="d61cd-240">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="d61cd-241">Deslize o botão de **alternância para ativar** a política.</span><span class="sxs-lookup"><span data-stu-id="d61cd-241">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="d61cd-242">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-242">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="d61cd-243">Definir a prioridade de políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="d61cd-243">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="d61cd-244">Por padrão, as políticas anti-phishing recebem uma prioridade baseada na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="d61cd-244">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="d61cd-245">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="d61cd-245">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d61cd-246">Duas políticas não podem ter a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="d61cd-246">No two policies can have the same priority.</span></span>

<span data-ttu-id="d61cd-247">Políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="d61cd-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d61cd-248">A política anti-phishing padrão chamada do Office365 antiphish padrão tem o valor de prioridade personalizado **mais baixo**e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="d61cd-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="d61cd-249">**Observação**: no centro de conformidade & segurança, você só pode alterar a prioridade da política anti-phishing após criá-la.</span><span class="sxs-lookup"><span data-stu-id="d61cd-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="d61cd-250">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-Phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="d61cd-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d61cd-251">Para alterar a prioridade de uma política, clique em **aumentar** a prioridade ou **diminuir a prioridade** nas propriedades da política (não é possível modificar diretamente o número de **prioridade** no centro de conformidade do & de segurança).</span><span class="sxs-lookup"><span data-stu-id="d61cd-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="d61cd-252">Alterar a prioridade de uma política faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="d61cd-253">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-254">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="d61cd-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="d61cd-255">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="d61cd-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d61cd-256">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="d61cd-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="d61cd-257">A política anti-phishing personalizada com o valor de **prioridade** **0** tem apenas o botão **diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="d61cd-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d61cd-258">A política anti-phishing personalizada com o menor valor de **prioridade** (por exemplo, **3**) tem apenas o botão **aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="d61cd-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d61cd-259">Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d61cd-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d61cd-260">Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="d61cd-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d61cd-261">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="d61cd-262">Usar o centro de conformidade de & de segurança para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="d61cd-263">No centro de conformidade & segurança e vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-264">Execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d61cd-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="d61cd-265">Selecione uma política anti-phishing personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d61cd-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="d61cd-266">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="d61cd-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="d61cd-267">Clique em **política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="d61cd-268">O submenu **Editar \<name\> sua política** aparece, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="d61cd-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="d61cd-269">Usar o centro de conformidade de & de segurança para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="d61cd-270">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d61cd-271">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="d61cd-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="d61cd-272">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="d61cd-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d61cd-273">No submenu **editar sua \<name\> política** exibido, clique em **excluir política**e, em seguida, clique em **Sim** na caixa de diálogo de aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="d61cd-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d61cd-274">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="d61cd-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="d61cd-275">Usar o PowerShell do Exchange Online para configurar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="d61cd-276">Os procedimentos a seguir não estão disponíveis em organizações EOP autônomas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-276">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="d61cd-277">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-277">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="d61cd-278">A criação de uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="d61cd-278">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d61cd-279">Criar a política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-279">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="d61cd-280">Crie a regra anti-Phish que especifica a política de anti-phishing à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="d61cd-280">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="d61cd-281">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="d61cd-281">**Notes**:</span></span>

- <span data-ttu-id="d61cd-282">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e não associada a ela.</span><span class="sxs-lookup"><span data-stu-id="d61cd-282">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="d61cd-283">Uma regra anti-Phish não pode ser associada a mais de uma política de phishing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-283">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="d61cd-284">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="d61cd-284">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d61cd-285">Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="d61cd-285">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="d61cd-286">Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="d61cd-286">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="d61cd-287">Uma nova política de Phish que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-287">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="d61cd-288">Etapa 1: usar o PowerShell para criar uma política de anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-288">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="d61cd-289">Para criar uma política de anti-golpe, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-289">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="d61cd-290">Este exemplo cria uma política de anti-phishing chamada quarentena de pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d61cd-290">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="d61cd-291">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="d61cd-291">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="d61cd-292">A descrição é: política de departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d61cd-292">The description is: Research department policy.</span></span>
- <span data-ttu-id="d61cd-293">Altera a ação padrão para falsificação em quarentena.</span><span class="sxs-lookup"><span data-stu-id="d61cd-293">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="d61cd-294">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="d61cd-294">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="d61cd-295">Etapa 2: usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="d61cd-295">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="d61cd-296">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-296">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d61cd-297">Este exemplo cria uma regra anti-phishing chamada departamento de pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="d61cd-297">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="d61cd-298">A regra é associada à política de anti-phishing chamada quarentena de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d61cd-298">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="d61cd-299">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d61cd-299">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="d61cd-300">Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="d61cd-300">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="d61cd-301">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="d61cd-301">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="d61cd-302">Usar o PowerShell para exibir políticas antispam</span><span class="sxs-lookup"><span data-stu-id="d61cd-302">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="d61cd-303">Para exibir as políticas antispam existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-303">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d61cd-304">Este exemplo retorna uma lista resumida de todas as políticas de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-304">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="d61cd-305">Este exemplo retorna todos os valores de propriedade da política anti-Phish chamada executivos.</span><span class="sxs-lookup"><span data-stu-id="d61cd-305">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="d61cd-306">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="d61cd-306">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="d61cd-307">Usar o PowerShell para exibir regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="d61cd-307">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="d61cd-308">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-308">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d61cd-309">Este exemplo retorna uma lista resumida de todas as regras de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="d61cd-309">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="d61cd-310">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="d61cd-310">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="d61cd-311">Este exemplo retorna todos os valores de propriedade da regra anti-Phish chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="d61cd-311">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="d61cd-312">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="d61cd-312">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="d61cd-313">Usar o PowerShell para modificar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="d61cd-313">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="d61cd-314">Além dos seguintes itens, as mesmas configurações estão disponíveis quando você modifica uma política de anti-phishing no PowerShell como quando você cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anti-golpe](#step-1-use-powershell-to-create-an-anti-phish-policy) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d61cd-314">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="d61cd-315">A opção _MakeDefault_ que transforma a política especificada na política padrão (aplicada a todos, sempre a prioridade **mais baixa** e não é possível excluí-la) só está disponível quando você modifica uma política de Phish no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d61cd-315">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="d61cd-316">Não é possível renomear uma política anti-phishing (o cmdlet **set-AntiPhishPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="d61cd-316">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d61cd-317">Ao renomear uma política anti-phishing no centro de conformidade & segurança, você estará apenas renomeando a _regra_anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-317">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="d61cd-318">Para modificar uma política de anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-318">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d61cd-319">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="d61cd-319">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="d61cd-320">Usar o PowerShell para modificar as regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="d61cd-320">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="d61cd-321">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite que você crie uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="d61cd-321">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d61cd-322">Para habilitar ou desabilitar regras antispam existentes, confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="d61cd-322">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="d61cd-323">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d61cd-323">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="d61cd-324">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d61cd-324">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="d61cd-325">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-325">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d61cd-326">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="d61cd-326">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="d61cd-327">Usar o PowerShell para habilitar ou desabilitar regras de Phish</span><span class="sxs-lookup"><span data-stu-id="d61cd-327">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="d61cd-328">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política de anti-phishing atribuídas).</span><span class="sxs-lookup"><span data-stu-id="d61cd-328">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="d61cd-329">Você não pode habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="d61cd-329">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="d61cd-330">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-330">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="d61cd-331">Este exemplo desabilita a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-331">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d61cd-332">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="d61cd-332">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d61cd-333">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="d61cd-333">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="d61cd-334">Usar o PowerShell para definir a prioridade de regras de Phish</span><span class="sxs-lookup"><span data-stu-id="d61cd-334">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="d61cd-335">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="d61cd-335">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d61cd-336">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="d61cd-336">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d61cd-337">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="d61cd-337">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d61cd-338">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="d61cd-338">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d61cd-339">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="d61cd-339">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d61cd-340">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-340">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d61cd-341">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="d61cd-341">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d61cd-342">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="d61cd-342">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d61cd-343">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="d61cd-343">**Notes**:</span></span>

- <span data-ttu-id="d61cd-344">Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="d61cd-344">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="d61cd-345">A política de anti-phishing padrão não tem uma regra antiphishing correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="d61cd-345">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="d61cd-346">Usar o PowerShell para remover políticas antispam</span><span class="sxs-lookup"><span data-stu-id="d61cd-346">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="d61cd-347">Quando você usa o PowerShell para remover uma política de Phish, a regra anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="d61cd-347">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="d61cd-348">Para remover uma política de anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-348">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d61cd-349">Este exemplo remove a política de anti-golpe chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-349">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d61cd-350">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="d61cd-350">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="d61cd-351">Usar o PowerShell para remover regras de Phish</span><span class="sxs-lookup"><span data-stu-id="d61cd-351">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="d61cd-352">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="d61cd-352">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="d61cd-353">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d61cd-353">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="d61cd-354">Este exemplo remove a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="d61cd-354">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d61cd-355">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="d61cd-355">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d61cd-356">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="d61cd-356">How do you know these procedures worked?</span></span>

<span data-ttu-id="d61cd-357">Para verificar se você configurou com êxito as políticas de anti-phishing do ATP, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d61cd-357">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="d61cd-358">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **anti-phishing**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d61cd-358">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="d61cd-359">Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="d61cd-359">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d61cd-360">Para exibir mais detalhes, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d61cd-360">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="d61cd-361">Selecione a política na lista e exiba os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="d61cd-361">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="d61cd-362">Clique em **política padrão** e visualize os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="d61cd-362">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="d61cd-363">No PowerShell do Exchange Online, substitua \<Name\> o nome da política ou regra e execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="d61cd-363">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
