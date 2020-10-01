---
title: Configurar políticas anti-phishing ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing avançadas disponíveis em organizações com a proteção avançada contra ameaças do Office 365 (Office 365 ATP).
ms.openlocfilehash: 2986102b549b7302a7a4ac533f80846d832aeb41
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328066"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-103">Configurar políticas anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="135dd-104">As políticas de anti-phishing do ATP fazem parte da [proteção avançada contra ameaças do Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="135dd-105">As políticas de anti-phishing do ATP podem ajudar a proteger sua organização contra ataques de phishing baseados em personificação mal-intencionada e outros tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="135dd-106">Para obter mais informações sobre as diferenças entre políticas anti-phishing no Exchange Online Protection (EOP) e nas políticas de anti-phishing do ATP, consulte [proteção contra phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="135dd-107">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão da ATP.</span><span class="sxs-lookup"><span data-stu-id="135dd-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="135dd-108">Para obter uma granularidade maior, você também pode criar políticas anti-phishing personalizadas da ATP que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="135dd-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="135dd-109">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="135dd-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="135dd-110">Você pode configurar as políticas de anti-phishing do ATP no centro de conformidade & segurança ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="135dd-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="135dd-111">Para obter informações sobre como configurar o mais limitado em políticas anti-phishing que estão disponíveis em organizações do Exchange Online Protection (ou seja, Microsoft 365, organizações sem o Office 365 ATP), consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="135dd-112">Políticas de anti-phishing do ATP no centro de conformidade e segurança & vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="135dd-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="135dd-113">Os elementos básicos de uma política anti-phishing do ATP são:</span><span class="sxs-lookup"><span data-stu-id="135dd-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="135dd-114">**A política de anti-golpe**: especifica as proteções de phishing a serem habilitadas ou desabilitadas e as ações para aplicar as opções.</span><span class="sxs-lookup"><span data-stu-id="135dd-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="135dd-115">**A regra anti-Phish**: especifica a prioridade e os filtros de destinatário (com quem a política se aplica) para uma política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="135dd-116">A diferença entre esses dois elementos não é óbvia quando você gerencia as políticas de anti-phishing do ATP no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="135dd-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="135dd-117">Ao criar uma política, você realmente está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="135dd-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="135dd-118">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="135dd-119">Todas as outras configurações modificam a política de anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="135dd-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="135dd-120">Quando você remove uma política, a regra anti-Phish e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="135dd-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="135dd-121">No PowerShell do Exchange Online, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="135dd-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="135dd-122">Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online para configurar as políticas de anti-phishing do ATP](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="135dd-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="135dd-123">Todas as organizações do Office 365 ATP têm uma política anti-phishing interna da ATP chamada Office365 antiphishing default que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="135dd-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="135dd-124">A política é aplicada a todos os destinatários na organização, mesmo que não haja uma regra de anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="135dd-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="135dd-125">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="135dd-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="135dd-126">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="135dd-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="135dd-127">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="135dd-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="135dd-128">Para aumentar a eficácia da proteção contra phishing, você pode criar políticas anti-phishing personalizadas da ATP com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="135dd-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="135dd-129">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="135dd-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="135dd-130">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="135dd-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="135dd-131">Para ir diretamente para a página de **anti-phishing do ATP** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="135dd-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="135dd-132">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="135dd-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="135dd-133">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="135dd-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="135dd-134">Para adicionar, modificar e excluir as políticas de anti-phishing do ATP, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="135dd-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="135dd-135">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="135dd-136">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="135dd-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="135dd-137">Para acesso somente leitura às políticas anti-phishing da ATP, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="135dd-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="135dd-138">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="135dd-139">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="135dd-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="135dd-140">Para obter as configurações recomendadas para políticas de anti-phishing da ATP, consulte [ATP anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="135dd-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="135dd-141">Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="135dd-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="135dd-142">Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-143">Usar o centro de conformidade de & de segurança para criar políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="135dd-144">Criar uma política antivírus ATP personalizada no centro de conformidade de & de segurança cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="135dd-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="135dd-145">Ao criar uma política anti-phishing do ATP, você só pode especificar o nome da política, a descrição e o filtro de destinatário que identifica a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="135dd-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="135dd-146">Após criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="135dd-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="135dd-147">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-148">Na página **anti-phishing** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="135dd-149">O assistente para **criar uma nova política** de anti-phishing é aberto.</span><span class="sxs-lookup"><span data-stu-id="135dd-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="135dd-150">Na página **nomear sua política** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="135dd-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="135dd-151">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="135dd-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="135dd-152">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="135dd-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="135dd-153">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="135dd-154">Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="135dd-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="135dd-155">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="135dd-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="135dd-156">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="135dd-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="135dd-157">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="135dd-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="135dd-158">Clique em **Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="135dd-158">Click **Add a condition**.</span></span> <span data-ttu-id="135dd-159">Na lista suspensa exibida, selecione uma condição em **aplicado se**:</span><span class="sxs-lookup"><span data-stu-id="135dd-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="135dd-160">**O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="135dd-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="135dd-161">**O destinatário é um membro de**: especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="135dd-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="135dd-162">**O domínio do destinatário é**: especifica destinatários em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="135dd-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="135dd-163">Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.</span><span class="sxs-lookup"><span data-stu-id="135dd-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="135dd-164">Clique na caixa e role pela lista de valores para selecionar.</span><span class="sxs-lookup"><span data-stu-id="135dd-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="135dd-165">Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="135dd-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="135dd-166">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="135dd-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="135dd-167">Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="135dd-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="135dd-168">Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="135dd-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="135dd-169">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.</span><span class="sxs-lookup"><span data-stu-id="135dd-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="135dd-170">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**.</span><span class="sxs-lookup"><span data-stu-id="135dd-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="135dd-171">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="135dd-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="135dd-172">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="135dd-173">Na página **revise suas configurações** exibidas, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="135dd-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="135dd-174">Você pode clicar em **Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="135dd-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="135dd-175">Quando tiver concluído, clique em **criar esta política**.</span><span class="sxs-lookup"><span data-stu-id="135dd-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="135dd-176">Clique em **OK** na caixa de diálogo de confirmação que aparece.</span><span class="sxs-lookup"><span data-stu-id="135dd-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="135dd-177">Após criar a política anti-phishing do ATP com estas configurações gerais de política, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="135dd-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-178">Usar o centro de conformidade de & de segurança para modificar as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="135dd-179">Use os procedimentos a seguir para modificar as políticas de anti-phishing do ATP: uma nova política que você criou ou políticas existentes que você já personalizou.</span><span class="sxs-lookup"><span data-stu-id="135dd-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="135dd-180">Se você ainda não estiver lá, abra o centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-phishing da ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-181">Selecione a política de anti-phishing padrão ATP que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="135dd-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="135dd-182">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="135dd-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="135dd-183">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="135dd-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="135dd-184">Clicar em **Editar** em qualquer seção fornece acesso às configurações dessa seção.</span><span class="sxs-lookup"><span data-stu-id="135dd-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="135dd-185">As etapas a seguir são apresentadas na ordem em que as seções são exibidas, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="135dd-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="135dd-186">Depois de clicar em **Editar** em uma seção, as configurações disponíveis são apresentadas em um formato de assistente, mas você pode saltar dentro das páginas em qualquer ordem, e você pode clicar em **salvar** em qualquer página (ou **Cancelar** ou **fechar** ![ o ícone fechar ](../../media/scc-remove-icon.png) para retornar à página \*\*editar sua política \<name\> \*\* (não é necessário visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="135dd-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="135dd-187">**Configuração de política**: clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você [criou a política](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="135dd-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="135dd-188">**Nome**</span><span class="sxs-lookup"><span data-stu-id="135dd-188">**Name**</span></span>
   - <span data-ttu-id="135dd-189">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="135dd-189">**Description**</span></span>
   - <span data-ttu-id="135dd-190">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="135dd-190">**Applied to**</span></span>
   - <span data-ttu-id="135dd-191">**Revisar suas configurações**</span><span class="sxs-lookup"><span data-stu-id="135dd-191">**Review your settings**</span></span>

   <span data-ttu-id="135dd-192">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="135dd-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="135dd-193">**Representação**: clique em **Editar** para modificar os remetentes protegidos e os domínios protegidos na política.</span><span class="sxs-lookup"><span data-stu-id="135dd-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="135dd-194">Essas configurações são uma condição para a política que identifica remetentes falsificados a serem procurados (individualmente ou por domínio) no endereço de das mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="135dd-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="135dd-195">Para obter mais informações, consulte [configurações de representação em políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="135dd-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="135dd-196">**Adicionar usuários para proteger**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="135dd-197">Para ativá-la, deslize o botão de alternância para **ativado**e, em seguida, clique no botão **Adicionar usuário** que aparece.</span><span class="sxs-lookup"><span data-stu-id="135dd-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="135dd-198">No submenu **Adicionar usuário** exibido, configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="135dd-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="135dd-199">**Endereço de email**:</span><span class="sxs-lookup"><span data-stu-id="135dd-199">**Email address**:</span></span>

        - <span data-ttu-id="135dd-200">Clique na caixa e role pela lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="135dd-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="135dd-201">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="135dd-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="135dd-202">Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.</span><span class="sxs-lookup"><span data-stu-id="135dd-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="135dd-203">**Nome**: esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="135dd-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="135dd-204">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="135dd-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="135dd-205">Para editar uma entrada existente, selecione o usuário protegido na lista.</span><span class="sxs-lookup"><span data-stu-id="135dd-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="135dd-206">**Adicionar domínios para proteger**: Configure uma ou ambas as configurações a seguir:</span><span class="sxs-lookup"><span data-stu-id="135dd-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="135dd-207">**Incluir automaticamente os domínios que**possuo: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="135dd-208">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="135dd-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="135dd-209">**Incluir domínios personalizados**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="135dd-210">Para ativá-la, deslize o **botão para ativar e,** na caixa **adicionar domínios** , digite o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="135dd-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="135dd-211">**Ações**: clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="135dd-211">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="135dd-212">**Se o email for enviado por um usuário representado**: Configure uma das ações a seguir para mensagens em que o remetente falsificado é um dos usuários protegidos que você especificou em **Adicionar usuários para proteger**:</span><span class="sxs-lookup"><span data-stu-id="135dd-212">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="135dd-213">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="135dd-213">**Don't apply any action**</span></span>
       - <span data-ttu-id="135dd-214">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="135dd-214">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="135dd-215">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="135dd-215">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="135dd-216">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="135dd-216">**Quarantine the message**</span></span>
       - <span data-ttu-id="135dd-217">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="135dd-217">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="135dd-218">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="135dd-218">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="135dd-219">**Se o email for enviado por um domínio representado**: Configure uma das ações a seguir para mensagens em que o remetente falsificado está em um dos domínios protegidos que você especificou em **adicionar domínios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="135dd-219">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="135dd-220">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="135dd-220">**Don't apply any action**</span></span>
     - <span data-ttu-id="135dd-221">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="135dd-221">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="135dd-222">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="135dd-222">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="135dd-223">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="135dd-223">**Quarantine the message**</span></span>
     - <span data-ttu-id="135dd-224">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="135dd-224">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="135dd-225">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="135dd-225">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="135dd-226">Clique em **Ativar dicas de segurança de representação** e configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="135dd-226">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="135dd-227">**Mostrar dica para usuários representados**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-227">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="135dd-228">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="135dd-228">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="135dd-229">**Mostrar dica para domínios representados**: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-229">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="135dd-230">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="135dd-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="135dd-231">**Mostrar dica para caracteres incomuns**: o valor padrão está **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-231">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="135dd-232">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="135dd-232">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="135dd-233">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-233">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="135dd-234">**Inteligência de caixa de correio**:</span><span class="sxs-lookup"><span data-stu-id="135dd-234">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="135dd-235">**Habilitar o Mailbox Intelligence?**: o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-235">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="135dd-236">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-236">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="135dd-237">**Habilitar proteção de representação baseada em inteligência de caixa de correio?**: essa configuração só estará disponível se **habilitar inteligência de caixa de correio?** estiver **ativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-237">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="135dd-238">Em **se o email for enviado por um usuário representado**, você poderá especificar uma das ações a seguir para executar as mensagens que falham na inteligência de caixa de correio (as mesmas ações que estão disponíveis para usuários protegidos e domínios protegidos):</span><span class="sxs-lookup"><span data-stu-id="135dd-238">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="135dd-239">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="135dd-239">**Don't apply any action**</span></span>
       - <span data-ttu-id="135dd-240">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="135dd-240">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="135dd-241">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="135dd-241">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="135dd-242">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="135dd-242">**Quarantine the message**</span></span>
       - <span data-ttu-id="135dd-243">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="135dd-243">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="135dd-244">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="135dd-244">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="135dd-245">**Adicionar remetentes e domínios confiáveis**: especifique exceções para a política:</span><span class="sxs-lookup"><span data-stu-id="135dd-245">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="135dd-246">**Remetentes confiáveis**:</span><span class="sxs-lookup"><span data-stu-id="135dd-246">**Trusted senders**:</span></span>

       - <span data-ttu-id="135dd-247">Clique na caixa e role pela lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="135dd-247">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="135dd-248">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="135dd-248">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="135dd-249">Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.</span><span class="sxs-lookup"><span data-stu-id="135dd-249">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="135dd-250">**Domínios confiáveis**: Insira o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="135dd-250">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="135dd-251">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="135dd-251">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="135dd-252">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="135dd-252">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="135dd-253">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="135dd-253">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="135dd-254">**Usuários protegidos**</span><span class="sxs-lookup"><span data-stu-id="135dd-254">**Protected users**</span></span>
       - <span data-ttu-id="135dd-255">**Domínios protegidos** \> **Incluir domínios que sou proprietário**</span><span class="sxs-lookup"><span data-stu-id="135dd-255">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="135dd-256">**Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)</span><span class="sxs-lookup"><span data-stu-id="135dd-256">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="135dd-257">**Inteligência da caixa de correio**</span><span class="sxs-lookup"><span data-stu-id="135dd-257">**Mailbox intelligence**</span></span>

   <span data-ttu-id="135dd-258">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="135dd-258">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="135dd-259">**Spoof**: clique em **Editar** para ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação a ser aplicada às mensagens de remetentes falsificados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="135dd-259">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="135dd-260">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="135dd-260">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="135dd-261">Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.</span><span class="sxs-lookup"><span data-stu-id="135dd-261">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="135dd-262">**Falsificação de configurações de filtro**: o valor padrão é **ativado**e recomendamos que você o deixe ligado.</span><span class="sxs-lookup"><span data-stu-id="135dd-262">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="135dd-263">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-263">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="135dd-264">Para obter mais informações, consulte [Configure spoof Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-264">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="135dd-265">Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores.</span><span class="sxs-lookup"><span data-stu-id="135dd-265">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="135dd-266">Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="135dd-266">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="135dd-267">**Habilitar o recurso de remetente não autenticado**: o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-267">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="135dd-268">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="135dd-268">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="135dd-269">**Ações**: Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="135dd-269">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="135dd-270">**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio**:</span><span class="sxs-lookup"><span data-stu-id="135dd-270">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="135dd-271">**Mover mensagem para pastas de lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="135dd-271">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="135dd-272">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="135dd-272">**Quarantine the message**</span></span>

   - <span data-ttu-id="135dd-273">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="135dd-273">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="135dd-274">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="135dd-274">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="135dd-275">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="135dd-275">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="135dd-276">**Habilitar proteção contra falsificação**</span><span class="sxs-lookup"><span data-stu-id="135dd-276">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="135dd-277">**Habilitar o recurso de remetente não autenticado**</span><span class="sxs-lookup"><span data-stu-id="135dd-277">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="135dd-278">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="135dd-278">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="135dd-279">**Configurações avançadas**: clique em **Editar** para configurar os limites avançados de phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-279">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="135dd-280">Para obter mais informações, consulte [limites de phishing avançados nas políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="135dd-280">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="135dd-281">**Limites de phishing avançados**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="135dd-281">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="135dd-282">**1-padrão** (este é o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="135dd-282">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="135dd-283">**2-agressivo**</span><span class="sxs-lookup"><span data-stu-id="135dd-283">**2 - Aggressive**</span></span>
   - <span data-ttu-id="135dd-284">**3-mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="135dd-284">**3 - More aggressive**</span></span>
   - <span data-ttu-id="135dd-285">**4-mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="135dd-285">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="135dd-286">**Revise suas configurações**: clique em **Editar** para voltar para a página de **limiares de phishing avançados** .</span><span class="sxs-lookup"><span data-stu-id="135dd-286">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="135dd-287">Quando tiver terminado, clique em **salvar** em qualquer uma das páginas.</span><span class="sxs-lookup"><span data-stu-id="135dd-287">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="135dd-288">Novamente na página \*\*editar sua política \<Name\> \*\* , revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-288">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="135dd-289">Usar o centro de conformidade de & de segurança para modificar a política de anti-phishing padrão ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-289">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="135dd-290">A política anti-phishing padrão ATP é chamada de padrão do Office365 antiphish, e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="135dd-290">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="135dd-291">Para modificar a política anti-phishing padrão da ATP, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="135dd-291">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="135dd-292">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-292">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-293">Na página **anti-phishing** , clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="135dd-293">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="135dd-294">A página **editar sua política padrão do Office365 antiphishing** é exibida.</span><span class="sxs-lookup"><span data-stu-id="135dd-294">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="135dd-295">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="135dd-295">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="135dd-296">**Representação**</span><span class="sxs-lookup"><span data-stu-id="135dd-296">**Impersonation**</span></span>
   - <span data-ttu-id="135dd-297">**Simulação**</span><span class="sxs-lookup"><span data-stu-id="135dd-297">**Spoof**</span></span>
   - <span data-ttu-id="135dd-298">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="135dd-298">**Advanced settings**</span></span>

   <span data-ttu-id="135dd-299">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="135dd-299">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="135dd-300">Você pode ver a seção e os valores da **configuração de política** , mas não há nenhum link de **edição** , portanto, não é possível modificar as configurações (nome da diretiva, descrição e a qual a política se aplica (ela se aplica a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="135dd-300">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="135dd-301">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="135dd-301">You can't delete the default policy.</span></span>
   - <span data-ttu-id="135dd-302">Você não pode alterar a prioridade da política padrão (ela é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="135dd-302">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="135dd-303">Na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-303">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-304">Habilitar ou desabilitar políticas antivírus ATP personalizadas</span><span class="sxs-lookup"><span data-stu-id="135dd-304">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="135dd-305">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-305">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-306">Observe o valor na coluna **status** :</span><span class="sxs-lookup"><span data-stu-id="135dd-306">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="135dd-307">Deslize o botão de **alternância para desativar** a política.</span><span class="sxs-lookup"><span data-stu-id="135dd-307">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="135dd-308">Deslize o botão de **alternância para ativar** a política.</span><span class="sxs-lookup"><span data-stu-id="135dd-308">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="135dd-309">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="135dd-309">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-310">Definir a prioridade de políticas anti-phishing padrão da ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-310">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="135dd-311">Por padrão, as políticas anti-phishing do ATP recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="135dd-311">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="135dd-312">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="135dd-312">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="135dd-313">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="135dd-313">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="135dd-314">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="135dd-314">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="135dd-315">As políticas anti-phishing padrão ATP são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="135dd-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="135dd-316">A política anti-phishing padrão chamada do Office365 antiphish padrão tem o valor de prioridade personalizado **mais baixo**e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="135dd-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="135dd-317">**Observação**: no centro de conformidade & segurança, você só pode alterar a prioridade da política anti-phishing do ATP após criá-la.</span><span class="sxs-lookup"><span data-stu-id="135dd-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="135dd-318">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-Phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="135dd-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="135dd-319">Para alterar a prioridade de uma política, clique em **aumentar** a prioridade ou **diminuir a prioridade** nas propriedades da política (não é possível modificar diretamente o número de **prioridade** no centro de conformidade do & de segurança).</span><span class="sxs-lookup"><span data-stu-id="135dd-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="135dd-320">Alterar a prioridade de uma política faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="135dd-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="135dd-321">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-322">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="135dd-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="135dd-323">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="135dd-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="135dd-324">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="135dd-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="135dd-325">A política de anti-phishing padrão ATP com o valor **Priority** de prioridade **0** tem apenas o botão **diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="135dd-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="135dd-326">A política de anti-phishing padrão ATP com o menor valor de **prioridade** (por exemplo, **3**) tem apenas o botão **aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="135dd-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="135dd-327">Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="135dd-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="135dd-328">Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="135dd-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="135dd-329">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-330">Usar o centro de conformidade de & de segurança para exibir as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="135dd-331">No centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-332">Execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="135dd-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="135dd-333">Selecione uma política antivírus ATP personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="135dd-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="135dd-334">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="135dd-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="135dd-335">Clique em **política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="135dd-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="135dd-336">O submenu **Editar \<name\> sua política** aparece, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="135dd-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-337">Usar o centro de conformidade de & de segurança para remover as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="135dd-338">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="135dd-339">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="135dd-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="135dd-340">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="135dd-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="135dd-341">No submenu **editar sua \<name\> política** exibido, clique em **excluir política**e, em seguida, clique em **Sim** na caixa de diálogo de aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="135dd-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="135dd-342">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="135dd-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="135dd-343">Usar o PowerShell do Exchange Online para configurar as políticas de anti-phishing da ATP</span><span class="sxs-lookup"><span data-stu-id="135dd-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="135dd-344">Conforme descrito anteriormente, uma política antispam ATP consiste em uma política de anti-phishing e uma regra de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-344">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="135dd-345">No PowerShell do Exchange Online, a diferença entre políticas de anti-phishing e regras antiphish é aparente.</span><span class="sxs-lookup"><span data-stu-id="135dd-345">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="135dd-346">Você gerencia as políticas de anti-phishing usando os cmdlets \*\* \* -AntiPhishPolicy\*\* e gerencia regras de anti-phishing usando os cmdlets \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="135dd-346">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="135dd-347">No PowerShell, você cria a política de anti-phishing primeiro e, em seguida, cria a regra anti-Phish que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="135dd-347">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="135dd-348">No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-Phish separadamente.</span><span class="sxs-lookup"><span data-stu-id="135dd-348">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="135dd-349">Quando você remove uma política de anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="135dd-349">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="135dd-350">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="135dd-350">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="135dd-351">A criação de uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="135dd-351">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="135dd-352">Criar a política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-352">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="135dd-353">Crie a regra anti-Phish que especifica a política de anti-phishing à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="135dd-353">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="135dd-354">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="135dd-354">**Notes**:</span></span>

- <span data-ttu-id="135dd-355">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e não associada a ela.</span><span class="sxs-lookup"><span data-stu-id="135dd-355">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="135dd-356">Uma regra anti-Phish não pode ser associada a mais de uma política de phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-356">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="135dd-357">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="135dd-357">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="135dd-358">Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="135dd-358">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="135dd-359">Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="135dd-359">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="135dd-360">Uma nova política de Phish que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-360">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="135dd-361">Etapa 1: usar o PowerShell para criar uma política de anti-phishing</span><span class="sxs-lookup"><span data-stu-id="135dd-361">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="135dd-362">Para criar uma política de anti-golpe, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-362">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="135dd-363">Este exemplo cria uma política de anti-phishing chamada quarentena de pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="135dd-363">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="135dd-364">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="135dd-364">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="135dd-365">A descrição é: política de departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="135dd-365">The description is: Research department policy.</span></span>
- <span data-ttu-id="135dd-366">Habilita a proteção de domínios de organização para todos os domínios aceitos e proteção de domínios direcionados para o fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="135dd-366">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="135dd-367">Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário para proteger da representação.</span><span class="sxs-lookup"><span data-stu-id="135dd-367">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="135dd-368">Habilita a inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="135dd-368">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="135dd-369">Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.</span><span class="sxs-lookup"><span data-stu-id="135dd-369">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="135dd-370">Permite dicas de segurança.</span><span class="sxs-lookup"><span data-stu-id="135dd-370">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="135dd-371">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="135dd-371">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="135dd-372">Etapa 2: usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="135dd-372">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="135dd-373">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-373">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="135dd-374">Este exemplo cria uma regra anti-phishing chamada departamento de pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="135dd-374">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="135dd-375">A regra é associada à política de anti-phishing chamada quarentena de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="135dd-375">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="135dd-376">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="135dd-376">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="135dd-377">Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="135dd-377">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="135dd-378">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="135dd-378">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="135dd-379">Usar o PowerShell para exibir políticas antispam</span><span class="sxs-lookup"><span data-stu-id="135dd-379">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="135dd-380">Para exibir as políticas antispam existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-380">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="135dd-381">Este exemplo retorna uma lista resumida de todas as políticas de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="135dd-381">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="135dd-382">Este exemplo retorna todos os valores de propriedade da política anti-Phish chamada executivos.</span><span class="sxs-lookup"><span data-stu-id="135dd-382">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="135dd-383">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="135dd-383">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="135dd-384">Usar o PowerShell para exibir regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="135dd-384">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="135dd-385">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-385">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="135dd-386">Este exemplo retorna uma lista resumida de todas as regras de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="135dd-386">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="135dd-387">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="135dd-387">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="135dd-388">Este exemplo retorna todos os valores de propriedade da regra anti-Phish chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="135dd-388">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="135dd-389">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="135dd-389">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="135dd-390">Usar o PowerShell para modificar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="135dd-390">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="135dd-391">Além dos seguintes itens, as mesmas configurações estão disponíveis quando você modifica uma política de anti-phishing no PowerShell como quando você cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anti-golpe](#step-1-use-powershell-to-create-an-anti-phish-policy) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="135dd-391">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="135dd-392">A opção _MakeDefault_ que transforma a política especificada na política padrão (aplicada a todos, sempre a prioridade **mais baixa** e não é possível excluí-la) só está disponível quando você modifica uma política de Phish no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="135dd-392">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="135dd-393">Não é possível renomear uma política anti-phishing (o cmdlet **set-AntiPhishPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="135dd-393">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="135dd-394">Ao renomear uma política anti-phishing no centro de conformidade & segurança, você estará apenas renomeando a _regra_anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="135dd-394">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="135dd-395">Para modificar uma política de anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-395">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="135dd-396">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="135dd-396">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="135dd-397">Usar o PowerShell para modificar as regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="135dd-397">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="135dd-398">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite que você crie uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="135dd-398">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="135dd-399">Para habilitar ou desabilitar regras antispam existentes, confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="135dd-399">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="135dd-400">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="135dd-400">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="135dd-401">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="135dd-401">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="135dd-402">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-402">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="135dd-403">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="135dd-403">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="135dd-404">Usar o PowerShell para habilitar ou desabilitar regras de Phish</span><span class="sxs-lookup"><span data-stu-id="135dd-404">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="135dd-405">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política de anti-phishing atribuídas).</span><span class="sxs-lookup"><span data-stu-id="135dd-405">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="135dd-406">Você não pode habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="135dd-406">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="135dd-407">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-407">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="135dd-408">Este exemplo desabilita a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="135dd-408">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="135dd-409">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="135dd-409">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="135dd-410">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="135dd-410">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="135dd-411">Usar o PowerShell para definir a prioridade de regras de Phish</span><span class="sxs-lookup"><span data-stu-id="135dd-411">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="135dd-412">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="135dd-412">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="135dd-413">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="135dd-413">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="135dd-414">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="135dd-414">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="135dd-415">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="135dd-415">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="135dd-416">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="135dd-416">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="135dd-417">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-417">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="135dd-418">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="135dd-418">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="135dd-419">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="135dd-419">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="135dd-420">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="135dd-420">**Notes**:</span></span>

- <span data-ttu-id="135dd-421">Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="135dd-421">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="135dd-422">A política de anti-phishing padrão não tem uma regra antiphishing correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="135dd-422">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="135dd-423">Usar o PowerShell para remover políticas antispam</span><span class="sxs-lookup"><span data-stu-id="135dd-423">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="135dd-424">Quando você usa o PowerShell para remover uma política de Phish, a regra anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="135dd-424">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="135dd-425">Para remover uma política de anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-425">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="135dd-426">Este exemplo remove a política de anti-golpe chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="135dd-426">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="135dd-427">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="135dd-427">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="135dd-428">Usar o PowerShell para remover regras de Phish</span><span class="sxs-lookup"><span data-stu-id="135dd-428">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="135dd-429">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="135dd-429">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="135dd-430">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="135dd-430">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="135dd-431">Este exemplo remove a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="135dd-431">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="135dd-432">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="135dd-432">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="135dd-433">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="135dd-433">How do you know these procedures worked?</span></span>

<span data-ttu-id="135dd-434">Para verificar se você configurou com êxito as políticas de anti-phishing do ATP, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="135dd-434">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="135dd-435">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="135dd-435">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="135dd-436">Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="135dd-436">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="135dd-437">Para exibir mais detalhes, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="135dd-437">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="135dd-438">Selecione a política na lista e exiba os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="135dd-438">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="135dd-439">Clique em **política padrão** e visualize os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="135dd-439">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="135dd-440">No PowerShell do Exchange Online, substitua \<Name\> o nome da política ou regra e execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="135dd-440">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
