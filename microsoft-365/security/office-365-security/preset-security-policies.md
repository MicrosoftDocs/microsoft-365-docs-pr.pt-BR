---
title: Predefinir políticas de segurança
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
description: Os administradores podem aprender a aplicar as configurações de política padrão e estrita nos recursos de proteção do Exchange Online Protection (EOP) e no Office 365 Advanced Threat Protection (ATP)
ms.openlocfilehash: a624d48944965c217fb8547e4f09da0ec388e615
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830532"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="f8570-103">Políticas de segurança predefinidas no EOP e no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f8570-103">Preset security policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f8570-104">As políticas de segurança predefinidas fornecem um local centralizado para aplicar todas as políticas recomendadas de spam, malware e phishing aos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="f8570-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="f8570-105">As configurações de política não são configuráveis.</span><span class="sxs-lookup"><span data-stu-id="f8570-105">The policy settings are not configurable.</span></span> <span data-ttu-id="f8570-106">Em vez disso, eles são definidos por nós e são baseados em observações e experiências nos data centers para obter um equilíbrio entre manter o conteúdo prejudicial longe dos usuários sem interromper o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f8570-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="f8570-107">O restante deste tópico descreve as políticas de segurança predefinidas e como configurá-las.</span><span class="sxs-lookup"><span data-stu-id="f8570-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="f8570-108">Quais políticas de segurança predefinidas são feitas</span><span class="sxs-lookup"><span data-stu-id="f8570-108">What preset security policies are made of</span></span>

<span data-ttu-id="f8570-109">As políticas de segurança predefinidas consistem nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="f8570-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="f8570-110">Perfis</span><span class="sxs-lookup"><span data-stu-id="f8570-110">Profiles</span></span>
- <span data-ttu-id="f8570-111">Políticas</span><span class="sxs-lookup"><span data-stu-id="f8570-111">Policies</span></span>
- <span data-ttu-id="f8570-112">Configurações de política</span><span class="sxs-lookup"><span data-stu-id="f8570-112">Policy settings</span></span>

<span data-ttu-id="f8570-113">Além disso, a ordem de precedência é importante se várias diretivas de segurança predefinidas e outras políticas se aplicarem à mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="f8570-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="f8570-114">Perfis em políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="f8570-114">Profiles in preset security policies</span></span>

<span data-ttu-id="f8570-115">Um perfil determina o nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="f8570-115">A profile determines the level of protection.</span></span> <span data-ttu-id="f8570-116">Os seguintes perfis estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f8570-116">The following profiles are available:</span></span>

- <span data-ttu-id="f8570-117">**Proteção padrão** : um perfil de proteção de linha de base adequado para a maioria dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f8570-117">**Standard protection** : A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="f8570-118">**Proteção estrita** : um perfil de proteção mais agressivo para usuários selecionados (metas de alto valor ou usuários com prioridade).</span><span class="sxs-lookup"><span data-stu-id="f8570-118">**Strict protection** : A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="f8570-119">Você usa regras com condições e exceções que determinam a quem os perfis estão ou não são aplicados.</span><span class="sxs-lookup"><span data-stu-id="f8570-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="f8570-120">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="f8570-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f8570-121">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="f8570-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="f8570-122">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="f8570-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

<span data-ttu-id="f8570-123">As condições e exceções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="f8570-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="f8570-124">**Os destinatários são** : caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8570-124">**The recipients are** : Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="f8570-125">**Os destinatários são membros de** : grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8570-125">**The recipients are members of** : Groups in your organization.</span></span>
- <span data-ttu-id="f8570-126">**Os domínios de destinatário são** : domínios aceitos que são configurados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8570-126">**The recipient domains are** : Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="f8570-127">Políticas em políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="f8570-127">Policies in preset security policies</span></span>

<span data-ttu-id="f8570-128">As políticas de segurança predefinidas usam as políticas correspondentes dos vários recursos de proteção no EOP e no Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="f8570-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="f8570-129">Essas políticas são criadas _depois_ que você atribui as políticas de segurança predefinidas de **proteção padrão** ou **proteção estrita** aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f8570-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="f8570-130">Você não pode modificar essas políticas.</span><span class="sxs-lookup"><span data-stu-id="f8570-130">You can't modify these policies.</span></span>

