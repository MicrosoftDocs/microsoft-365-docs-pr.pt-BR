---
title: Configurar políticas anti-phishing ATP
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
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing avançadas disponíveis em organizações com a proteção avançada contra ameaças do Office 365 (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726771"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-103">Configurar políticas anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="01b09-104">As políticas de anti-phishing do ATP fazem parte da [proteção avançada contra ameaças do Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="01b09-105">As políticas de anti-phishing do ATP podem ajudar a proteger sua organização contra ataques de phishing baseados em personificação mal-intencionada e outros tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="01b09-106">Para obter mais informações sobre as diferenças entre políticas anti-phishing no Exchange Online Protection (EOP) e nas políticas de anti-phishing do ATP, consulte [proteção contra phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="01b09-107">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão da ATP.</span><span class="sxs-lookup"><span data-stu-id="01b09-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="01b09-108">Para obter uma granularidade maior, você também pode criar políticas anti-phishing personalizadas da ATP que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="01b09-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="01b09-109">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="01b09-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="01b09-110">Você pode configurar as políticas de anti-phishing do ATP no centro de conformidade & segurança ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="01b09-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="01b09-111">Para obter informações sobre como configurar o mais limitado em políticas anti-phishing que estão disponíveis em organizações do Exchange Online Protection (ou seja, Microsoft 365, organizações sem o Office 365 ATP), consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="01b09-112">Políticas de anti-phishing do ATP no centro de conformidade e segurança & vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="01b09-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="01b09-113">Os elementos básicos de uma política anti-phishing do ATP são:</span><span class="sxs-lookup"><span data-stu-id="01b09-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="01b09-114">**A política de anti-golpe**: especifica as proteções de phishing a serem habilitadas ou desabilitadas e as ações para aplicar as opções.</span><span class="sxs-lookup"><span data-stu-id="01b09-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="01b09-115">**A regra anti-Phish**: especifica a prioridade e os filtros de destinatário (com quem a política se aplica) para uma política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="01b09-116">A diferença entre esses dois elementos não é óbvia quando você gerencia as políticas de anti-phishing do ATP no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="01b09-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="01b09-117">Ao criar uma política de anti-phishing do ATP no centro de conformidade de & de segurança, você está realmente criando uma regra anti-phishing e a política de anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="01b09-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="01b09-118">Quando você modifica uma política de anti-phishing do ATP no centro de conformidade de & de segurança, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="01b09-119">Todas as outras configurações modificam a política de anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="01b09-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="01b09-120">Quando você remove uma política anti-phishing do ATP do centro de conformidade & segurança, a regra anti-Phish e a política de anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="01b09-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="01b09-121">No PowerShell do Exchange Online, a diferença entre políticas de anti-phishing e regras antiphish é aparente.</span><span class="sxs-lookup"><span data-stu-id="01b09-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="01b09-122">Você gerencia as políticas de anti-phishing usando os cmdlets \*\* \* -AntiPhishPolicy\*\* e gerencia regras de anti-phishing usando os cmdlets \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="01b09-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="01b09-123">No PowerShell, você cria a política de anti-phishing primeiro e, em seguida, cria a regra anti-Phish que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="01b09-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="01b09-124">No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-Phish separadamente.</span><span class="sxs-lookup"><span data-stu-id="01b09-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="01b09-125">Quando você remove uma política de anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="01b09-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="01b09-126">Política anti-phishing padrão ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="01b09-127">Todas as organizações ATP têm uma política antiphishing interna da ATP chamada de padrão do Office365 antiphish que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="01b09-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="01b09-128">A política de anti-phishing chamada padrão do Office365 antiphish é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de Phish (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="01b09-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="01b09-129">A política chamada padrão do Office365 antiphish tem o valor de prioridade personalizado **mais baixo** que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="01b09-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="01b09-130">Qualquer política personalizada que você criar sempre terá uma prioridade maior do que a política denominada padrão do Office365 antiphishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="01b09-131">A política denominada padrão do Office365 antiphish é a política padrão (a propriedade **IsDefault** tem o valor `True` ) e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="01b09-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="01b09-132">Para aumentar a eficácia da proteção contra phishing, você pode criar políticas anti-phishing personalizadas da ATP com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="01b09-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="01b09-133">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="01b09-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="01b09-134">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="01b09-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="01b09-135">Para ir diretamente para a página de **anti-phishing do ATP** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="01b09-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="01b09-136">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="01b09-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="01b09-137">Você precisa receber permissões antes de executar os procedimentos deste tópico:</span><span class="sxs-lookup"><span data-stu-id="01b09-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="01b09-138">Para adicionar, modificar e excluir as políticas de anti-phishing do ATP, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="01b09-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="01b09-139">**Gerenciamento da organização** ou **administrador de segurança** no centro de conformidade de & de [segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="01b09-140">Gerenciamento da **organização** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="01b09-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="01b09-141">Para acesso somente leitura às políticas anti-phishing da ATP, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="01b09-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="01b09-142">**Leitor de segurança** no [centro de conformidade & segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="01b09-143">**Gerenciamento de organização somente para exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="01b09-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="01b09-144">Para obter as configurações recomendadas para políticas de anti-phishing da ATP, confira [configurações de política de anti-phishing do Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="01b09-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="01b09-145">Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="01b09-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="01b09-146">Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-147">Usar o centro de conformidade de & de segurança para criar políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="01b09-148">Criar uma política antivírus ATP personalizada no centro de conformidade de & de segurança cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="01b09-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="01b09-149">Ao criar uma política anti-phishing do ATP, você só pode especificar o nome da política, a descrição e o filtro de destinatário que identifica a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="01b09-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="01b09-150">Após criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="01b09-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="01b09-151">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-152">Na página **anti-phishing** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="01b09-153">O assistente para **criar uma nova política** de anti-phishing é aberto.</span><span class="sxs-lookup"><span data-stu-id="01b09-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="01b09-154">Na página **nomear sua política** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="01b09-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="01b09-155">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="01b09-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="01b09-156">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="01b09-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="01b09-157">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="01b09-158">Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="01b09-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="01b09-159">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="01b09-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="01b09-160">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="01b09-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="01b09-161">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="01b09-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="01b09-162">Clique em **Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="01b09-162">Click **Add a condition**.</span></span> <span data-ttu-id="01b09-163">Na lista suspensa exibida, selecione uma condição em **aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="01b09-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="01b09-164">**O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="01b09-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="01b09-165">**O destinatário é um membro de**: especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="01b09-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="01b09-166">**O domínio do destinatário é**: especifica destinatários em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="01b09-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="01b09-167">Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.</span><span class="sxs-lookup"><span data-stu-id="01b09-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="01b09-168">Clique na caixa e role pela lista de valores para selecionar.</span><span class="sxs-lookup"><span data-stu-id="01b09-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="01b09-169">Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="01b09-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="01b09-170">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="01b09-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="01b09-171">Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="01b09-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="01b09-172">Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="01b09-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="01b09-173">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.</span><span class="sxs-lookup"><span data-stu-id="01b09-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="01b09-174">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**.</span><span class="sxs-lookup"><span data-stu-id="01b09-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="01b09-175">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="01b09-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="01b09-176">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="01b09-177">Na página **revise suas configurações** exibidas, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="01b09-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="01b09-178">Você pode clicar em **Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="01b09-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="01b09-179">Quando tiver concluído, clique em **criar esta política**.</span><span class="sxs-lookup"><span data-stu-id="01b09-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="01b09-180">Clique em **OK** na caixa de diálogo de confirmação que aparece.</span><span class="sxs-lookup"><span data-stu-id="01b09-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="01b09-181">Após criar a política anti-phishing do ATP com estas configurações gerais de política, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="01b09-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-182">Usar o centro de conformidade de & de segurança para modificar as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="01b09-183">Use os procedimentos a seguir para modificar as políticas de anti-phishing do ATP: uma nova política que você criou ou políticas existentes que você já personalizou.</span><span class="sxs-lookup"><span data-stu-id="01b09-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="01b09-184">Se você ainda não estiver lá, abra o centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-phishing da ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-185">Selecione a política de anti-phishing padrão ATP que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="01b09-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="01b09-186">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="01b09-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="01b09-187">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="01b09-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="01b09-188">Clicar em **Editar** em qualquer seção fornece acesso às configurações dessa seção.</span><span class="sxs-lookup"><span data-stu-id="01b09-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="01b09-189">As etapas a seguir são apresentadas na ordem em que as seções são exibidas, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="01b09-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="01b09-190">Depois de clicar em **Editar** em uma seção, as configurações disponíveis são apresentadas em um formato de assistente, mas você pode saltar dentro das páginas em qualquer ordem, e você pode clicar em **salvar** em qualquer página (ou **Cancelar** ou **fechar** ![ o ícone fechar ](../../media/scc-remove-icon.png) para retornar à página \*\*editar sua política \<name\> \*\* (não é necessário visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="01b09-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="01b09-191">**Configuração de política**: clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você [criou a política](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="01b09-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="01b09-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="01b09-192">**Name**</span></span>
   - <span data-ttu-id="01b09-193">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="01b09-193">**Description**</span></span>
   - <span data-ttu-id="01b09-194">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="01b09-194">**Applied to**</span></span>
   - <span data-ttu-id="01b09-195">**Revisar suas configurações**</span><span class="sxs-lookup"><span data-stu-id="01b09-195">**Review your settings**</span></span>

   <span data-ttu-id="01b09-196">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="01b09-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="01b09-197">**Representação**: clique em **Editar** para modificar os remetentes protegidos e os domínios protegidos na política.</span><span class="sxs-lookup"><span data-stu-id="01b09-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="01b09-198">Essas configurações são uma condição para a política que identifica remetentes falsificados a serem procurados (individualmente ou por domínio) no endereço de das mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="01b09-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="01b09-199">Para obter mais informações, consulte [configurações de representação em políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="01b09-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="01b09-200">**Adicionar usuários para proteger**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="01b09-201">Para ativá-la, deslize o botão de alternância para **ativado**e, em seguida, clique no botão **Adicionar usuário** que aparece.</span><span class="sxs-lookup"><span data-stu-id="01b09-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="01b09-202">No submenu **Adicionar usuário** exibido, configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="01b09-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="01b09-203">**Endereço de email**:</span><span class="sxs-lookup"><span data-stu-id="01b09-203">**Email address**:</span></span>

        - <span data-ttu-id="01b09-204">Clique na caixa e role pela lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="01b09-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="01b09-205">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="01b09-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="01b09-206">Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.</span><span class="sxs-lookup"><span data-stu-id="01b09-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="01b09-207">**Nome**: esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="01b09-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="01b09-208">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="01b09-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="01b09-209">Para editar uma entrada existente, selecione o usuário protegido na lista.</span><span class="sxs-lookup"><span data-stu-id="01b09-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="01b09-210">**Adicionar domínios para proteger**: Configure uma ou ambas as configurações a seguir:</span><span class="sxs-lookup"><span data-stu-id="01b09-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="01b09-211">**Incluir automaticamente os domínios que**possuo: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="01b09-212">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="01b09-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="01b09-213">**Incluir domínios personalizados**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="01b09-214">Para ativá-la, deslize o **botão para ativar e,** na caixa **adicionar domínios** , digite o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="01b09-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="01b09-215">**Ações**: clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="01b09-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="01b09-216">**Se o email for enviado por um usuário representado**: Configure uma das ações a seguir para mensagens em que o remetente falsificado é um dos usuários protegidos que você especificou em **Adicionar usuários para proteger**:</span><span class="sxs-lookup"><span data-stu-id="01b09-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="01b09-217">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="01b09-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="01b09-218">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="01b09-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="01b09-219">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="01b09-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="01b09-220">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="01b09-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="01b09-221">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="01b09-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="01b09-222">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="01b09-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="01b09-223">**Se o email for enviado por um domínio representado**: Configure uma das ações a seguir para mensagens em que o remetente falsificado está em um dos domínios protegidos que você especificou em **adicionar domínios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="01b09-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="01b09-224">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="01b09-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="01b09-225">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="01b09-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="01b09-226">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="01b09-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="01b09-227">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="01b09-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="01b09-228">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="01b09-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="01b09-229">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="01b09-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="01b09-230">Clique em **Ativar dicas de segurança de representação** e configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="01b09-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="01b09-231">**Mostrar dica para usuários representados**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="01b09-232">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="01b09-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="01b09-233">**Mostrar dica para domínios representados**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="01b09-234">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="01b09-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="01b09-235">**Mostrar dica para caracteres incomuns**: o valor padrão está **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="01b09-236">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="01b09-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="01b09-237">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="01b09-238">**Inteligência de caixa de correio**:</span><span class="sxs-lookup"><span data-stu-id="01b09-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="01b09-239">**Habilitar o Mailbox Intelligence?**: o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="01b09-240">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="01b09-241">**Habilitar proteção de representação baseada em inteligência de caixa de correio?**: essa configuração só estará disponível se **habilitar inteligência de caixa de correio?** estiver **ativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="01b09-242">Em **se o email for enviado por um usuário representado**, você poderá especificar uma das ações a seguir para executar as mensagens que falham na inteligência de caixa de correio (as mesmas ações que estão disponíveis para usuários protegidos e domínios protegidos):</span><span class="sxs-lookup"><span data-stu-id="01b09-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="01b09-243">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="01b09-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="01b09-244">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="01b09-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="01b09-245">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="01b09-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="01b09-246">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="01b09-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="01b09-247">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="01b09-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="01b09-248">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="01b09-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="01b09-249">**Adicionar remetentes e domínios confiáveis**: especifique exceções para a política:</span><span class="sxs-lookup"><span data-stu-id="01b09-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="01b09-250">**Remetentes confiáveis**:</span><span class="sxs-lookup"><span data-stu-id="01b09-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="01b09-251">Clique na caixa e role pela lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="01b09-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="01b09-252">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="01b09-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="01b09-253">Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.</span><span class="sxs-lookup"><span data-stu-id="01b09-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="01b09-254">**Domínios confiáveis**: Insira o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="01b09-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="01b09-255">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="01b09-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="01b09-256">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="01b09-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="01b09-257">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="01b09-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="01b09-258">**Usuários protegidos**</span><span class="sxs-lookup"><span data-stu-id="01b09-258">**Protected users**</span></span>
       - <span data-ttu-id="01b09-259">**Domínios protegidos** \> **Incluir domínios que sou proprietário**</span><span class="sxs-lookup"><span data-stu-id="01b09-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="01b09-260">**Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)</span><span class="sxs-lookup"><span data-stu-id="01b09-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="01b09-261">**Inteligência da caixa de correio**</span><span class="sxs-lookup"><span data-stu-id="01b09-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="01b09-262">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="01b09-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="01b09-263">**Spoof**: clique em **Editar** para ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação a ser aplicada às mensagens de remetentes falsificados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="01b09-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="01b09-264">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="01b09-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="01b09-265">Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.</span><span class="sxs-lookup"><span data-stu-id="01b09-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="01b09-266">**Falsificação de configurações de filtro**: o valor padrão é **ativado**e recomendamos que você o deixe ligado.</span><span class="sxs-lookup"><span data-stu-id="01b09-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="01b09-267">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="01b09-268">Para obter mais informações, consulte [Configure spoof Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="01b09-269">Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores.</span><span class="sxs-lookup"><span data-stu-id="01b09-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="01b09-270">Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="01b09-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="01b09-271">**Habilitar o recurso de remetente não autenticado**: o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="01b09-272">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="01b09-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="01b09-273">**Ações**: Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="01b09-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="01b09-274">**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio**:</span><span class="sxs-lookup"><span data-stu-id="01b09-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="01b09-275">**Mover mensagem para pastas de lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="01b09-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="01b09-276">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="01b09-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="01b09-277">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="01b09-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="01b09-278">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="01b09-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="01b09-279">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="01b09-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="01b09-280">**Habilitar proteção contra falsificação**</span><span class="sxs-lookup"><span data-stu-id="01b09-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="01b09-281">**Habilitar o recurso de remetente não autenticado**</span><span class="sxs-lookup"><span data-stu-id="01b09-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="01b09-282">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="01b09-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="01b09-283">**Configurações avançadas**: clique em **Editar** para configurar os limites avançados de phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="01b09-284">Para obter mais informações, consulte [limites de phishing avançados nas políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="01b09-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="01b09-285">**Limites de phishing avançados**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="01b09-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="01b09-286">**1-padrão** (este é o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="01b09-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="01b09-287">**2-agressivo**</span><span class="sxs-lookup"><span data-stu-id="01b09-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="01b09-288">**3-mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="01b09-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="01b09-289">**4-mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="01b09-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="01b09-290">**Revise suas configurações**: clique em **Editar** para voltar para a página de **limiares de phishing avançados** .</span><span class="sxs-lookup"><span data-stu-id="01b09-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="01b09-291">Quando tiver terminado, clique em **salvar** em qualquer uma das páginas.</span><span class="sxs-lookup"><span data-stu-id="01b09-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="01b09-292">Novamente na página \*\*editar sua política \<Name\> \*\* , revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="01b09-293">Usar o centro de conformidade de & de segurança para modificar a política de anti-phishing padrão ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="01b09-294">A política anti-phishing padrão ATP é chamada de padrão do Office365 antiphish, e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="01b09-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="01b09-295">Para modificar a política anti-phishing padrão da ATP, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="01b09-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="01b09-296">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-297">Na página **anti-phishing** , clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="01b09-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="01b09-298">A página **editar sua política padrão do Office365 antiphishing** é exibida.</span><span class="sxs-lookup"><span data-stu-id="01b09-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="01b09-299">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="01b09-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="01b09-300">**Representação**</span><span class="sxs-lookup"><span data-stu-id="01b09-300">**Impersonation**</span></span>
   - <span data-ttu-id="01b09-301">**Simulação**</span><span class="sxs-lookup"><span data-stu-id="01b09-301">**Spoof**</span></span>
   - <span data-ttu-id="01b09-302">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="01b09-302">**Advanced settings**</span></span>

   <span data-ttu-id="01b09-303">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="01b09-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="01b09-304">Você pode ver a seção e os valores da **configuração de política** , mas não há nenhum link de **edição** , portanto, não é possível modificar as configurações (nome da diretiva, descrição e a qual a política se aplica (ela se aplica a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="01b09-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="01b09-305">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="01b09-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="01b09-306">Você não pode alterar a prioridade da política padrão (ela é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="01b09-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="01b09-307">Na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-308">Habilitar ou desabilitar políticas antivírus ATP personalizadas</span><span class="sxs-lookup"><span data-stu-id="01b09-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="01b09-309">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-310">Observe o valor na coluna **status** :</span><span class="sxs-lookup"><span data-stu-id="01b09-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="01b09-311">Deslize o botão de **alternância para desativar** a política.</span><span class="sxs-lookup"><span data-stu-id="01b09-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="01b09-312">Deslize o botão de **alternância para ativar** a política.</span><span class="sxs-lookup"><span data-stu-id="01b09-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="01b09-313">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="01b09-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-314">Definir a prioridade de políticas anti-phishing padrão da ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="01b09-315">Por padrão, as políticas anti-phishing do ATP recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="01b09-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="01b09-316">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="01b09-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="01b09-317">Duas políticas não podem ter a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="01b09-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="01b09-318">As políticas anti-phishing padrão ATP são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="01b09-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="01b09-319">A política anti-phishing padrão chamada do Office365 antiphish padrão tem o valor de prioridade personalizado **mais baixo**e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="01b09-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="01b09-320">**Observação**: no centro de conformidade & segurança, você só pode alterar a prioridade da política anti-phishing do ATP após criá-la.</span><span class="sxs-lookup"><span data-stu-id="01b09-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="01b09-321">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-Phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="01b09-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="01b09-322">Para alterar a prioridade de uma política, clique em **aumentar** a prioridade ou **diminuir a prioridade** nas propriedades da política (não é possível modificar diretamente o número de **prioridade** no centro de conformidade do & de segurança).</span><span class="sxs-lookup"><span data-stu-id="01b09-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="01b09-323">Alterar a prioridade de uma política faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="01b09-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="01b09-324">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-325">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="01b09-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="01b09-326">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="01b09-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="01b09-327">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="01b09-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="01b09-328">A política de anti-phishing padrão ATP com o valor **Priority** de prioridade **0** tem apenas o botão **diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="01b09-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="01b09-329">A política de anti-phishing padrão ATP com o menor valor de **prioridade** (por exemplo, **3**) tem apenas o botão **aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="01b09-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="01b09-330">Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="01b09-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="01b09-331">Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="01b09-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="01b09-332">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="01b09-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-333">Usar o centro de conformidade de & de segurança para exibir as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="01b09-334">No centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-335">Execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="01b09-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="01b09-336">Selecione uma política antivírus ATP personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="01b09-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="01b09-337">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="01b09-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="01b09-338">Clique em **política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="01b09-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="01b09-339">O submenu **Editar \<name\> sua política** aparece, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="01b09-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-340">Usar o centro de conformidade de & de segurança para remover as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="01b09-341">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="01b09-342">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="01b09-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="01b09-343">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="01b09-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="01b09-344">No submenu **editar sua \<name\> política** exibido, clique em **excluir política**e, em seguida, clique em **Sim** na caixa de diálogo de aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="01b09-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="01b09-345">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="01b09-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="01b09-346">Usar o PowerShell do Exchange Online para configurar as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="01b09-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="01b09-347">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="01b09-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="01b09-348">A criação de uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="01b09-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="01b09-349">Criar a política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="01b09-350">Crie a regra anti-Phish que especifica a política de anti-phishing à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="01b09-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="01b09-351">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="01b09-351">**Notes**:</span></span>

- <span data-ttu-id="01b09-352">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e não associada a ela.</span><span class="sxs-lookup"><span data-stu-id="01b09-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="01b09-353">Uma regra anti-Phish não pode ser associada a mais de uma política de phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="01b09-354">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="01b09-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="01b09-355">Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="01b09-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="01b09-356">Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="01b09-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="01b09-357">Uma nova política de Phish que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="01b09-358">Etapa 1: usar o PowerShell para criar uma política de anti-phishing</span><span class="sxs-lookup"><span data-stu-id="01b09-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="01b09-359">Para criar uma política de anti-golpe, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="01b09-360">Este exemplo cria uma política de anti-phishing chamada quarentena de pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="01b09-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="01b09-361">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="01b09-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="01b09-362">A descrição é: política de departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="01b09-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="01b09-363">Habilita a proteção de domínios de organização para todos os domínios aceitos e proteção de domínios direcionados para o fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="01b09-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="01b09-364">Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário para proteger da representação.</span><span class="sxs-lookup"><span data-stu-id="01b09-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="01b09-365">Habilita a inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="01b09-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="01b09-366">Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.</span><span class="sxs-lookup"><span data-stu-id="01b09-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="01b09-367">Permite dicas de segurança.</span><span class="sxs-lookup"><span data-stu-id="01b09-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="01b09-368">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="01b09-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="01b09-369">Etapa 2: usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="01b09-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="01b09-370">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="01b09-371">Este exemplo cria uma regra anti-phishing chamada departamento de pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="01b09-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="01b09-372">A regra é associada à política de anti-phishing chamada quarentena de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="01b09-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="01b09-373">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="01b09-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="01b09-374">Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="01b09-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="01b09-375">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="01b09-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="01b09-376">Usar o PowerShell para exibir políticas antispam</span><span class="sxs-lookup"><span data-stu-id="01b09-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="01b09-377">Para exibir as políticas antispam existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="01b09-378">Este exemplo retorna uma lista resumida de todas as políticas de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="01b09-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="01b09-379">Este exemplo retorna todos os valores de propriedade da política anti-Phish chamada executivos.</span><span class="sxs-lookup"><span data-stu-id="01b09-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="01b09-380">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="01b09-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="01b09-381">Usar o PowerShell para exibir regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="01b09-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="01b09-382">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="01b09-383">Este exemplo retorna uma lista resumida de todas as regras de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="01b09-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="01b09-384">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="01b09-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="01b09-385">Este exemplo retorna todos os valores de propriedade da regra anti-Phish chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="01b09-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="01b09-386">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="01b09-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="01b09-387">Usar o PowerShell para modificar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="01b09-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="01b09-388">Além dos seguintes itens, as mesmas configurações estão disponíveis quando você modifica uma política de anti-phishing no PowerShell como quando você cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anti-golpe](#step-1-use-powershell-to-create-an-anti-phish-policy) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="01b09-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="01b09-389">A opção _MakeDefault_ que transforma a política especificada na política padrão (aplicada a todos, sempre a prioridade **mais baixa** e não é possível excluí-la) só está disponível quando você modifica uma política de Phish no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01b09-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="01b09-390">Não é possível renomear uma política anti-phishing (o cmdlet **set-AntiPhishPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="01b09-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="01b09-391">Ao renomear uma política anti-phishing no centro de conformidade & segurança, você estará apenas renomeando a _regra_anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="01b09-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="01b09-392">Para modificar uma política de anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="01b09-393">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="01b09-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="01b09-394">Usar o PowerShell para modificar as regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="01b09-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="01b09-395">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite que você crie uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="01b09-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="01b09-396">Para habilitar ou desabilitar regras antispam existentes, confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="01b09-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="01b09-397">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01b09-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="01b09-398">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="01b09-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="01b09-399">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="01b09-400">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="01b09-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="01b09-401">Usar o PowerShell para habilitar ou desabilitar regras de Phish</span><span class="sxs-lookup"><span data-stu-id="01b09-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="01b09-402">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política de anti-phishing atribuídas).</span><span class="sxs-lookup"><span data-stu-id="01b09-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="01b09-403">Você não pode habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="01b09-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="01b09-404">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="01b09-405">Este exemplo desabilita a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="01b09-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="01b09-406">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="01b09-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="01b09-407">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="01b09-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="01b09-408">Usar o PowerShell para definir a prioridade de regras de Phish</span><span class="sxs-lookup"><span data-stu-id="01b09-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="01b09-409">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="01b09-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="01b09-410">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="01b09-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="01b09-411">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="01b09-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="01b09-412">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="01b09-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="01b09-413">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="01b09-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="01b09-414">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="01b09-415">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="01b09-415">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="01b09-416">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="01b09-416">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="01b09-417">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="01b09-417">**Notes**:</span></span>

- <span data-ttu-id="01b09-418">Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="01b09-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="01b09-419">A política de anti-phishing padrão não tem uma regra antiphishing correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="01b09-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="01b09-420">Usar o PowerShell para remover políticas antispam</span><span class="sxs-lookup"><span data-stu-id="01b09-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="01b09-421">Quando você usa o PowerShell para remover uma política de Phish, a regra anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="01b09-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="01b09-422">Para remover uma política de anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="01b09-423">Este exemplo remove a política de anti-golpe chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="01b09-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="01b09-424">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="01b09-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="01b09-425">Usar o PowerShell para remover regras de Phish</span><span class="sxs-lookup"><span data-stu-id="01b09-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="01b09-426">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="01b09-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="01b09-427">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01b09-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="01b09-428">Este exemplo remove a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="01b09-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="01b09-429">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="01b09-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="01b09-430">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="01b09-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="01b09-431">Para verificar se você configurou com êxito as políticas de anti-phishing do ATP, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="01b09-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="01b09-432">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="01b09-433">Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="01b09-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="01b09-434">Para exibir mais detalhes, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="01b09-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="01b09-435">Selecione a política na lista e exiba os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="01b09-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="01b09-436">Clique em **política padrão** e visualize os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="01b09-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="01b09-437">No PowerShell do Exchange Online, substitua \<Name\> o nome da política ou regra e execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="01b09-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
