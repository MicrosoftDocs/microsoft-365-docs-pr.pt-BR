---
title: Configurar políticas anti-phishing no Microsoft defender para Office 365
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
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing avançadas disponíveis nas organizações com o Microsoft defender para Office 365.
ms.openlocfilehash: 7665d0dc475909d04da209aa6c1cd6b12378f8a9
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993383"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-103">Configurar políticas anti-phishing no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3d2d-104">As políticas anti-phishing no [Microsoft defender para Office 365](office-365-atp.md) podem ajudar a proteger sua organização contra ataques de phishing baseados em personificação mal-intencionada e outros tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="c3d2d-105">Para obter mais informações sobre as diferenças entre políticas anti-phishing no Exchange Online Protection (EOP) e nas políticas anti-phishing no Microsoft defender para Office 365, consulte [anti-phishing Protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="c3d2d-106">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="c3d2d-107">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="c3d2d-108">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="c3d2d-109">Você pode configurar políticas anti-phishing no centro de conformidade & segurança ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="c3d2d-110">Para obter informações sobre como configurar o mais limitado em políticas anti-phishing que estão disponíveis em organizações do Exchange Online Protection (ou seja, organizações sem o Microsoft defender para Office 365), consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="c3d2d-111">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="c3d2d-112">**A política de anti-golpe** : especifica as proteções de phishing a serem habilitadas ou desabilitadas e as ações para aplicar as opções.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-112">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="c3d2d-113">**A regra anti-Phish** : especifica a prioridade e os filtros de destinatário (com quem a política se aplica) para uma política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-113">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="c3d2d-114">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas anti-phishing no centro de conformidade & segurança:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c3d2d-115">Ao criar uma política, você realmente está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c3d2d-116">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="c3d2d-117">Todas as outras configurações modificam a política de anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="c3d2d-118">Quando você remove uma política, a regra anti-Phish e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="c3d2d-119">No PowerShell do Exchange Online, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c3d2d-120">Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online para configurar políticas anti-phishing no Microsoft defender para Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="c3d2d-121">Todas as organizações do Microsoft defender para Office 365 têm uma política anti-phishing interna chamada Office365 antiphishing default que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="c3d2d-122">A política é aplicada a todos os destinatários na organização, mesmo que não haja uma regra de anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="c3d2d-123">A política tem o valor de prioridade personalizado **Menor** , que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="c3d2d-124">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="c3d2d-125">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="c3d2d-126">Para aumentar a eficácia da proteção contra phishing no Microsoft defender para Office 365, você pode criar políticas anti-phishing personalizadas com configurações mais rigorosas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3d2d-127">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="c3d2d-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3d2d-128">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c3d2d-129">Para ir diretamente para a página de **anti-phishing do ATP** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="c3d2d-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="c3d2d-130">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c3d2d-131">Você precisa receber permissões antes de executar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="c3d2d-132">Para adicionar, modificar e excluir políticas anti-phishing, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-132">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c3d2d-133">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c3d2d-134">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-134">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="c3d2d-135">Para acesso somente leitura às políticas anti-phishing, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-135">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c3d2d-136">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-136">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c3d2d-137">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-137">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="c3d2d-138">Para nossas configurações recomendadas para políticas anti-phishing no Microsoft defender para Office 365, consulte [anti-phishing Policy in defender for office 365 Settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-138">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="c3d2d-139">Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-139">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c3d2d-140">Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-140">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-141">Usar o centro de conformidade de & de segurança para criar políticas anti-phishing no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-141">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c3d2d-142">A criação de uma política anti-phishing personalizada no centro de conformidade & segurança cria a regra anti-phishing e a política de anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-142">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="c3d2d-143">Ao criar uma política anti-phishing, você só poderá especificar o nome da política, a descrição e o filtro de destinatário que identifique a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-143">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="c3d2d-144">Após criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-144">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="c3d2d-145">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-146">Na página **anti-phishing** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-146">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="c3d2d-147">O assistente para **criar uma nova política** de anti-phishing é aberto.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-147">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="c3d2d-148">Na página **nomear sua política** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="c3d2d-149">**Nome** : insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-149">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="c3d2d-150">**Descrição** : digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-150">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="c3d2d-151">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c3d2d-152">Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-152">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="c3d2d-153">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-153">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c3d2d-154">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-154">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="c3d2d-155">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-155">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="c3d2d-156">Clique em **Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-156">Click **Add a condition**.</span></span> <span data-ttu-id="c3d2d-157">Na lista suspensa exibida, selecione uma condição em **aplicado se** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-157">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="c3d2d-158">**O destinatário é** : especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-158">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="c3d2d-159">**O destinatário é um membro de** : especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-159">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="c3d2d-160">**O domínio do destinatário é** : especifica destinatários em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-160">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="c3d2d-161">Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-161">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="c3d2d-162">Clique na caixa e role pela lista de valores para selecionar.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-162">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="c3d2d-163">Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-163">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="c3d2d-164">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-164">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="c3d2d-165">Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-165">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="c3d2d-166">Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-166">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="c3d2d-167">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-167">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="c3d2d-168">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-168">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="c3d2d-169">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="c3d2d-170">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c3d2d-171">Na página **revise suas configurações** exibidas, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-171">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="c3d2d-172">Você pode clicar em **Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-172">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="c3d2d-173">Quando tiver concluído, clique em **criar esta política**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-173">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="c3d2d-174">Clique em **OK** na caixa de diálogo de confirmação que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-174">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="c3d2d-175">Após criar a política anti-phishing com estas configurações gerais, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-175">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-176">Usar o centro de conformidade de & de segurança para modificar políticas anti-phishing no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-176">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c3d2d-177">Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalizou.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-177">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="c3d2d-178">Se você ainda não estiver lá, abra o centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-phishing da ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-178">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-179">Selecione a política anti-phishing personalizada que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-179">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="c3d2d-180">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-180">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="c3d2d-181">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-181">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="c3d2d-182">Clicar em **Editar** em qualquer seção fornece acesso às configurações dessa seção.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-182">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="c3d2d-183">As etapas a seguir são apresentadas na ordem em que as seções são exibidas, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-183">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="c3d2d-184">Depois de clicar em **Editar** em uma seção, as configurações disponíveis são apresentadas em um formato de assistente, mas você pode saltar dentro das páginas em qualquer ordem, e você pode clicar em **salvar** em qualquer página (ou **Cancelar** ou **fechar** ![ o ícone fechar ](../../media/scc-remove-icon.png) para retornar à página **editar sua política \<name\>** (não é necessário visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-184">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="c3d2d-185">**Configuração de política** : clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você [criou a política](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-185">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="c3d2d-186">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-186">**Name**</span></span>
   - <span data-ttu-id="c3d2d-187">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-187">**Description**</span></span>
   - <span data-ttu-id="c3d2d-188">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-188">**Applied to**</span></span>
   - <span data-ttu-id="c3d2d-189">**Revisar suas configurações**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-189">**Review your settings**</span></span>

   <span data-ttu-id="c3d2d-190">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-190">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="c3d2d-191">**Representação** : clique em **Editar** para modificar os remetentes protegidos e os domínios protegidos na política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-191">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="c3d2d-192">Essas configurações são uma condição para a política que identifica remetentes falsificados a serem procurados (individualmente ou por domínio) no endereço de das mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-192">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="c3d2d-193">Para obter mais informações, consulte [configurações de representação em políticas anti-phishing no Microsoft defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-193">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="c3d2d-194">**Adicionar usuários para proteger** : o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-194">**Add users to protect** : The default value is **Off**.</span></span> <span data-ttu-id="c3d2d-195">Para ativá-la, deslize o botão de alternância para **ativado** e, em seguida, clique no botão **Adicionar usuário** que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-195">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="c3d2d-196">No submenu **Adicionar usuário** exibido, configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-196">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="c3d2d-197">**Endereço de email** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-197">**Email address** :</span></span>

       - <span data-ttu-id="c3d2d-198">Clique na caixa e role pela lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-198">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="c3d2d-199">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-199">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="c3d2d-200">Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-200">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="c3d2d-201">**Nome** : esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-201">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="c3d2d-202">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-202">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="c3d2d-203">Para editar uma entrada existente, selecione o usuário protegido na lista.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-203">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="c3d2d-204">Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-204">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="c3d2d-205">Você não pode especificar o mesmo usuário protegido em várias políticas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-205">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="c3d2d-206">A proteção de representação do usuário não funciona se o remetente e o destinatário tiverem sido comunicados anteriormente por email.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-206">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="c3d2d-207">Se o remetente e o destinatário nunca tiverem sido comunicados por email, a mensagem será identificada como uma tentativa de representação.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-207">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="c3d2d-208">**Adicionar domínios para proteger** : Configure uma ou ambas as configurações a seguir:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-208">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="c3d2d-209">**Incluir automaticamente os domínios que** possuo: o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-209">**Automatically include the domains I own** : The default value is **Off**.</span></span> <span data-ttu-id="c3d2d-210">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-210">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="c3d2d-211">**Incluir domínios personalizados** : o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-211">**Include custom domains** : The default value is **Off**.</span></span> <span data-ttu-id="c3d2d-212">Para ativá-la, deslize o **botão para ativar e,** na caixa **adicionar domínios** , digite o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-212">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c3d2d-213">Você pode ter no máximo 50 domínios em todas as políticas anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-213">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="c3d2d-214">**Ações** : clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-214">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="c3d2d-215">**Se o email for enviado por um usuário representado** : Configure uma das ações a seguir para mensagens em que o remetente falsificado é um dos usuários protegidos que você especificou em **Adicionar usuários para proteger** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-215">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="c3d2d-216">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-216">**Don't apply any action**</span></span>
       - <span data-ttu-id="c3d2d-217">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-217">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c3d2d-218">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-218">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="c3d2d-219">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-219">**Quarantine the message**</span></span>
       - <span data-ttu-id="c3d2d-220">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-220">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c3d2d-221">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-221">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="c3d2d-222">**Se o email for enviado por um domínio representado** : Configure uma das ações a seguir para mensagens em que o remetente falsificado está em um dos domínios protegidos que você especificou em **adicionar domínios para proteger** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-222">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

       - <span data-ttu-id="c3d2d-223">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="c3d2d-224">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c3d2d-225">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-225">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="c3d2d-226">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="c3d2d-227">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c3d2d-228">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-228">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="c3d2d-229">Clique em **Ativar dicas de segurança de representação** e configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-229">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="c3d2d-230">**Mostrar dica para usuários representados** : o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-230">**Show tip for impersonated users** : The default value is **Off**.</span></span> <span data-ttu-id="c3d2d-231">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-231">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="c3d2d-232">**Mostrar dica para domínios representados** : o valor padrão é **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-232">**Show tip for impersonated domains** : The default value is **Off**.</span></span> <span data-ttu-id="c3d2d-233">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-233">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="c3d2d-234">**Mostrar dica para caracteres incomuns** : o valor padrão está **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-234">**Show tip for unusual characters** : The default value is **Off**.</span></span> <span data-ttu-id="c3d2d-235">Para ativá-la, deslize o botão para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-235">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="c3d2d-236">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-236">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="c3d2d-237">**Inteligência de caixa de correio** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-237">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="c3d2d-238">**Habilitar o Mailbox Intelligence?** : o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-238">**Enable mailbox intelligence?** : The default value is **On**.</span></span> <span data-ttu-id="c3d2d-239">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-239">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="c3d2d-240">**Habilitar proteção de representação baseada em inteligência de caixa de correio?** : essa configuração só estará disponível se **habilitar inteligência de caixa de correio?** estiver **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-240">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="c3d2d-241">Em **se o email for enviado por um usuário representado** , você poderá especificar uma das ações a seguir para executar as mensagens que falham na inteligência de caixa de correio (as mesmas ações que estão disponíveis para usuários protegidos e domínios protegidos):</span><span class="sxs-lookup"><span data-stu-id="c3d2d-241">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="c3d2d-242">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-242">**Don't apply any action**</span></span>
       - <span data-ttu-id="c3d2d-243">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-243">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c3d2d-244">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-244">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="c3d2d-245">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-245">**Quarantine the message**</span></span>
       - <span data-ttu-id="c3d2d-246">**Entregar a mensagem e adicionar outros endereços à linha Cco**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-246">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c3d2d-247">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-247">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="c3d2d-248">**Adicionar remetentes e domínios confiáveis** : especifique exceções para a política:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-248">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="c3d2d-249">**Remetentes confiáveis** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-249">**Trusted senders** :</span></span>

       - <span data-ttu-id="c3d2d-250">Clique na caixa e role pela lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-250">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="c3d2d-251">Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-251">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="c3d2d-252">Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-252">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="c3d2d-253">**Domínios confiáveis** : Insira o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-253">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="c3d2d-254">**Revise suas configurações** : em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-254">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="c3d2d-255">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-255">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="c3d2d-256">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-256">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="c3d2d-257">**Usuários protegidos**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-257">**Protected users**</span></span>
       - <span data-ttu-id="c3d2d-258">**Domínios protegidos** \> **Incluir domínios que sou proprietário**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-258">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="c3d2d-259">**Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)</span><span class="sxs-lookup"><span data-stu-id="c3d2d-259">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="c3d2d-260">**Inteligência da caixa de correio**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-260">**Mailbox intelligence**</span></span>

   <span data-ttu-id="c3d2d-261">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-261">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="c3d2d-262">**Spoof** : clique em **Editar** para ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação a ser aplicada às mensagens de remetentes falsificados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-262">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="c3d2d-263">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-263">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="c3d2d-264">Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-264">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="c3d2d-265">**Falsificação de configurações de filtro** : o valor padrão é **ativado** e recomendamos que você o deixe ligado.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-265">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="c3d2d-266">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-266">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="c3d2d-267">Para obter mais informações, consulte [Configure spoof Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-267">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="c3d2d-268">Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-268">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="c3d2d-269">Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-269">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="c3d2d-270">**Habilitar o recurso de remetente não autenticado** : o valor padrão é **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-270">**Enable Unauthenticated Sender feature** : The default value is **On**.</span></span> <span data-ttu-id="c3d2d-271">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-271">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="c3d2d-272">**Ações** : Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-272">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="c3d2d-273">**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-273">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="c3d2d-274">**Mover mensagem para pastas de lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-274">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="c3d2d-275">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-275">**Quarantine the message**</span></span>

   - <span data-ttu-id="c3d2d-276">**Revise suas configurações** : em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-276">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="c3d2d-277">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-277">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="c3d2d-278">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-278">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="c3d2d-279">**Habilitar proteção contra falsificação**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-279">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="c3d2d-280">**Habilitar o recurso de remetente não autenticado**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-280">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="c3d2d-281">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-281">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="c3d2d-282">**Configurações avançadas** : clique em **Editar** para configurar os limites avançados de phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-282">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="c3d2d-283">Para obter mais informações, consulte [limites avançados de phishing em políticas anti-phishing no Microsoft defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-283">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="c3d2d-284">**Limites de phishing avançados** : selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-284">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="c3d2d-285">**1-padrão** (este é o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-285">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="c3d2d-286">**2-agressivo**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-286">**2 - Aggressive**</span></span>
   - <span data-ttu-id="c3d2d-287">**3-mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-287">**3 - More aggressive**</span></span>
   - <span data-ttu-id="c3d2d-288">**4-mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-288">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="c3d2d-289">**Revise suas configurações** : clique em **Editar** para voltar para a página de **limiares de phishing avançados** .</span><span class="sxs-lookup"><span data-stu-id="c3d2d-289">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="c3d2d-290">Quando tiver terminado, clique em **salvar** em qualquer uma das páginas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-290">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="c3d2d-291">Novamente na página **editar sua política \<Name\>** , revise suas configurações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-291">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-292">Usar o centro de conformidade de & de segurança para modificar a política anti-phishing padrão no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-292">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c3d2d-293">A política anti-phishing padrão no Microsoft defender para Office 365 é chamada de padrão do Office365 antiphish, e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-293">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="c3d2d-294">Para modificar a política anti-phishing padrão, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-294">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="c3d2d-295">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-295">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-296">Na página **anti-phishing** , clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-296">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="c3d2d-297">A página **editar sua política padrão do Office365 antiphishing** é exibida.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-297">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="c3d2d-298">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="c3d2d-298">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="c3d2d-299">**Representação**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-299">**Impersonation**</span></span>
   - <span data-ttu-id="c3d2d-300">**Simulação**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-300">**Spoof**</span></span>
   - <span data-ttu-id="c3d2d-301">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="c3d2d-301">**Advanced settings**</span></span>

   <span data-ttu-id="c3d2d-302">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-302">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="c3d2d-303">Você pode ver a seção e os valores da **configuração de política** , mas não há nenhum link de **edição** , portanto, não é possível modificar as configurações (nome da diretiva, descrição e a qual a política se aplica (ela se aplica a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-303">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="c3d2d-304">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-304">You can't delete the default policy.</span></span>
   - <span data-ttu-id="c3d2d-305">Você não pode alterar a prioridade da política padrão (ela é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-305">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="c3d2d-306">Na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-306">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-307">Habilitar ou desabilitar políticas anti-phishing personalizadas no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-307">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="c3d2d-308">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-309">Observe o valor na coluna **status** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-309">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="c3d2d-310">Deslize o botão de **alternância para desativar** a política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-310">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="c3d2d-311">Deslize o botão de **alternância para ativar** a política.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-311">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="c3d2d-312">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-312">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-313">Definir a prioridade de políticas anti-phishing personalizadas no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-313">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c3d2d-314">Por padrão, as políticas anti-phishing recebem uma prioridade baseada na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-314">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="c3d2d-315">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-315">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c3d2d-316">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-316">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c3d2d-317">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-317">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="c3d2d-318">Políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-318">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="c3d2d-319">A política anti-phishing padrão chamada do Office365 antiphish padrão tem o valor de prioridade personalizado **mais baixo** e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="c3d2d-320">**Observação** : no centro de conformidade & segurança, você só pode alterar a prioridade da política anti-phishing após criá-la.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-320">**Note** : In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="c3d2d-321">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-Phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="c3d2d-322">Para alterar a prioridade de uma política, clique em **aumentar** a prioridade ou **diminuir a prioridade** nas propriedades da política (não é possível modificar diretamente o número de **prioridade** no centro de conformidade do & de segurança).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="c3d2d-323">Alterar a prioridade de uma política faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="c3d2d-324">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-325">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="c3d2d-326">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="c3d2d-327">O submenu **Editar \<name\> sua política** é exibido.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="c3d2d-328">A política anti-phishing personalizada com o valor de **prioridade** **0** tem apenas o botão **diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-328">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="c3d2d-329">A política anti-phishing personalizada com o menor valor de **prioridade** (por exemplo, **3** ) tem apenas o botão **aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-329">The custom anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="c3d2d-330">Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="c3d2d-331">Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="c3d2d-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="c3d2d-332">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-333">Usar o centro de conformidade de & de segurança para exibir políticas anti-phishing no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-333">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="c3d2d-334">No centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-335">Execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="c3d2d-336">Selecione uma política anti-phishing personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-336">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="c3d2d-337">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="c3d2d-338">Clique em **política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="c3d2d-339">O submenu **Editar \<name\> sua política** aparece, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-340">Usar o centro de conformidade de & de segurança para remover políticas anti-phishing no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-340">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="c3d2d-341">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="c3d2d-342">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="c3d2d-343">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="c3d2d-344">No submenu **editar sua \<name\> política** exibido, clique em **excluir política** e, em seguida, clique em **Sim** na caixa de diálogo de aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="c3d2d-345">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c3d2d-346">Usar o PowerShell do Exchange Online para configurar políticas anti-phishing no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d2d-346">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c3d2d-347">Como descrito anteriormente, uma política antispam consiste em uma política anti-phishing e uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-347">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="c3d2d-348">No PowerShell do Exchange Online, a diferença entre políticas de anti-phishing e regras antiphish é aparente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-348">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="c3d2d-349">Você gerencia as políticas de anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia regras de anti-phishing usando os cmdlets **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="c3d2d-349">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="c3d2d-350">No PowerShell, você cria a política de anti-phishing primeiro e, em seguida, cria a regra anti-Phish que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-350">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c3d2d-351">No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-Phish separadamente.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-351">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="c3d2d-352">Quando você remove uma política de anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-352">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="c3d2d-353">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="c3d2d-353">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="c3d2d-354">A criação de uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-354">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c3d2d-355">Criar a política de anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-355">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="c3d2d-356">Crie a regra anti-Phish que especifica a política de anti-phishing à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-356">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="c3d2d-357">**Observações** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-357">**Notes** :</span></span>

- <span data-ttu-id="c3d2d-358">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e não associada a ela.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-358">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="c3d2d-359">Uma regra anti-Phish não pode ser associada a mais de uma política de phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-359">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="c3d2d-360">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-360">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="c3d2d-361">Crie a nova política como desabilitada ( _habilitada_ `$false` no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-361">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="c3d2d-362">Definir a prioridade da política durante a criação ( _prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-362">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="c3d2d-363">Uma nova política de Phish que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-363">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="c3d2d-364">Etapa 1: usar o PowerShell para criar uma política de anti-phishing</span><span class="sxs-lookup"><span data-stu-id="c3d2d-364">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="c3d2d-365">Para criar uma política de anti-golpe, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-365">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="c3d2d-366">Este exemplo cria uma política de anti-phishing chamada quarentena de pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-366">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="c3d2d-367">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-367">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="c3d2d-368">A descrição é: política de departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-368">The description is: Research department policy.</span></span>
- <span data-ttu-id="c3d2d-369">Habilita a proteção de domínios de organização para todos os domínios aceitos e proteção de domínios direcionados para o fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-369">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="c3d2d-370">Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário para proteger da representação.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-370">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="c3d2d-371">Habilita a inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-371">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="c3d2d-372">Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-372">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="c3d2d-373">Permite dicas de segurança.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-373">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="c3d2d-374">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-374">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="c3d2d-375">Etapa 2: usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="c3d2d-375">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="c3d2d-376">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-376">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="c3d2d-377">Este exemplo cria uma regra anti-phishing chamada departamento de pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-377">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="c3d2d-378">A regra é associada à política de anti-phishing chamada quarentena de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-378">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="c3d2d-379">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-379">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="c3d2d-380">Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-380">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="c3d2d-381">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-381">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="c3d2d-382">Usar o PowerShell para exibir políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c3d2d-382">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="c3d2d-383">Para exibir as políticas antispam existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-383">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c3d2d-384">Este exemplo retorna uma lista resumida de todas as políticas de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-384">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="c3d2d-385">Este exemplo retorna todos os valores de propriedade da política anti-Phish chamada executivos.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-385">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="c3d2d-386">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-386">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="c3d2d-387">Usar o PowerShell para exibir regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="c3d2d-387">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="c3d2d-388">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-388">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c3d2d-389">Este exemplo retorna uma lista resumida de todas as regras de anti-phishing junto com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-389">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="c3d2d-390">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-390">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="c3d2d-391">Este exemplo retorna todos os valores de propriedade da regra anti-Phish chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-391">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="c3d2d-392">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-392">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="c3d2d-393">Usar o PowerShell para modificar políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c3d2d-393">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="c3d2d-394">Além dos seguintes itens, as mesmas configurações estão disponíveis quando você modifica uma política de anti-phishing no PowerShell como quando você cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anti-golpe](#step-1-use-powershell-to-create-an-anti-phish-policy) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-394">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="c3d2d-395">A opção _MakeDefault_ que transforma a política especificada na política padrão (aplicada a todos, sempre a prioridade **mais baixa** e não é possível excluí-la) só está disponível quando você modifica uma política de Phish no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-395">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="c3d2d-396">Não é possível renomear uma política anti-phishing (o cmdlet **set-AntiPhishPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-396">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c3d2d-397">Ao renomear uma política anti-phishing no centro de conformidade & segurança, você estará apenas renomeando a _regra_ anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-397">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="c3d2d-398">Para modificar uma política de anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-398">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c3d2d-399">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-399">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="c3d2d-400">Usar o PowerShell para modificar as regras de anti-golpe</span><span class="sxs-lookup"><span data-stu-id="c3d2d-400">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="c3d2d-401">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite que você crie uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-401">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c3d2d-402">Para habilitar ou desabilitar regras antispam existentes, confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-402">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="c3d2d-403">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-403">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="c3d2d-404">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) , anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-404">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="c3d2d-405">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-405">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c3d2d-406">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-406">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="c3d2d-407">Usar o PowerShell para habilitar ou desabilitar regras de Phish</span><span class="sxs-lookup"><span data-stu-id="c3d2d-407">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="c3d2d-408">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política de anti-phishing atribuídas).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-408">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="c3d2d-409">Você não pode habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-409">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="c3d2d-410">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-410">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="c3d2d-411">Este exemplo desabilita a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-411">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c3d2d-412">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-412">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c3d2d-413">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-413">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="c3d2d-414">Usar o PowerShell para definir a prioridade de regras de Phish</span><span class="sxs-lookup"><span data-stu-id="c3d2d-414">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="c3d2d-415">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-415">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c3d2d-416">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-416">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c3d2d-417">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-417">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c3d2d-418">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-418">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c3d2d-419">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-419">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c3d2d-420">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-420">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c3d2d-421">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-421">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="c3d2d-422">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-422">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="c3d2d-423">**Observações** :</span><span class="sxs-lookup"><span data-stu-id="c3d2d-423">**Notes** :</span></span>

- <span data-ttu-id="c3d2d-424">Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="c3d2d-424">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="c3d2d-425">A política de anti-phishing padrão não tem uma regra antiphishing correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-425">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="c3d2d-426">Usar o PowerShell para remover políticas antispam</span><span class="sxs-lookup"><span data-stu-id="c3d2d-426">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="c3d2d-427">Quando você usa o PowerShell para remover uma política de Phish, a regra anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-427">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="c3d2d-428">Para remover uma política de anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-428">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c3d2d-429">Este exemplo remove a política de anti-golpe chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-429">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c3d2d-430">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-430">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="c3d2d-431">Usar o PowerShell para remover regras de Phish</span><span class="sxs-lookup"><span data-stu-id="c3d2d-431">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="c3d2d-432">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-Phish correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-432">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="c3d2d-433">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-433">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="c3d2d-434">Este exemplo remove a regra anti-Phish chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-434">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c3d2d-435">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="c3d2d-435">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c3d2d-436">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="c3d2d-436">How do you know these procedures worked?</span></span>

<span data-ttu-id="c3d2d-437">Para verificar se você configurou com êxito as políticas anti-phishing no Microsoft defender para Office 365, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-437">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="c3d2d-438">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-438">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="c3d2d-439">Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="c3d2d-439">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="c3d2d-440">Para exibir mais detalhes, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-440">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="c3d2d-441">Selecione a política na lista e exiba os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-441">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="c3d2d-442">Clique em **política padrão** e visualize os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="c3d2d-442">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="c3d2d-443">No PowerShell do Exchange Online, substitua \<Name\> o nome da política ou regra e execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="c3d2d-443">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