- <span data-ttu-id="f8570-131">**Políticas de proteção do Exchange Online (EOP)** : isso inclui as organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f8570-131">**Exchange Online Protection (EOP) policies** : This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="f8570-132">[Políticas antispam](configure-your-spam-filter-policies.md) chamadas política de **segurança predefinida padrão** e **política de segurança predefinida restrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>
  - <span data-ttu-id="f8570-133">[Diretivas Antimalware](configure-anti-malware-policies.md) chamadas **política de segurança predefinida padrão** e **política de segurança predefinida restrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>
  - <span data-ttu-id="f8570-134">[EOP políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings) chamadas política de **segurança** predefinida padrão e **política de segurança predefinida restrita** (configurações de spoof).</span><span class="sxs-lookup"><span data-stu-id="f8570-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="f8570-135">**Políticas de proteção avançada contra ameaças (ATP) do office 365** : inclui organizações com as assinaturas do Microsoft 365 E5 ou do Office 365 ATP Add-on:</span><span class="sxs-lookup"><span data-stu-id="f8570-135">**Office 365 Advanced Threat Protection (ATP) policies** : This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="f8570-136">Diretivas antiphishing da ATP chamadas de **política de segurança predefinida padrão** e **política de segurança predefinida estrita** , que incluem:</span><span class="sxs-lookup"><span data-stu-id="f8570-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy** , which include:</span></span>

    - <span data-ttu-id="f8570-137">As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.</span><span class="sxs-lookup"><span data-stu-id="f8570-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="f8570-138">Configurações de representação</span><span class="sxs-lookup"><span data-stu-id="f8570-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="f8570-139">Limites avançados de phishing</span><span class="sxs-lookup"><span data-stu-id="f8570-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="f8570-140">[Políticas de links seguros](set-up-atp-safe-links-policies.md) chamada **política de segurança predefinida padrão** e **política de segurança predefinida estrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-140">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>

  - <span data-ttu-id="f8570-141">[Políticas de anexos seguros](set-up-atp-safe-attachments-policies.md) chamadas **política de segurança predefinida padrão** e **política de segurança predefinida estrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-141">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy** .</span></span>

<span data-ttu-id="f8570-142">Observe que você pode aplicar proteções do EOP a diferentes usuários do que as proteções ATP.</span><span class="sxs-lookup"><span data-stu-id="f8570-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="f8570-143">Configurações de política em políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="f8570-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="f8570-144">Você não pode modificar as configurações de política nos perfis de proteção.</span><span class="sxs-lookup"><span data-stu-id="f8570-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="f8570-145">Os valores de configuração de política **padrão** e **estrito** são descritos em [configurações recomendadas para a segurança do EOP e do Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f8570-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="f8570-146">Ordem de precedência para políticas de segurança predefinidas e outras políticas</span><span class="sxs-lookup"><span data-stu-id="f8570-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="f8570-147">Quando várias políticas são aplicadas a um usuário, a ordem a seguir é aplicada da prioridade mais alta à prioridade mais baixa:</span><span class="sxs-lookup"><span data-stu-id="f8570-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="f8570-148">Política de segurança predefinida de **proteção estrita**</span><span class="sxs-lookup"><span data-stu-id="f8570-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="f8570-149">Política de segurança predefinida de **proteção padrão**</span><span class="sxs-lookup"><span data-stu-id="f8570-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="f8570-150">Políticas de segurança personalizadas</span><span class="sxs-lookup"><span data-stu-id="f8570-150">Custom security policies</span></span>
4. <span data-ttu-id="f8570-151">Políticas de segurança padrão</span><span class="sxs-lookup"><span data-stu-id="f8570-151">Default security policies</span></span>

