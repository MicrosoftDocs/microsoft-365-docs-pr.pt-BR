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
ms.openlocfilehash: 8b8a43127c4e445ab214a709bb27e5e29100d358
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165710"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-103">Configurar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fd065-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="fd065-104">**Applies to**</span></span>
- [<span data-ttu-id="fd065-105">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="fd065-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="fd065-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd065-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fd065-107">As políticas anti-phishing no [Microsoft Defender para Office 365](office-365-atp.md) podem ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="fd065-108">Para obter mais informações sobre as diferenças entre as políticas anti-phishing na Proteção do Exchange Online (EOP) e políticas anti-phishing no Microsoft Defender para Office 365, consulte [Proteção anti-phishing.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="fd065-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="fd065-109">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="fd065-110">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fd065-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="fd065-111">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fd065-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="fd065-112">Você pode configurar políticas anti-phishing no Centro de Conformidade e Segurança & ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fd065-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="fd065-113">Para obter informações sobre como configurar as políticas anti-phishing mais limitadas disponíveis nas organizações do Proteção do Exchange Online (ou seja, organizações sem o Microsoft Defender para Office 365), consulte Configurar políticas [anti-phishing no EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="fd065-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="fd065-114">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="fd065-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="fd065-115">**A política anti-phishing:** especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.</span><span class="sxs-lookup"><span data-stu-id="fd065-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="fd065-116">**A regra anti-phishing:** especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="fd065-117">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas anti-phishing no Centro de Conformidade & e Segurança:</span><span class="sxs-lookup"><span data-stu-id="fd065-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fd065-118">Ao criar uma política, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="fd065-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fd065-119">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitada ou desabilitada e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="fd065-120">Todas as outras configurações modificam a política anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="fd065-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="fd065-121">Quando você remove uma política, a regra anti-phishing e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="fd065-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="fd065-122">No PowerShell do Exchange Online, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="fd065-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fd065-123">Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online para configurar políticas [anti-phishing no Microsoft Defender para Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fd065-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="fd065-124">Cada organização do Microsoft Defender para Office 365 tem uma política antiphishing interna chamada Office365 AntiPhish Default que tem estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="fd065-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="fd065-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="fd065-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="fd065-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="fd065-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="fd065-127">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="fd065-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="fd065-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="fd065-129">Para aumentar a eficácia da proteção anti-phishing no Microsoft Defender para Office 365, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="fd065-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fd065-130">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="fd065-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fd065-131">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fd065-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fd065-132">Para ir diretamente para a **página anti-phishing da ATP,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="fd065-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="fd065-133">Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fd065-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="fd065-134">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="fd065-134">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fd065-135">Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="fd065-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="fd065-136">Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** <sup>\*</sup> Segurança.</span><span class="sxs-lookup"><span data-stu-id="fd065-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="fd065-137">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fd065-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="fd065-138">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="fd065-138">**Notes**:</span></span>

  - <span data-ttu-id="fd065-139">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd065-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fd065-140">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="fd065-140">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="fd065-141">O **grupo de função Gerenciamento da Organização Somente** Exibição no Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também oferece acesso somente leitura ao <sup>\*</sup> recurso.</span><span class="sxs-lookup"><span data-stu-id="fd065-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="fd065-142"><sup>\*</sup> No Centro de Conformidade & segurança, o acesso somente leitura permite que os usuários vejam as configurações de políticas anti-phishing personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fd065-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="fd065-143">Os usuários somente leitura não podem ver as configurações na política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="fd065-144">Para nossas configurações recomendadas para políticas anti-phishing no Microsoft Defender para Office 365, confira a política anti-phishing nas configurações do Defender para [Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="fd065-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="fd065-145">Permita até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="fd065-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="fd065-146">Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte Ordem e [precedência da proteção de email.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="fd065-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-147">Usar o Centro de Conformidade & segurança para criar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fd065-148">Criar uma política anti-phishing personalizada no Centro de Conformidade e Segurança cria a regra anti-phishing e a política anti-phish & ing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="fd065-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="fd065-149">Ao criar uma política anti-phishing, você só pode especificar o nome, a descrição e o filtro de destinatário que identifica a quem a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="fd065-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="fd065-150">Depois de criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="fd065-151">No Centro de Conformidade & segurança, vá para **política** de gerenciamento de ameaças \>  \> **atp anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fd065-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-152">Na página **Anti-phishing,** clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="fd065-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="fd065-153">O **assistente Criar uma nova política anti-phishing** é aberto.</span><span class="sxs-lookup"><span data-stu-id="fd065-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="fd065-154">Na página **Nomear sua política,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fd065-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="fd065-155">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="fd065-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="fd065-156">**Descrição**: digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="fd065-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fd065-157">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fd065-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fd065-158">Na página **Aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="fd065-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="fd065-159">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="fd065-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="fd065-160">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="fd065-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="fd065-161">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="fd065-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="fd065-162">Clique **em Adicionar uma condição.**</span><span class="sxs-lookup"><span data-stu-id="fd065-162">Click **Add a condition**.</span></span> <span data-ttu-id="fd065-163">No menu suspenso exibido, selecione uma condição em **Aplicado se:**</span><span class="sxs-lookup"><span data-stu-id="fd065-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="fd065-164">**O destinatário é:** Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fd065-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fd065-165">**O destinatário é membro de:** Especifica um ou mais grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fd065-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="fd065-166">**O domínio do destinatário** é: Especifica destinatários em um ou mais dos domínios aceitos configurados na organização.</span><span class="sxs-lookup"><span data-stu-id="fd065-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="fd065-167">Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**</span><span class="sxs-lookup"><span data-stu-id="fd065-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="fd065-168">Clique na caixa e role pela lista de valores a selecionar.</span><span class="sxs-lookup"><span data-stu-id="fd065-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="fd065-169">Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="fd065-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="fd065-170">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="fd065-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="fd065-171">Para remover entradas individuais, clique **no** ícone ![ Remover no ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="fd065-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="fd065-172">Para remover toda a condição, clique **no** ícone ![ Remover na ](../../media/scc-remove-icon.png) condição.</span><span class="sxs-lookup"><span data-stu-id="fd065-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="fd065-173">Para adicionar uma condição adicional, clique **em Adicionar uma condição** e selecione um valor restante em Aplicado **se**.</span><span class="sxs-lookup"><span data-stu-id="fd065-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="fd065-174">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**.</span><span class="sxs-lookup"><span data-stu-id="fd065-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="fd065-175">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="fd065-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fd065-176">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fd065-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fd065-177">Na página **Revisar as configurações** exibida, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="fd065-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="fd065-178">Você pode clicar **em Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="fd065-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="fd065-179">Quando terminar, clique em **Criar esta política.**</span><span class="sxs-lookup"><span data-stu-id="fd065-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="fd065-180">Clique **em OK** na caixa de diálogo de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="fd065-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="fd065-181">Depois de criar a política anti-phishing com essas configurações gerais, use as instruções na próxima seção para definir as configurações de proteção na política.</span><span class="sxs-lookup"><span data-stu-id="fd065-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-182">Usar o Centro de Conformidade & segurança para modificar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fd065-183">Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalificou.</span><span class="sxs-lookup"><span data-stu-id="fd065-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="fd065-184">Se você ainda não estiver lá, abra o Centro de  Conformidade e Segurança & e vá para a Política de Gerenciamento de Ameaças \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="fd065-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-185">Selecione a política anti-phishing personalizada que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="fd065-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="fd065-186">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="fd065-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="fd065-187">O **flyout \<name\> Editar sua** política é exibido.</span><span class="sxs-lookup"><span data-stu-id="fd065-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="fd065-188">Clicar em **Editar** em qualquer seção lhe dá acesso às configurações dessa seção.</span><span class="sxs-lookup"><span data-stu-id="fd065-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="fd065-189">As etapas a seguir são apresentadas na ordem em que as seções aparecem, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).</span><span class="sxs-lookup"><span data-stu-id="fd065-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="fd065-190">Depois de  clicar em Editar em uma seção, as configurações disponíveis são apresentadas em um formato  de assistente, mas  você  pode pular dentro das páginas em qualquer ordem e pode clicar em Salvar em qualquer página (ou ![ ](../../media/scc-remove-icon.png) **\<name\>** cancelar ou fechar ícone para retornar à página Editar sua política (você não precisa visitar a última página do assistente para salvar ou sair).</span><span class="sxs-lookup"><span data-stu-id="fd065-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="fd065-191">**Configuração de** política: **clique** em Editar para modificar as mesmas configurações que estavam disponíveis quando você [criou](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) a política na seção anterior:</span><span class="sxs-lookup"><span data-stu-id="fd065-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="fd065-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fd065-192">**Name**</span></span>
   - <span data-ttu-id="fd065-193">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fd065-193">**Description**</span></span>
   - <span data-ttu-id="fd065-194">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="fd065-194">**Applied to**</span></span>
   - <span data-ttu-id="fd065-195">**Revise suas configurações**</span><span class="sxs-lookup"><span data-stu-id="fd065-195">**Review your settings**</span></span>

   <span data-ttu-id="fd065-196">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="fd065-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="fd065-197">**Representação:** clique **em Editar** para modificar os senders protegidos e os domínios protegidos na política.</span><span class="sxs-lookup"><span data-stu-id="fd065-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="fd065-198">Essas configurações são uma condição para a política que identifica remetentes falsas a procurar (individualmente ou por domínio) no endereço De das mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="fd065-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="fd065-199">Para obter mais informações, consulte Configurações de representação [em políticas anti-phishing no Microsoft Defender para Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="fd065-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="fd065-200">**Adicionar usuários para proteger:** o valor padrão é **Off**.</span><span class="sxs-lookup"><span data-stu-id="fd065-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="fd065-201">Para acioná-lo, deslize a alternância para **Ativar** e clique no botão Adicionar **usuário** que aparece.</span><span class="sxs-lookup"><span data-stu-id="fd065-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="fd065-202">No **flyout Adicionar usuário** exibido, configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd065-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="fd065-203">**Endereço de email**:</span><span class="sxs-lookup"><span data-stu-id="fd065-203">**Email address**:</span></span>

       - <span data-ttu-id="fd065-204">Clique na caixa e role a lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="fd065-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="fd065-205">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário.</span><span class="sxs-lookup"><span data-stu-id="fd065-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="fd065-206">Para remover uma entrada, clique **no** ![ ícone Remover do ](../../media/scc-remove-icon.png) usuário.</span><span class="sxs-lookup"><span data-stu-id="fd065-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="fd065-207">**Nome:** esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="fd065-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="fd065-208">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="fd065-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="fd065-209">Para editar uma entrada existente, selecione o usuário protegido na lista.</span><span class="sxs-lookup"><span data-stu-id="fd065-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="fd065-210">Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente).</span><span class="sxs-lookup"><span data-stu-id="fd065-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="fd065-211">Você não pode especificar o mesmo usuário protegido em várias políticas.</span><span class="sxs-lookup"><span data-stu-id="fd065-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="fd065-212">A proteção contra representação de usuário não funcionará se o remetente e o destinatário se comunicaram anteriormente por email.</span><span class="sxs-lookup"><span data-stu-id="fd065-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="fd065-213">Se o remetente e o destinatário nunca se comunicarem por email, a mensagem será identificada como uma tentativa de representação.</span><span class="sxs-lookup"><span data-stu-id="fd065-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="fd065-214">**Adicionar domínios para proteger:** de configurar uma ou ambas as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fd065-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="fd065-215">**Inclua automaticamente os domínios que eu tenho:** o valor padrão é **Off**.</span><span class="sxs-lookup"><span data-stu-id="fd065-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="fd065-216">Para a ligar, deslize a alternância para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="fd065-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="fd065-217">**Incluir domínios personalizados:** o valor padrão é **Off**.</span><span class="sxs-lookup"><span data-stu-id="fd065-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="fd065-218">Para acioná-lo, deslize a alternância para **Ativar** e, na caixa Adicionar **domínios,** digite o nome de domínio (por exemplo, contoso.com), pressione ENTER e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fd065-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="fd065-219">Você pode ter no máximo 50 domínios em todas as políticas anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="fd065-220">**Ações**: Clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="fd065-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="fd065-221">**Se o email** for enviado por um usuário personificado: configure uma das seguintes ações para mensagens em que o remetente spoofed é um dos usuários protegidos que você especificou em Adicionar usuários para **proteger:**</span><span class="sxs-lookup"><span data-stu-id="fd065-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="fd065-222">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="fd065-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="fd065-223">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="fd065-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="fd065-224">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="fd065-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="fd065-225">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="fd065-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="fd065-226">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="fd065-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="fd065-227">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="fd065-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="fd065-228">**Se o email** for enviado por um domínio personificado: configure uma das seguintes ações para mensagens em que o remetente spoofed está em um dos domínios protegidos que você especificou em Adicionar **domínios** para proteger:</span><span class="sxs-lookup"><span data-stu-id="fd065-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="fd065-229">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="fd065-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="fd065-230">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="fd065-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="fd065-231">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="fd065-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="fd065-232">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="fd065-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="fd065-233">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="fd065-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="fd065-234">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="fd065-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="fd065-235">Clique **em ativar as dicas de segurança de** representação e de configurar qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fd065-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="fd065-236">**Mostrar dica para usuários personificados:** o valor padrão é **Off**.</span><span class="sxs-lookup"><span data-stu-id="fd065-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="fd065-237">Para a ligar, deslize a alternância para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="fd065-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="fd065-238">**Mostrar dica para domínios personificados:** o valor padrão é **Off**.</span><span class="sxs-lookup"><span data-stu-id="fd065-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="fd065-239">Para a ligar, deslize a alternância para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="fd065-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="fd065-240">**Dica de apresentação para caracteres incomuns:** o valor padrão é **Off**.</span><span class="sxs-lookup"><span data-stu-id="fd065-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="fd065-241">Para a ligar, deslize a alternância para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="fd065-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="fd065-242">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd065-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="fd065-243">**Inteligência de caixa de correio:**</span><span class="sxs-lookup"><span data-stu-id="fd065-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="fd065-244">**Habilitar a inteligência de** caixa de correio? : O valor padrão é **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="fd065-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="fd065-245">Para desativar, deslize a alternância para **Desligado.**</span><span class="sxs-lookup"><span data-stu-id="fd065-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="fd065-246">**Habilitar a inteligência de caixa** de correio com base em proteção contra representação? : Esta configuração só estará disponível se **Habilitar** inteligência de caixa de correio? está **ativado**.</span><span class="sxs-lookup"><span data-stu-id="fd065-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="fd065-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span><span class="sxs-lookup"><span data-stu-id="fd065-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="fd065-248">**Não aplicar nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="fd065-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="fd065-249">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="fd065-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="fd065-250">**Mover mensagem para a pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="fd065-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="fd065-251">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="fd065-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="fd065-252">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="fd065-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="fd065-253">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="fd065-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="fd065-254">**Adicionar domínios e senders confiáveis:** especifique exceções para a política:</span><span class="sxs-lookup"><span data-stu-id="fd065-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="fd065-255">**Senders confiáveis:**</span><span class="sxs-lookup"><span data-stu-id="fd065-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="fd065-256">Clique na caixa e role a lista de usuários para selecionar.</span><span class="sxs-lookup"><span data-stu-id="fd065-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="fd065-257">Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário.</span><span class="sxs-lookup"><span data-stu-id="fd065-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="fd065-258">Para remover uma entrada, clique **no** ![ ícone Remover do ](../../media/scc-remove-icon.png) usuário.</span><span class="sxs-lookup"><span data-stu-id="fd065-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="fd065-259">**Domínios confiáveis:** insira o nome de domínio (por exemplo, contoso.com), pressione ENTER e repita conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fd065-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="fd065-260">**Revise suas configurações:** em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="fd065-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="fd065-261">Você pode clicar **em Editar** em cada seção para voltar à página relevante.</span><span class="sxs-lookup"><span data-stu-id="fd065-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="fd065-262">Você pode alternar as seguintes  configurações **diretamente** nesta página:</span><span class="sxs-lookup"><span data-stu-id="fd065-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="fd065-263">**Usuários protegidos**</span><span class="sxs-lookup"><span data-stu-id="fd065-263">**Protected users**</span></span>
       - <span data-ttu-id="fd065-264">**Domínios protegidos** \> **Incluir domínios que eu tenho**</span><span class="sxs-lookup"><span data-stu-id="fd065-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="fd065-265">**Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)</span><span class="sxs-lookup"><span data-stu-id="fd065-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="fd065-266">**Inteligência da caixa de correio**</span><span class="sxs-lookup"><span data-stu-id="fd065-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="fd065-267">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="fd065-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="fd065-268">**Spoof**:  Clique em Editar para ativar ou desativar a inteligência contra spoof, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação para aplicar às mensagens de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="fd065-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="fd065-269">Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="fd065-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="fd065-270">Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.</span><span class="sxs-lookup"><span data-stu-id="fd065-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="fd065-271">**Configurações de filtro de spoofing:** o valor padrão é **On,** e recomendamos que você o deixe em.</span><span class="sxs-lookup"><span data-stu-id="fd065-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="fd065-272">Para desativar, deslize a alternância para **Desligado.**</span><span class="sxs-lookup"><span data-stu-id="fd065-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="fd065-273">Para obter mais informações, [consulte Configurar a inteligência contra spoof no EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="fd065-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="fd065-274">Você não precisará desabilitar a proteção anti-spoofing se seu registro MX não apontar para o Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores.</span><span class="sxs-lookup"><span data-stu-id="fd065-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="fd065-275">Para obter instruções, consulte [Filtragem aprimorada para conectores no Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="fd065-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="fd065-276">**Habilitar o recurso Remetente Não Autenticado:** o valor padrão é **Ativado.**</span><span class="sxs-lookup"><span data-stu-id="fd065-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="fd065-277">Para desativar, deslize a alternância para **Desligado.**</span><span class="sxs-lookup"><span data-stu-id="fd065-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="fd065-278">**Ações:** especifique a ação a ser tomada em mensagens que não têm inteligência contra spoof:</span><span class="sxs-lookup"><span data-stu-id="fd065-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="fd065-279">**Se o email for enviado por alguém que não tem permissão para fazer a spoof do seu domínio:**</span><span class="sxs-lookup"><span data-stu-id="fd065-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="fd065-280">**Mover mensagem para as pastas de Lixo Eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="fd065-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="fd065-281">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="fd065-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="fd065-282">**Revise suas configurações:** em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="fd065-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="fd065-283">Você pode clicar **em Editar** em cada seção para voltar à página relevante.</span><span class="sxs-lookup"><span data-stu-id="fd065-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="fd065-284">Você pode alternar as seguintes  configurações **diretamente** nesta página:</span><span class="sxs-lookup"><span data-stu-id="fd065-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="fd065-285">**Habilitar a proteção antispoofing**</span><span class="sxs-lookup"><span data-stu-id="fd065-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="fd065-286">**Habilitar o recurso Remetente Não Autenticado**</span><span class="sxs-lookup"><span data-stu-id="fd065-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="fd065-287">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="fd065-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="fd065-288">**Configurações avançadas:** clique **em Editar** para configurar os limites avançados de phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="fd065-289">Para saber mais, confira [Os limites avançados de phishing em políticas anti-phishing no Microsoft Defender para Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="fd065-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="fd065-290">**Limites avançados de phishing:** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd065-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="fd065-291">**1 - Padrão** (este é o valor padrão.)</span><span class="sxs-lookup"><span data-stu-id="fd065-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="fd065-292">**2 - Agressivo**</span><span class="sxs-lookup"><span data-stu-id="fd065-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="fd065-293">**3 - Mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="fd065-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="fd065-294">**4 - Mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="fd065-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="fd065-295">**Revise suas configurações:** clique **em Editar** para voltar à **página De limites de phishing** avançados.</span><span class="sxs-lookup"><span data-stu-id="fd065-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="fd065-296">Quando terminar, clique em **Salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="fd065-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="fd065-297">De volta à **página Editar sua política, \<Name\>** revise suas configurações e clique em **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="fd065-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-298">Usar o Centro de Conformidade & segurança para modificar a política anti-phishing padrão no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fd065-299">A política antiphishing padrão no Microsoft Defender para Office 365 é chamada de Office365 AntiPhish Default e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="fd065-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="fd065-300">Para modificar a política anti-phishing padrão, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd065-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="fd065-301">No Centro de Conformidade & segurança,  vá para \>  \> **anti-phishing da Política de Gerenciamento** de Ameaças da ATP.</span><span class="sxs-lookup"><span data-stu-id="fd065-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-302">Na página **Anti-phishing,** clique em **Política padrão.**</span><span class="sxs-lookup"><span data-stu-id="fd065-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="fd065-303">A **página Editar sua política Padrão AntiPhish do Office365 é** exibida.</span><span class="sxs-lookup"><span data-stu-id="fd065-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="fd065-304">As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="fd065-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="fd065-305">**Representação**</span><span class="sxs-lookup"><span data-stu-id="fd065-305">**Impersonation**</span></span>
   - <span data-ttu-id="fd065-306">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="fd065-306">**Spoof**</span></span>
   - <span data-ttu-id="fd065-307">**Configurações avançadas**</span><span class="sxs-lookup"><span data-stu-id="fd065-307">**Advanced settings**</span></span>

   <span data-ttu-id="fd065-308">As configurações a seguir não estão disponíveis quando você modifica a política padrão:</span><span class="sxs-lookup"><span data-stu-id="fd065-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="fd065-309">Você pode  ver a seção de configuração de política e os valores, mas não há **nenhum** link de edição, portanto, você não pode modificar as configurações (nome da política, descrição e a quem a política se aplica (aplica-se a todos os destinatários)).</span><span class="sxs-lookup"><span data-stu-id="fd065-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="fd065-310">Não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="fd065-311">Não é possível alterar a prioridade da política padrão (ela é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="fd065-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="fd065-312">Na página **Editar sua política Padrão AntiPhish do Office365,** revise suas configurações e clique em **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="fd065-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-313">Habilitar ou desabilitar políticas anti-phishing personalizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="fd065-314">No Centro de Conformidade & segurança, vá para **política** de gerenciamento de ameaças \>  \> **atp anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fd065-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-315">Observe o valor na coluna **Status:**</span><span class="sxs-lookup"><span data-stu-id="fd065-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="fd065-316">Deslize a alternância para **Desabilitar** para desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="fd065-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="fd065-317">Deslize a alternância para **Ativado** para habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="fd065-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="fd065-318">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-319">Definir a prioridade de políticas anti-phishing personalizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fd065-320">Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="fd065-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="fd065-321">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="fd065-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fd065-322">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="fd065-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fd065-323">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="fd065-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="fd065-324">As políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem o **valor** prioridade 0).</span><span class="sxs-lookup"><span data-stu-id="fd065-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="fd065-325">A política antiphishing padrão chamada Office365 AntiPhish Default tem o valor de prioridade personalizado **Menor,** e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="fd065-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="fd065-326">**Observação:** no Centro de Conformidade & segurança, você só pode alterar a prioridade da política anti-phishing depois de criar a política.</span><span class="sxs-lookup"><span data-stu-id="fd065-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="fd065-327">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phishing (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="fd065-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="fd065-328">Para alterar a prioridade de  uma política, clique em Aumentar prioridade ou Diminuir prioridade  nas propriedades da política (não é possível modificar diretamente o número prioridade no Centro de Conformidade e Segurança &). </span><span class="sxs-lookup"><span data-stu-id="fd065-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="fd065-329">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="fd065-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="fd065-330">No Centro de Conformidade & segurança,  vá para \>  \> **anti-phishing da Política de Gerenciamento** de Ameaças da ATP.</span><span class="sxs-lookup"><span data-stu-id="fd065-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-331">Selecione a política que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="fd065-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="fd065-332">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="fd065-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="fd065-333">O **flyout \<name\> Editar sua** política é exibido.</span><span class="sxs-lookup"><span data-stu-id="fd065-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="fd065-334">A política anti-phishing personalizada com o **valor** prioridade **0** tem apenas o **botão** Diminuir prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="fd065-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="fd065-335">A política anti-phishing personalizada com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão** Aumentar prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="fd065-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="fd065-336">Se você tiver três ou mais políticas anti-phishing personalizadas, as  políticas  entre os valores de prioridade mais alta e mais baixa terão os botões Aumentar prioridade e Diminuir prioridade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fd065-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="fd065-337">Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor prioridade.**</span><span class="sxs-lookup"><span data-stu-id="fd065-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="fd065-338">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="fd065-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-339">Usar o Centro de Conformidade & segurança para exibir políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="fd065-340">No Centro de Conformidade & segurança e  vá para política de gerenciamento de ameaças \>  \> **atp anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fd065-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-341">Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="fd065-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="fd065-342">Selecione uma política anti-phishing personalizada que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="fd065-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="fd065-343">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="fd065-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="fd065-344">Clique **em Política Padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="fd065-345">O **menu \<name\> Editar seu menu** desdoado de política é exibido, onde você pode exibir as configurações e os valores.</span><span class="sxs-lookup"><span data-stu-id="fd065-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-346">Usar o Centro de Conformidade & segurança para remover políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="fd065-347">No Centro de Conformidade & segurança,  vá para \>  \> **anti-phishing da Política de Gerenciamento** de Ameaças da ATP.</span><span class="sxs-lookup"><span data-stu-id="fd065-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fd065-348">Selecione a política que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="fd065-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="fd065-349">Se ele já estiver selecionado, desmarque-o e selecione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="fd065-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="fd065-350">No flyout **Editar a política \<name\>** exibida, clique em Excluir política e, em seguida, clique em **Sim** na caixa de diálogo de aviso exibida.</span><span class="sxs-lookup"><span data-stu-id="fd065-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="fd065-351">Não é possível remover a política padrão.</span><span class="sxs-lookup"><span data-stu-id="fd065-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd065-352">Usar o PowerShell do Exchange Online para configurar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fd065-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fd065-353">Conforme descrito anteriormente, uma política anti-spam consiste em uma política anti-phishing e uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="fd065-354">No PowerShell do Exchange Online, a diferença entre políticas anti-phishing e regras anti-phishing é aparente.</span><span class="sxs-lookup"><span data-stu-id="fd065-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="fd065-355">Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia regras antiphish usando os cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="fd065-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="fd065-356">No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phishing que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="fd065-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fd065-357">No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-phishing separadamente.</span><span class="sxs-lookup"><span data-stu-id="fd065-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="fd065-358">Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="fd065-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="fd065-359">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="fd065-360">Criar uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="fd065-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fd065-361">Crie a política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="fd065-362">Crie a regra anti-phishing que especifica a política anti-phishing à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="fd065-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="fd065-363">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="fd065-363">**Notes**:</span></span>

- <span data-ttu-id="fd065-364">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="fd065-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="fd065-365">Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="fd065-366">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no Centro de Conformidade e Segurança até que você crie & a política:</span><span class="sxs-lookup"><span data-stu-id="fd065-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="fd065-367">Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="fd065-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="fd065-368">Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="fd065-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="fd065-369">Uma nova política anti-phishing que você cria no Power & Shell não fica visível no Centro de Conformidade e Segurança até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="fd065-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="fd065-370">Etapa 1: Usar o PowerShell para criar uma política anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="fd065-371">Para criar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="fd065-372">Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fd065-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="fd065-373">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="fd065-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="fd065-374">A descrição é: política do departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fd065-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="fd065-375">Habilita a proteção de domínios da organização para todos os domínios aceitos e a proteção de domínios direcionados para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="fd065-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="fd065-376">Especifica MaiIato (mfujito@fabrikam.com) como o usuário a ser protegido contra representação.</span><span class="sxs-lookup"><span data-stu-id="fd065-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="fd065-377">Habilita a inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="fd065-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="fd065-378">Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.</span><span class="sxs-lookup"><span data-stu-id="fd065-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="fd065-379">Habilita dicas de segurança.</span><span class="sxs-lookup"><span data-stu-id="fd065-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="fd065-380">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="fd065-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="fd065-381">Etapa 2: Usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="fd065-382">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="fd065-383">Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="fd065-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="fd065-384">A regra é associada à política anti-phishing chamada Quarentena de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fd065-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="fd065-385">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fd065-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="fd065-386">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="fd065-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="fd065-387">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="fd065-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="fd065-388">Usar o PowerShell para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="fd065-389">Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fd065-390">Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="fd065-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="fd065-391">Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="fd065-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="fd065-392">Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="fd065-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="fd065-393">Usar o PowerShell para exibir regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="fd065-394">Para exibir as regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fd065-395">Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="fd065-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="fd065-396">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fd065-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="fd065-397">Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="fd065-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="fd065-398">Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="fd065-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="fd065-399">Usar o PowerShell para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="fd065-400">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria a política conforme descrito na Etapa 1: Use o PowerShell para criar uma seção de política [anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fd065-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="fd065-401">A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre com prioridade mais baixa e você não pode excluí-la) só estará disponível quando você modificar uma política anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd065-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="fd065-402">Não é possível renomear uma política antiphish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="fd065-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fd065-403">Ao renomear uma política anti-phish & ing no Centro de Conformidade e Segurança, você está apenas renomeando a regra _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="fd065-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="fd065-404">Para modificar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fd065-405">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="fd065-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="fd065-406">Usar o PowerShell para modificar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="fd065-407">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="fd065-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fd065-408">Para habilitar ou desabilitar regras anti-phishing existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="fd065-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="fd065-409">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd065-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="fd065-410">As mesmas configurações estão disponíveis quando você cria uma regra conforme descrito na Etapa 2: Usar o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fd065-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="fd065-411">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fd065-412">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="fd065-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="fd065-413">Usar o PowerShell para habilitar ou desabilitar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="fd065-414">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída).</span><span class="sxs-lookup"><span data-stu-id="fd065-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="fd065-415">Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="fd065-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="fd065-416">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="fd065-417">Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fd065-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="fd065-418">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="fd065-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="fd065-419">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="fd065-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="fd065-420">Usar o PowerShell para definir a prioridade das regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="fd065-421">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="fd065-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fd065-422">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="fd065-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fd065-423">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="fd065-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fd065-424">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="fd065-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fd065-425">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="fd065-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fd065-426">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fd065-427">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="fd065-427">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="fd065-428">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="fd065-428">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="fd065-429">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="fd065-429">**Notes**:</span></span>

- <span data-ttu-id="fd065-430">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="fd065-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="fd065-431">A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade inmodificável **Menor.**</span><span class="sxs-lookup"><span data-stu-id="fd065-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="fd065-432">Usar o PowerShell para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="fd065-433">Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="fd065-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="fd065-434">Para remover uma política anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fd065-435">Este exemplo remove a política anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fd065-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fd065-436">Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="fd065-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="fd065-437">Usar o PowerShell para remover regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fd065-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="fd065-438">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="fd065-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="fd065-439">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fd065-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="fd065-440">Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fd065-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="fd065-441">Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="fd065-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fd065-442">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="fd065-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="fd065-443">Para verificar se você configurou com êxito as políticas anti-phishing no Microsoft Defender para Office 365, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="fd065-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="fd065-444">No Centro de Conformidade & segurança,  vá para \>  \> **anti-phishing da Política de Gerenciamento** de Ameaças da ATP.</span><span class="sxs-lookup"><span data-stu-id="fd065-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="fd065-445">Verifique a lista de políticas, seus **valores de Status** e seus valores **de** Prioridade.</span><span class="sxs-lookup"><span data-stu-id="fd065-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fd065-446">Para exibir mais detalhes, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="fd065-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="fd065-447">Selecione a política na lista e veja os detalhes no flyout.</span><span class="sxs-lookup"><span data-stu-id="fd065-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="fd065-448">Clique **em Política** Padrão e veja os detalhes no flyout.</span><span class="sxs-lookup"><span data-stu-id="fd065-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="fd065-449">No PowerShell do Exchange Online, substitua pelo nome da política ou regra, execute o seguinte comando \<Name\> e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="fd065-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
