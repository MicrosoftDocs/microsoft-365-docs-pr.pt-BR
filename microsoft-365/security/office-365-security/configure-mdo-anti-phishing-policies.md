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
ms.openlocfilehash: 1a948604f11064f2c1fefcc441adc4a9792ac918
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108434"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a590b-103">Configurar políticas anti-phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a590b-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a590b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a590b-104">**Applies to**</span></span>
- [<span data-ttu-id="a590b-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a590b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a590b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a590b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a590b-107">As políticas anti-phishing no [Microsoft Defender](defender-for-office-365.md) para Office 365 podem ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="a590b-108">Para obter mais informações sobre as diferenças entre políticas anti-phishing no Proteção do Exchange Online (EOP) e políticas anti-phishing no Microsoft Defender para Office 365, consulte [Proteção anti-phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a590b-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="a590b-109">Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a590b-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="a590b-110">Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a590b-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a590b-111">Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a590b-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a590b-112">Você pode configurar políticas anti-phishing no Defender para Office 365 no portal Microsoft 365 Defender ou no Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a590b-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="a590b-113">Para obter informações sobre como configurar o mais limitado em políticas anti-phishing disponíveis no Proteção do Exchange Online (ou seja, organizações sem o Defender para Office 365), consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a590b-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="a590b-114">Os elementos básicos de uma política anti-phishing são:</span><span class="sxs-lookup"><span data-stu-id="a590b-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="a590b-115">**A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.</span><span class="sxs-lookup"><span data-stu-id="a590b-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="a590b-116">**A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="a590b-117">A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="a590b-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="a590b-118">Ao criar uma política, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="a590b-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a590b-119">Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="a590b-120">Todas as outras configurações modificam a política anti-phishing associada.</span><span class="sxs-lookup"><span data-stu-id="a590b-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="a590b-121">Quando você remove uma política, a regra anti-phishing e a política anti-phishing associada são removidas.</span><span class="sxs-lookup"><span data-stu-id="a590b-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="a590b-122">No Exchange Online PowerShell, você gerencia a política e a regra separadamente.</span><span class="sxs-lookup"><span data-stu-id="a590b-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a590b-123">Para obter mais informações, consulte a seção Usar Exchange Online PowerShell para configurar políticas [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a590b-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="a590b-124">Cada defender para Office 365 organização tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="a590b-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="a590b-125">A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.</span><span class="sxs-lookup"><span data-stu-id="a590b-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a590b-126">A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último).</span><span class="sxs-lookup"><span data-stu-id="a590b-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a590b-127">As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="a590b-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="a590b-128">A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.</span><span class="sxs-lookup"><span data-stu-id="a590b-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a590b-129">Para aumentar a eficácia da proteção anti-phishing no Defender para Office 365, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="a590b-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a590b-130">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="a590b-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a590b-131">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a590b-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a590b-132">Para ir diretamente para a página **Anti-phishing,** use <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="a590b-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="a590b-133">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a590b-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a590b-134">Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="a590b-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a590b-135">Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="a590b-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a590b-136">Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** <sup>\*</sup> Segurança.</span><span class="sxs-lookup"><span data-stu-id="a590b-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="a590b-137">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a590b-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a590b-138">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a590b-138">**Notes**:</span></span>

  - <span data-ttu-id="a590b-139">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a590b-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a590b-140">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a590b-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a590b-141">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="a590b-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a590b-142">Para nossas configurações recomendadas para políticas anti-phishing no Defender para Office 365, consulte [Política anti-phishing](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)no Defender para Office 365 configurações .</span><span class="sxs-lookup"><span data-stu-id="a590b-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="a590b-143">Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="a590b-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="a590b-144">Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="a590b-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="a590b-145">Usar o portal Microsoft 365 Defender para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="a590b-146">Criar uma política anti-phishing personalizada no portal Microsoft 365 Defender cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="a590b-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a590b-147">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a590b-148">Na página **Anti-phishing,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="a590b-149">O assistente de política é aberto.</span><span class="sxs-lookup"><span data-stu-id="a590b-149">The policy wizard opens.</span></span> <span data-ttu-id="a590b-150">Na página **Nome da** política, configure estas configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="a590b-151">**Nome**: insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="a590b-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="a590b-152">**Descrição**: insira uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="a590b-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a590b-153">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a590b-154">Na página **Usuários, grupos e domínios** exibida, identifique os destinatários internos aos quais a política se aplica (condições do destinatário):</span><span class="sxs-lookup"><span data-stu-id="a590b-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="a590b-155">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="a590b-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a590b-156">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="a590b-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="a590b-157">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="a590b-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="a590b-158">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="a590b-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a590b-159">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="a590b-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a590b-160">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="a590b-160">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a590b-162">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="a590b-162">next to the value.</span></span>

   <span data-ttu-id="a590b-163">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="a590b-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a590b-164">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a590b-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="a590b-165">Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a590b-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a590b-166">Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a590b-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="a590b-167">**Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="a590b-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a590b-168">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="a590b-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a590b-169">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a590b-170">Na página **de proteção & phishing** exibida, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a590b-171">**Limite de email de phishing**: Use o controle deslizante para selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a590b-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="a590b-172">**1 - Standard** (Este é o valor padrão.)</span><span class="sxs-lookup"><span data-stu-id="a590b-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="a590b-173">**2 - Agressivo**</span><span class="sxs-lookup"><span data-stu-id="a590b-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="a590b-174">**3 - Mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="a590b-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="a590b-175">**4 - Mais agressivo**</span><span class="sxs-lookup"><span data-stu-id="a590b-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="a590b-176">Para obter mais informações, consulte [Limites avançados de phishing em políticas anti-phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)no Microsoft Defender para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="a590b-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="a590b-177">**Representação**: Essas configurações são uma condição para a política que identifica remetentes específicos a procurar (individualmente ou por domínio) no endereço From de mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="a590b-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="a590b-178">Para obter mais informações, consulte Configurações de representação [em políticas anti-phishing no Microsoft Defender para](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="a590b-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="a590b-179">Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente).</span><span class="sxs-lookup"><span data-stu-id="a590b-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="a590b-180">Não é possível especificar o mesmo usuário protegido em várias políticas.</span><span class="sxs-lookup"><span data-stu-id="a590b-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="a590b-181">A proteção de representação do usuário não funcionará se o remetente e o destinatário se comunicarem anteriormente por email.</span><span class="sxs-lookup"><span data-stu-id="a590b-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="a590b-182">Se o remetente e o destinatário nunca se comunicarem por email, a mensagem será identificada como uma tentativa de representação.</span><span class="sxs-lookup"><span data-stu-id="a590b-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="a590b-183">**Permitir que os usuários protejam**: O valor padrão está desligado (não selecionado).</span><span class="sxs-lookup"><span data-stu-id="a590b-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="a590b-184">Para acioná-lo, marque a caixa de seleção e clique no link **Gerenciar remetentes (nn)** exibido.</span><span class="sxs-lookup"><span data-stu-id="a590b-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="a590b-185">No **flyout Manage senders for impersonation protection** que aparece, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a590b-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="a590b-186">**Envios internos**: clique ![ em Adicionar ícone interno Selecione ](../../media/m365-cc-sc-add-internal-icon.png) **interno**.</span><span class="sxs-lookup"><span data-stu-id="a590b-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="a590b-187">No **flyout Adicionar envios** internos que aparece, clique na caixa e selecione um usuário interno na lista.</span><span class="sxs-lookup"><span data-stu-id="a590b-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="a590b-188">Você pode filtrar a lista digitando o usuário e selecionando o usuário dos resultados.</span><span class="sxs-lookup"><span data-stu-id="a590b-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="a590b-189">Você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente é mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="a590b-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="a590b-190">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="a590b-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a590b-191">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="a590b-191">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a590b-193">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="a590b-193">next to the value.</span></span>

         <span data-ttu-id="a590b-194">Quando terminar, clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="a590b-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="a590b-195">**Senders externos**: clique ![ em Adicionar ícone externo Selecione ](../../media/m365-cc-sc-create-icon.png) **externo**.</span><span class="sxs-lookup"><span data-stu-id="a590b-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="a590b-196">No flyout **Adicionar remetentes** externos que aparece,  insira um nome de exibição na caixa Adicionar um nome e um endereço de email na caixa **Adicionar** um email de fusão e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="a590b-197">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="a590b-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a590b-198">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="a590b-198">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a590b-200">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="a590b-200">next to the value.</span></span>

         <span data-ttu-id="a590b-201">Quando terminar, clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="a590b-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="a590b-202">De volta ao **flyout Gerenciar envios** para representação, você pode remover entradas selecionando uma ou mais entradas da lista.</span><span class="sxs-lookup"><span data-stu-id="a590b-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="a590b-203">Você pode pesquisar entradas usando a caixa ![ Pesquisar ícone ](../../media/m365-cc-sc-create-icon.png) **de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a590b-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="a590b-204">Depois de selecionar pelo menos uma entrada, será exibido o ícone Remover usuários selecionados Remover usuários selecionados, que você pode usar para ![ remover as entradas ](../../media/m365-cc-sc-remove-selected-users-icon.png)  selecionadas.</span><span class="sxs-lookup"><span data-stu-id="a590b-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="a590b-205">Quando terminar, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="a590b-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="a590b-206">**Habilitar domínios para proteger**: O valor padrão está desligado (não selecionado).</span><span class="sxs-lookup"><span data-stu-id="a590b-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="a590b-207">Para acioná-lo, marque a caixa de seleção e configure uma ou ambas as configurações a seguir que aparecem:</span><span class="sxs-lookup"><span data-stu-id="a590b-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="a590b-208">**Inclua os domínios que eu tenho:** Para ativar essa configuração, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="a590b-209">Para exibir os domínios que você possui, clique em **Exibir meus domínios**.</span><span class="sxs-lookup"><span data-stu-id="a590b-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="a590b-210">**Incluir domínios personalizados**: Para ativar essa configuração, selecione a caixa de seleção e clique no link **Gerenciar (nn) domínios personalizados** que aparece.</span><span class="sxs-lookup"><span data-stu-id="a590b-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="a590b-211">No flyout **Gerenciar domínios personalizados para** proteção de representação que aparece, clique em ![ Adicionar ícone Adicionar ](../../media/m365-cc-sc-create-icon.png) **domínios**.</span><span class="sxs-lookup"><span data-stu-id="a590b-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="a590b-212">No flyout **Adicionar domínios personalizados** que aparece, clique na caixa **Domínio,** insira um valor e pressione Enter ou selecione o valor exibido abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="a590b-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="a590b-213">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="a590b-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a590b-214">Para remover um valor existente, clique em remover ![ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="a590b-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="a590b-215">Quando terminar, clique em **Adicionar domínios**</span><span class="sxs-lookup"><span data-stu-id="a590b-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="a590b-216">Você pode ter no máximo 50 domínios em todas as políticas anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="a590b-217">De volta ao **flyout Gerenciar domínios personalizados** para representação, você pode remover entradas selecionando uma ou mais entradas da lista.</span><span class="sxs-lookup"><span data-stu-id="a590b-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="a590b-218">Você pode pesquisar entradas usando a caixa ![ Pesquisar ícone ](../../media/m365-cc-sc-create-icon.png) **de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a590b-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="a590b-219">Depois de selecionar pelo menos uma entrada, o ícone Excluir domínios Excluir será exibido, que você pode usar para ![ remover as entradas ](../../media/m365-cc-sc-delete-icon.png)  selecionadas.</span><span class="sxs-lookup"><span data-stu-id="a590b-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="a590b-220">**Adicione remetentes** e domínios confiáveis: : Especifique exceções de proteção de representação para a política clicando em **Gerenciar (nn) remetentes confiáveis e domínios(s)**.</span><span class="sxs-lookup"><span data-stu-id="a590b-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="a590b-221">No flyout **Gerenciar domínios personalizados para** proteção de representação que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="a590b-222">**Remetentes**: verifique se **a** guia Remetente está selecionada e clique em ![ Adicionar ícone de ](../../media/m365-cc-sc-create-icon.png) remetentes.</span><span class="sxs-lookup"><span data-stu-id="a590b-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="a590b-223">No **sobrevoo Adicionar remetentes** confiáveis que aparece, insira um endereço de email na caixa e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="a590b-224">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="a590b-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a590b-225">Para remover uma entrada existente, clique em ![ Excluir ícone ](../../media/m365-cc-sc-close-icon.png) da entrada.</span><span class="sxs-lookup"><span data-stu-id="a590b-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="a590b-226">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="a590b-227">**Domínios**: selecione a guia **Domínio** e clique ![ em Adicionar domínios ícone ](../../media/m365-cc-sc-create-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="a590b-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="a590b-228">No flyout **Adicionar domínios** confiáveis que aparece, clique na caixa **Domínio,** insira um valor e pressione Enter ou selecione o valor exibido abaixo da caixa.</span><span class="sxs-lookup"><span data-stu-id="a590b-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="a590b-229">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="a590b-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a590b-230">Para remover um valor existente, clique em remover ![ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="a590b-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="a590b-231">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="a590b-232">De volta ao **flyout Gerenciar domínios personalizados** para representação, você  pode remover entradas das guias **Remetente** e Domínio selecionando uma ou mais entradas da lista.</span><span class="sxs-lookup"><span data-stu-id="a590b-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="a590b-233">Você pode pesquisar entradas usando a caixa ![ Pesquisar ícone ](../../media/m365-cc-sc-create-icon.png) **de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a590b-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="a590b-234">Depois de selecionar pelo menos uma entrada, o ícone **Excluir** será exibido, que você pode usar para remover as entradas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="a590b-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="a590b-235">Quando terminar, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="a590b-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="a590b-236">**Habilitar a inteligência** de caixa de correio : o valor padrão está ativado (selecionado) e recomendamos que você o deixe ativado.</span><span class="sxs-lookup"><span data-stu-id="a590b-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="a590b-237">Para desativar, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="a590b-238">**Habilitar a proteção de representação baseada em inteligência:** essa configuração só estará disponível se **Habilitar** a inteligência de caixa de correio estiver ativada (selecionada).</span><span class="sxs-lookup"><span data-stu-id="a590b-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="a590b-239">Essa configuração permite que a inteligência de caixa de correio tome medidas em mensagens identificadas como tentativas de representação.</span><span class="sxs-lookup"><span data-stu-id="a590b-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="a590b-240">Especifique a ação a ser tomada na **configuração Se** a inteligência da caixa de correio detectar uma configuração de usuário personificado na próxima página.</span><span class="sxs-lookup"><span data-stu-id="a590b-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="a590b-241">Recomendamos ativar essa configuração selecionando a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="a590b-242">Para desativar essa configuração, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="a590b-243">**Spoof**: nesta seção, use a caixa de seleção Habilitar a inteligência de **spoof** para ativar ou desativar a inteligência de spoof.</span><span class="sxs-lookup"><span data-stu-id="a590b-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="a590b-244">O valor padrão está em (selecionado) e recomendamos que você o deixe em.</span><span class="sxs-lookup"><span data-stu-id="a590b-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="a590b-245">Especifique a ação a ser tomada em mensagens de envios com spoofed bloqueados na configuração Se a mensagem for detectada como **spoof** na próxima página.</span><span class="sxs-lookup"><span data-stu-id="a590b-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="a590b-246">Para desativar a inteligência de spoof, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a590b-247">Você não precisa desativar a proteção anti-spoofing se seu registro MX não apontar para Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores.</span><span class="sxs-lookup"><span data-stu-id="a590b-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="a590b-248">Para obter instruções, [consulte Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="a590b-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="a590b-249">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a590b-250">Na página **Ações** exibida, de acordo com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a590b-251">**Ações de mensagem**: Configure as seguintes ações nesta seção:</span><span class="sxs-lookup"><span data-stu-id="a590b-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="a590b-252">**Se a mensagem for detectada como** um usuário personificado : essa configuração estará disponível somente se você tiver selecionado Habilitar os usuários para **proteger** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="a590b-253">Selecione uma das seguintes ações na listada para mensagens em que o remetente é um dos usuários protegidos especificados na página anterior:</span><span class="sxs-lookup"><span data-stu-id="a590b-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="a590b-254">**Não aplique nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="a590b-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="a590b-255">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="a590b-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="a590b-256">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="a590b-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a590b-257">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="a590b-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="a590b-258">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="a590b-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="a590b-259">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="a590b-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="a590b-260">**Se a mensagem for detectada como** um domínio personificado : essa configuração estará disponível somente se você tiver selecionado Habilitar **domínios** para proteger na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="a590b-261">Selecione uma das seguintes ações na listada para mensagens em que o endereço de email do remetente está em um dos domínios protegidos especificados na página anterior:</span><span class="sxs-lookup"><span data-stu-id="a590b-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="a590b-262">**Não aplique nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="a590b-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="a590b-263">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="a590b-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="a590b-264">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="a590b-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a590b-265">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="a590b-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="a590b-266">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="a590b-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="a590b-267">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="a590b-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="a590b-268">**Se a inteligência de caixa de** correio detectar um usuário  personificado : essa configuração estará disponível somente se você tiver selecionado Habilitar inteligência para proteção de representação na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="a590b-269">Selecione uma das seguintes ações na listada para mensagens identificadas como tentativas de representação pela inteligência de caixa de correio:</span><span class="sxs-lookup"><span data-stu-id="a590b-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="a590b-270">**Não aplique nenhuma ação**</span><span class="sxs-lookup"><span data-stu-id="a590b-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="a590b-271">**Redirecionar mensagem para outros endereços de email**</span><span class="sxs-lookup"><span data-stu-id="a590b-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="a590b-272">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="a590b-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a590b-273">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="a590b-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="a590b-274">**Entregar a mensagem e adicionar outros endereços à linha Cc**</span><span class="sxs-lookup"><span data-stu-id="a590b-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="a590b-275">**Excluir a mensagem antes de ser entregue**</span><span class="sxs-lookup"><span data-stu-id="a590b-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="a590b-276">**Se a mensagem for detectada como** falsa : essa configuração estará disponível somente se você tiver selecionado Habilitar a inteligência de **spoof** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="a590b-277">Selecione uma das seguintes ações na listada para mensagens de envios com spoofed bloqueados:</span><span class="sxs-lookup"><span data-stu-id="a590b-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="a590b-278">**Mover mensagem para as pastas lixo eletrônico dos destinatários**</span><span class="sxs-lookup"><span data-stu-id="a590b-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="a590b-279">**Colocar em quarentena a mensagem**</span><span class="sxs-lookup"><span data-stu-id="a590b-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="a590b-280">**Dicas de segurança & indicadores**: Configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="a590b-281">**Mostrar o primeiro contato dica de segurança**: Para obter mais informações, consulte First contact [dica de segurança](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span><span class="sxs-lookup"><span data-stu-id="a590b-281">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="a590b-282">**Mostrar a identidade do usuário dica de segurança**: Essa configuração só estará disponível se você selecionou **Habilitar** os usuários para proteger na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="a590b-283">**Mostrar a representação de domínio dica de segurança**: Essa configuração estará disponível somente se você selecionou Habilitar **domínios** para proteger na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="a590b-284">**Mostrar caracteres incomuns de representação do usuário dica de segurança** Essa configuração só estará disponível se você tiver selecionado **Habilitar** os usuários para proteger ou Habilitar **domínios para proteger** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="a590b-285">**Mostrar (?)** para envios não autenticados para spoof : Essa configuração só estará disponível se você tiver selecionado Habilitar inteligência de **spoof** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="a590b-286">Adiciona um ponto de interrogação à foto do remetente na caixa De no Outlook se a  mensagem não passar verificações SPF ou DKIM e a mensagem não passar DMARC ou autenticação composta [.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="a590b-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="a590b-287">**Mostrar a marca "via":** Essa configuração só estará disponível se você tiver selecionado Habilitar inteligência de **spoof** na página anterior.</span><span class="sxs-lookup"><span data-stu-id="a590b-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="a590b-288">Adiciona uma marca via (chris@contoso.com via fabrikam.com) ao endereço From se for diferente do domínio na assinatura DKIM ou no **endereço MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="a590b-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="a590b-289">O valor padrão está em (selecionado).</span><span class="sxs-lookup"><span data-stu-id="a590b-289">The default value is on (selected).</span></span> <span data-ttu-id="a590b-290">Para desativar, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="a590b-291">Se você não tiver a configuração de marca  Mostrar **"via",** o ponto de interrogação e a marca via serão controlados pela configuração **Mostrar (?)** para envios não autenticados para a configuração de spoof em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a590b-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="a590b-292">Para ativar uma configuração, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="a590b-293">Para desativar, desempure a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a590b-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="a590b-294">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="a590b-295">Na página **Revisão** exibida, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="a590b-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="a590b-296">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="a590b-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a590b-297">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="a590b-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="a590b-298">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="a590b-299">Na mensagem de confirmação exibida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="a590b-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="a590b-300">Usar o portal Microsoft 365 Defender para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="a590b-301">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a590b-302">Na página **Anti-phishing,** as seguintes propriedades são exibidas na lista de políticas anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="a590b-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="a590b-303">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a590b-303">**Name**</span></span>
   - <span data-ttu-id="a590b-304">**Status**</span><span class="sxs-lookup"><span data-stu-id="a590b-304">**Status**</span></span>
   - <span data-ttu-id="a590b-305">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="a590b-305">**Priority**</span></span>
   - <span data-ttu-id="a590b-306">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="a590b-306">**Last modified**</span></span>

3. <span data-ttu-id="a590b-307">Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="a590b-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="a590b-308">Usar o portal Microsoft 365 Defender para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="a590b-309">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a590b-310">Na página **Anti-phishing,** selecione uma política na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="a590b-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a590b-311">No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="a590b-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a590b-312">Para obter mais informações sobre as configurações, consulte a seção Usar o portal Microsoft 365 Defender para criar políticas [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a590b-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="a590b-313">Para a política anti-phishing padrão, a seção Usuários, grupos e **domínios** não está disponível (a política se aplica a todos) e você não pode renomear a política.</span><span class="sxs-lookup"><span data-stu-id="a590b-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="a590b-314">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a590b-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="a590b-315">Habilitar ou desabilitar políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="a590b-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="a590b-316">Não é possível desabilitar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a590b-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="a590b-317">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a590b-318">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="a590b-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a590b-319">Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a590b-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="a590b-320">**Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .</span><span class="sxs-lookup"><span data-stu-id="a590b-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="a590b-321">**Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="a590b-322">Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="a590b-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="a590b-323">Clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="a590b-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="a590b-324">De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="a590b-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="a590b-325">Definir a prioridade de políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="a590b-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="a590b-326">Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="a590b-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a590b-327">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="a590b-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a590b-328">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="a590b-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a590b-329">Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="a590b-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="a590b-330">Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.</span><span class="sxs-lookup"><span data-stu-id="a590b-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="a590b-331">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a590b-331">**Notes**:</span></span>

- <span data-ttu-id="a590b-332">No portal Microsoft 365 Defender, você só pode alterar a prioridade da política anti-phishing após a criação.</span><span class="sxs-lookup"><span data-stu-id="a590b-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="a590b-333">No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="a590b-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="a590b-334">As políticas anti-phishing são processadas na ordem em que são exibidas (a primeira política tem o **valor priority** 0).</span><span class="sxs-lookup"><span data-stu-id="a590b-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a590b-335">A política anti-phishing padrão tem o valor de prioridade **Mais** Baixo e você não pode alterá-la.</span><span class="sxs-lookup"><span data-stu-id="a590b-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="a590b-336">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a590b-337">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.</span><span class="sxs-lookup"><span data-stu-id="a590b-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a590b-338">Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="a590b-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="a590b-339">A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="a590b-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="a590b-340">A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="a590b-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="a590b-341">Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a590b-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="a590b-342">Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.</span><span class="sxs-lookup"><span data-stu-id="a590b-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="a590b-343">Quando terminar, clique em **Fechar** no submenu de detalhes da política.</span><span class="sxs-lookup"><span data-stu-id="a590b-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="a590b-344">Usar o portal Microsoft 365 Defender para remover políticas anti-phishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="a590b-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="a590b-345">Quando você usa o portal Microsoft 365 Defender para remover uma política anti-phishing personalizada, a regra anti-phishing e a política anti-phishing correspondente são excluídas.</span><span class="sxs-lookup"><span data-stu-id="a590b-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="a590b-346">Não é possível remover a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="a590b-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="a590b-347">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a590b-348">Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome da política.</span><span class="sxs-lookup"><span data-stu-id="a590b-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="a590b-349">Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.</span><span class="sxs-lookup"><span data-stu-id="a590b-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="a590b-350">Na caixa de diálogo de confirmação exibida, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a590b-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="a590b-351">Usar Exchange Online PowerShell para configurar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="a590b-352">Conforme descrito anteriormente, uma política anti-spam consiste em uma política anti-phishing e uma regra anti-phish.</span><span class="sxs-lookup"><span data-stu-id="a590b-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="a590b-353">No Exchange Online PowerShell, a diferença entre políticas anti-phishing e regras anti-phishing é aparente.</span><span class="sxs-lookup"><span data-stu-id="a590b-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="a590b-354">Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="a590b-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="a590b-355">No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="a590b-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a590b-356">No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.</span><span class="sxs-lookup"><span data-stu-id="a590b-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="a590b-357">Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="a590b-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="a590b-358">Usar o PowerShell para criar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="a590b-359">Criar uma política anti-phishing no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="a590b-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a590b-360">Crie a política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="a590b-361">Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="a590b-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="a590b-362">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a590b-362">**Notes**:</span></span>

- <span data-ttu-id="a590b-363">Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela.</span><span class="sxs-lookup"><span data-stu-id="a590b-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="a590b-364">Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="a590b-365">Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:</span><span class="sxs-lookup"><span data-stu-id="a590b-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="a590b-366">Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="a590b-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="a590b-367">De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="a590b-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="a590b-368">Uma nova política anti-phishing que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="a590b-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="a590b-369">Etapa 1: Usar o PowerShell para criar uma política anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="a590b-370">Para criar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="a590b-371">Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="a590b-372">A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="a590b-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="a590b-373">A descrição é: Política do departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a590b-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="a590b-374">Habilita a proteção de domínios da organização para todos os domínios aceitos e a proteção de domínios direcionados para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="a590b-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="a590b-375">Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário a ser protegido contra representação.</span><span class="sxs-lookup"><span data-stu-id="a590b-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="a590b-376">Habilita a inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="a590b-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="a590b-377">Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.</span><span class="sxs-lookup"><span data-stu-id="a590b-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="a590b-378">Habilita dicas de segurança.</span><span class="sxs-lookup"><span data-stu-id="a590b-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="a590b-379">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a590b-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="a590b-380">Etapa 2: Usar o PowerShell para criar uma regra anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="a590b-381">Para criar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a590b-382">Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="a590b-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="a590b-383">A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a590b-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="a590b-384">A regra se aplica aos membros do grupo chamado Departamento de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a590b-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="a590b-385">Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="a590b-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="a590b-386">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="a590b-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="a590b-387">Usar o PowerShell para exibir políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="a590b-388">Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a590b-389">Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a590b-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="a590b-390">Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.</span><span class="sxs-lookup"><span data-stu-id="a590b-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="a590b-391">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a590b-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="a590b-392">Usar o PowerShell para exibir regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="a590b-393">Para exibir regras anti-phishing existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a590b-394">Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a590b-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="a590b-395">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a590b-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="a590b-396">Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="a590b-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="a590b-397">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="a590b-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="a590b-398">Usar o PowerShell para modificar políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="a590b-399">Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria a política conforme descrito na Etapa [1: Usar o PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) para criar uma seção de política anti-phishing anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a590b-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="a590b-400">A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a590b-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="a590b-401">Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._</span><span class="sxs-lookup"><span data-stu-id="a590b-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a590b-402">Quando você renomeia uma política anti-phishing no portal Microsoft 365 Defender, você só está renomeando a regra _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="a590b-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="a590b-403">Para modificar uma política anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a590b-404">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a590b-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="a590b-405">Usar o PowerShell para modificar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="a590b-406">A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a590b-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a590b-407">Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="a590b-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="a590b-408">Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a590b-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="a590b-409">As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na Etapa 2: Use o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a590b-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="a590b-410">Para modificar uma regra anti-phishing, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a590b-411">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="a590b-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="a590b-412">Usar o PowerShell para habilitar ou desabilitar regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="a590b-413">Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída).</span><span class="sxs-lookup"><span data-stu-id="a590b-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="a590b-414">Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).</span><span class="sxs-lookup"><span data-stu-id="a590b-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="a590b-415">Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="a590b-416">Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="a590b-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a590b-417">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="a590b-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a590b-418">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="a590b-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="a590b-419">Usar o PowerShell para definir a prioridade das regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="a590b-420">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="a590b-420">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a590b-421">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="a590b-421">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a590b-422">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="a590b-422">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a590b-423">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="a590b-423">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a590b-424">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="a590b-424">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a590b-425">Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a590b-426">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="a590b-426">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a590b-427">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="a590b-427">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a590b-428">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="a590b-428">**Notes**:</span></span>

- <span data-ttu-id="a590b-429">Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="a590b-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="a590b-430">A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.</span><span class="sxs-lookup"><span data-stu-id="a590b-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="a590b-431">Usar o PowerShell para remover políticas anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="a590b-432">Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="a590b-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="a590b-433">Para remover uma política anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a590b-434">Este exemplo remove a política anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="a590b-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a590b-435">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="a590b-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="a590b-436">Usar o PowerShell para remover regras anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a590b-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="a590b-437">Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="a590b-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="a590b-438">Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a590b-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="a590b-439">Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="a590b-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a590b-440">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="a590b-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a590b-441">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="a590b-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="a590b-442">Para verificar se você configurou com êxito políticas anti-phishing no Defender para Office 365, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a590b-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="a590b-443">No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção Políticas \>  \>  \>  \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="a590b-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="a590b-444">Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.**</span><span class="sxs-lookup"><span data-stu-id="a590b-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a590b-445">Para exibir mais detalhes, selecione a política na lista clicando no nome e exibindo os detalhes no sobremenu que aparece.</span><span class="sxs-lookup"><span data-stu-id="a590b-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="a590b-446">No Exchange Online PowerShell, substitua pelo nome da política ou regra e execute o seguinte comando e \<Name\> verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="a590b-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