<span data-ttu-id="f8570-152">Em outras palavras, as configurações da política de **proteção estrita** substituem as configurações da política de **proteção padrão** , que substitui as configurações de uma política personalizada, que substitui as configurações da política padrão.</span><span class="sxs-lookup"><span data-stu-id="f8570-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="f8570-153">Atribuir políticas de segurança predefinidas aos usuários</span><span class="sxs-lookup"><span data-stu-id="f8570-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8570-154">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f8570-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f8570-155">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f8570-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f8570-156">Para ir diretamente para a página **políticas de segurança predefinidas** , use <https://protection.office.com/presetSecurityPolicies> .</span><span class="sxs-lookup"><span data-stu-id="f8570-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="f8570-157">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f8570-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f8570-158">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="f8570-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f8570-159">Para configurar políticas de segurança predefinidas, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="f8570-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f8570-160">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f8570-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f8570-161">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f8570-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f8570-162">Para acesso somente leitura às políticas de segurança predefinidas, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="f8570-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f8570-163">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f8570-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f8570-164">**Leitor global** no [centro de conformidade e segurança &](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f8570-164">**Global Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f8570-165">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f8570-165">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="f8570-166">Usar o centro de conformidade de & de segurança para atribuir políticas de segurança predefinidas aos usuários</span><span class="sxs-lookup"><span data-stu-id="f8570-166">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="f8570-167">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **políticas de segurança predefinidas** da política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="f8570-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies** .</span></span>

2. <span data-ttu-id="f8570-168">Em **proteção padrão** ou **proteção estrita** , clique em **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f8570-168">Under **Standard protection** or **Strict protection** , click **Edit** .</span></span>

3. <span data-ttu-id="f8570-169">O assistente **aplicar proteção padrão** ou **aplicar proteção estrita** é iniciado.</span><span class="sxs-lookup"><span data-stu-id="f8570-169">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="f8570-170">Nas **proteções do EOP aplicam** -se à etapa, identifique os destinatários internos aos quais as [proteções do EOP](#policies-in-preset-security-policies) se aplicam:</span><span class="sxs-lookup"><span data-stu-id="f8570-170">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="f8570-171">Clique em **Adicionar uma condição** .</span><span class="sxs-lookup"><span data-stu-id="f8570-171">Click **Add a condition** .</span></span> <span data-ttu-id="f8570-172">Na lista suspensa exibida, selecione uma condição em **aplicado se** :</span><span class="sxs-lookup"><span data-stu-id="f8570-172">In the dropdown that appears, select a condition under **Applied if** :</span></span>

      - <span data-ttu-id="f8570-173">**Os destinatários são**</span><span class="sxs-lookup"><span data-stu-id="f8570-173">**The recipients are**</span></span>
      - <span data-ttu-id="f8570-174">**Os destinatários são membros de**</span><span class="sxs-lookup"><span data-stu-id="f8570-174">**The recipients are members of**</span></span>
      - <span data-ttu-id="f8570-175">**Os domínios do destinatário são**</span><span class="sxs-lookup"><span data-stu-id="f8570-175">**The recipient domains are**</span></span>

      <span data-ttu-id="f8570-176">Você só pode usar uma condição uma vez, mas pode especificar vários valores para a condição.</span><span class="sxs-lookup"><span data-stu-id="f8570-176">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="f8570-177">Vários valores do mesmo uso ou lógica de condição (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="f8570-177">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span>

   2. <span data-ttu-id="f8570-178">A condição selecionada aparece em uma seção sombreada.</span><span class="sxs-lookup"><span data-stu-id="f8570-178">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="f8570-179">Nessa seção, clique na caixa **qualquer uma** dessas caixas.</span><span class="sxs-lookup"><span data-stu-id="f8570-179">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="f8570-180">Se você esperar um instante, uma lista será exibida para que você possa selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="f8570-180">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="f8570-181">Ou você pode começar a digitar um valor para filtrar a lista e selecionar um valor.</span><span class="sxs-lookup"><span data-stu-id="f8570-181">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="f8570-182">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="f8570-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="f8570-183">Para remover um valor individual, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="f8570-183">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="f8570-184">Para remover a condição inteira, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="f8570-184">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="f8570-185">Para adicionar outra condição, clique em **Adicionar uma condição** e selecione entre as condições restantes.</span><span class="sxs-lookup"><span data-stu-id="f8570-185">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="f8570-186">Condições diferentes de uso e lógica (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="f8570-186">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

      <span data-ttu-id="f8570-187">Repita a etapa anterior para adicionar valores à condição e repita essa etapa quantas vezes forem necessárias ou até que você fique sem condições.</span><span class="sxs-lookup"><span data-stu-id="f8570-187">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="f8570-188">Para adicionar uma exceção, clique em **Adicionar uma condição** .</span><span class="sxs-lookup"><span data-stu-id="f8570-188">To add an exception, click **Add a condition** .</span></span> <span data-ttu-id="f8570-189">Na lista suspensa exibida, selecione uma condição em **exceto quando** .</span><span class="sxs-lookup"><span data-stu-id="f8570-189">In the dropdown that appears, select a condition under **Except when** .</span></span> <span data-ttu-id="f8570-190">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="f8570-190">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f8570-191">Quando terminar, clique em **Avançar** .</span><span class="sxs-lookup"><span data-stu-id="f8570-191">When you're finished, click **Next** .</span></span>

4. <span data-ttu-id="f8570-192">Se sua organização tiver o Office 365 ATP, você será levado para as **proteções de ATP aplicam** -se à etapa para identificar os destinatários internos aos quais as [proteções do Office 365 ATP](#policies-in-preset-security-policies) se aplicam.</span><span class="sxs-lookup"><span data-stu-id="f8570-192">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="f8570-193">As configurações e o comportamento são exatamente como as **proteções do EOP se aplicam à** etapa.</span><span class="sxs-lookup"><span data-stu-id="f8570-193">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="f8570-194">Quando terminar, clique em **Avançar** .</span><span class="sxs-lookup"><span data-stu-id="f8570-194">When you're finished, click **Next** .</span></span>

5. <span data-ttu-id="f8570-195">Na etapa **confirmar** , verifique suas seleções e clique em **confirmar** .</span><span class="sxs-lookup"><span data-stu-id="f8570-195">On the **Confirm** step, verify your selections, and then click **Confirm** .</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="f8570-196">Usar o centro de conformidade de & de segurança para modificar as atribuições de políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="f8570-196">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="f8570-197">As etapas para modificar a atribuição da política de segurança de **proteção padrão** ou **proteção estrita** são as mesmas de quando você [atribuiu inicialmente as políticas de segurança predefinidas aos usuários](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span><span class="sxs-lookup"><span data-stu-id="f8570-197">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="f8570-198">Para desabilitar a **proteção padrão** ou políticas de segurança de **proteção estrita** e, ao mesmo tempo, preservar as condições e exceções existentes, deslize a opção para **desabilitado** .</span><span class="sxs-lookup"><span data-stu-id="f8570-198">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** .</span></span> <span data-ttu-id="f8570-199">Para habilitar as políticas, deslize a opção para **habilitado** .</span><span class="sxs-lookup"><span data-stu-id="f8570-199">To enable the policies, slide the toggle to **Enabled** .</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f8570-200">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="f8570-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="f8570-201">Para verificar se você atribuiu com êxito a política de segurança de proteção **padrão** ou **proteção estrita** a um usuário, use uma configuração de proteção onde o valor padrão é diferente da configuração de **proteção padrão** , que é diferente da configuração de **proteção estrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-201">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="f8570-202">Por exemplo, para email que é detectado como spam (não spam de alta confiança) Verifique se a mensagem foi entregue à pasta lixo eletrônico para usuários de **proteção padrão** e em quarentena para usuários de **proteção estrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-202">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="f8570-203">Ou, para [emails em massa](bulk-complaint-level-values.md), verifique se o valor de BCL 6 ou superior entrega a mensagem para a pasta lixo eletrônico para usuários de **proteção padrão** e o valor de BCL 4 ou superior coloca em quarentena a mensagem para usuários de **proteção estrita** .</span><span class="sxs-lookup"><span data-stu-id="f8570-203">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
