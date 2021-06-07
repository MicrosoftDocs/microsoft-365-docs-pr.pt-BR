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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a aplicar configurações de política padrão e estrita nos recursos de proteção do Proteção do Exchange Online (EOP) e do Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca0b8b8dd879f3f662c96f1527bca13efbe5ef6c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771220"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="a18e0-103">Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a18e0-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a18e0-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a18e0-104">**Applies to**</span></span>
- [<span data-ttu-id="a18e0-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a18e0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a18e0-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a18e0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a18e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a18e0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a18e0-108">As políticas de segurança predefinidas fornecem um local centralizado para aplicar todas as políticas recomendadas de spam, malware e phishing aos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="a18e0-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="a18e0-109">As configurações de política não são configuráveis.</span><span class="sxs-lookup"><span data-stu-id="a18e0-109">The policy settings are not configurable.</span></span> <span data-ttu-id="a18e0-110">Em vez disso, eles são definidos por nós e se baseiam em nossas observações e experiências nos datacenters para um equilíbrio entre manter o conteúdo prejudicial longe dos usuários e evitar interrupções desnecessárias.</span><span class="sxs-lookup"><span data-stu-id="a18e0-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="a18e0-111">O restante deste artigo descreve políticas de segurança predefinidas e como configurá-las.</span><span class="sxs-lookup"><span data-stu-id="a18e0-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="a18e0-112">De que políticas de segurança predefinidas são feitas</span><span class="sxs-lookup"><span data-stu-id="a18e0-112">What preset security policies are made of</span></span>

<span data-ttu-id="a18e0-113">As políticas de segurança predefinidas consistem nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="a18e0-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="a18e0-114">Perfis</span><span class="sxs-lookup"><span data-stu-id="a18e0-114">Profiles</span></span>
- <span data-ttu-id="a18e0-115">Políticas</span><span class="sxs-lookup"><span data-stu-id="a18e0-115">Policies</span></span>
- <span data-ttu-id="a18e0-116">Configurações de política</span><span class="sxs-lookup"><span data-stu-id="a18e0-116">Policy settings</span></span>

<span data-ttu-id="a18e0-117">Além disso, a ordem de precedência é importante se várias políticas de segurança predefinidas e outras políticas se aplicarem à mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="a18e0-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="a18e0-118">Perfis em políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="a18e0-118">Profiles in preset security policies</span></span>

<span data-ttu-id="a18e0-119">Um perfil determina o nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="a18e0-119">A profile determines the level of protection.</span></span> <span data-ttu-id="a18e0-120">Os seguintes perfis estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="a18e0-120">The following profiles are available:</span></span>

- <span data-ttu-id="a18e0-121">**Proteção padrão**: um perfil de proteção de linha de base adequado para a maioria dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a18e0-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="a18e0-122">**Proteção estrita**: um perfil de proteção mais agressivo para usuários selecionados (destinos de alto valor ou usuários prioritários).</span><span class="sxs-lookup"><span data-stu-id="a18e0-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="a18e0-123">Você usa regras com condições e exceções que determinam a quem os perfis são ou não aplicados.</span><span class="sxs-lookup"><span data-stu-id="a18e0-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="a18e0-124">As condições e exceções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a18e0-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="a18e0-125">**Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="a18e0-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="a18e0-126">**Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.</span><span class="sxs-lookup"><span data-stu-id="a18e0-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="a18e0-127">**Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.</span><span class="sxs-lookup"><span data-stu-id="a18e0-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="a18e0-128">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="a18e0-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a18e0-129">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a18e0-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a18e0-130">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a18e0-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="a18e0-131">Políticas em políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="a18e0-131">Policies in preset security policies</span></span>

<span data-ttu-id="a18e0-132">As políticas de segurança predefinidas usam as políticas correspondentes dos vários recursos de proteção no EOP e no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a18e0-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a18e0-133">Essas políticas são _criadas depois que_ você atribui a **proteção padrão** ou políticas **de** segurança predefinidas de proteção estrita aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a18e0-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="a18e0-134">Não é possível modificar essas políticas.</span><span class="sxs-lookup"><span data-stu-id="a18e0-134">You can't modify these policies.</span></span>

- <span data-ttu-id="a18e0-135">**Proteção do Exchange Online (EOP)**: isso inclui organizações Microsoft 365 com caixas de correio Exchange Online e organizações EOP autônomas sem Exchange Online caixas de correio:</span><span class="sxs-lookup"><span data-stu-id="a18e0-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="a18e0-136">[Políticas anti-spam denominadas](configure-your-spam-filter-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**</span><span class="sxs-lookup"><span data-stu-id="a18e0-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="a18e0-137">[Políticas anti-malware denominadas](configure-anti-malware-policies.md) **Política de Segurança Predefinida Padrão** e Política de Segurança **Predefinida Estrita.**</span><span class="sxs-lookup"><span data-stu-id="a18e0-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="a18e0-138">[Políticas anti-phishing do EOP denominadas](set-up-anti-phishing-policies.md#spoof-settings) Política de **Segurança Predefinida Padrão** e **Política** de Segurança Predefinida Estrita (configurações de spoof).</span><span class="sxs-lookup"><span data-stu-id="a18e0-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="a18e0-139">**Políticas do Microsoft Defender para Office 365**: isso inclui organizações com o Microsoft 365 E5 ou o Defender para Office 365 assinaturas de complemento:</span><span class="sxs-lookup"><span data-stu-id="a18e0-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="a18e0-140">Políticas anti-phishing no Microsoft Defender para Office 365 chamada de **Política** de Segurança Predefinida Padrão e **Política** de Segurança Predefinida Estrita, que incluem:</span><span class="sxs-lookup"><span data-stu-id="a18e0-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="a18e0-141">As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.</span><span class="sxs-lookup"><span data-stu-id="a18e0-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="a18e0-142">Configurações de representação</span><span class="sxs-lookup"><span data-stu-id="a18e0-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="a18e0-143">Limites avançados de phishing</span><span class="sxs-lookup"><span data-stu-id="a18e0-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="a18e0-144">[Cofre políticas de links denominadas](set-up-safe-links-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**</span><span class="sxs-lookup"><span data-stu-id="a18e0-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="a18e0-145">[Cofre de anexos denominadas](set-up-safe-attachments-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**</span><span class="sxs-lookup"><span data-stu-id="a18e0-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="a18e0-146">Observe que você pode aplicar proteções EOP a usuários diferentes do Microsoft Defender para Office 365 proteção.</span><span class="sxs-lookup"><span data-stu-id="a18e0-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="a18e0-147">Configurações de política em políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="a18e0-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="a18e0-148">Não é possível modificar as configurações de política nos perfis de proteção.</span><span class="sxs-lookup"><span data-stu-id="a18e0-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="a18e0-149">Os **valores de configuração** de **política** Padrão e Estrita são descritos em [Configurações recomendadas para EOP](recommended-settings-for-eop-and-office365.md)e Microsoft Defender para Office 365 segurança .</span><span class="sxs-lookup"><span data-stu-id="a18e0-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="a18e0-150">Ordem de precedência para políticas de segurança predefinidas e outras políticas</span><span class="sxs-lookup"><span data-stu-id="a18e0-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="a18e0-151">Quando várias políticas são aplicadas a um usuário, a ordem a seguir é aplicada da prioridade mais alta à prioridade mais baixa:</span><span class="sxs-lookup"><span data-stu-id="a18e0-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="a18e0-152">**Política de segurança predefinida** de proteção estrita</span><span class="sxs-lookup"><span data-stu-id="a18e0-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="a18e0-153">**Política de segurança predefinida** de proteção padrão</span><span class="sxs-lookup"><span data-stu-id="a18e0-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="a18e0-154">Políticas de segurança personalizadas</span><span class="sxs-lookup"><span data-stu-id="a18e0-154">Custom security policies</span></span>
4. <span data-ttu-id="a18e0-155">Políticas de segurança padrão</span><span class="sxs-lookup"><span data-stu-id="a18e0-155">Default security policies</span></span>

<span data-ttu-id="a18e0-156">Em outras palavras, as  configurações da política de  proteção estrita substituem as configurações da política de proteção padrão, que substitui as configurações de uma política personalizada, que substitui as configurações da política padrão.</span><span class="sxs-lookup"><span data-stu-id="a18e0-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="a18e0-157">Atribuir políticas de segurança predefinidas aos usuários</span><span class="sxs-lookup"><span data-stu-id="a18e0-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a18e0-158">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="a18e0-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a18e0-159">Você abre o Microsoft 365 de segurança em <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="a18e0-159">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="a18e0-160">Para ir diretamente para a página **Políticas de segurança** predefinidas, use <https://security.microsoft.com/presetSecurityPolicies> .</span><span class="sxs-lookup"><span data-stu-id="a18e0-160">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="a18e0-161">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a18e0-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a18e0-162">Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="a18e0-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a18e0-163">Para configurar políticas de segurança predefinidas, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="a18e0-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a18e0-164">Para acesso somente leitura a políticas de segurança predefinidas, você precisa ser membro do grupo de função **Leitor Global.**</span><span class="sxs-lookup"><span data-stu-id="a18e0-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="a18e0-165">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a18e0-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a18e0-166">**Observação**: a adição de usuários à função Azure Active Directory correspondente no centro de  administração Microsoft 365 oferece aos usuários as permissões e permissões necessárias para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a18e0-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a18e0-167">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a18e0-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="a18e0-168">Usar o centro de segurança para atribuir políticas de segurança predefinidas aos usuários</span><span class="sxs-lookup"><span data-stu-id="a18e0-168">Use the security center to assign preset security policies to users</span></span>

1. <span data-ttu-id="a18e0-169">No centro de segurança, acesse **Email & de** colaboração & Regras Políticas de Segurança \>  \>  \> **Predefinidas.**</span><span class="sxs-lookup"><span data-stu-id="a18e0-169">In the security center, go to **Email & collaboration** \> **Policies & Rules** \> **Threat Policies** \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="a18e0-170">Em **Proteção padrão ou** proteção **estrita,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a18e0-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="a18e0-171">O **assistente Aplicar Proteção Padrão** ou Aplicar Proteção **Estrita** é iniciado.</span><span class="sxs-lookup"><span data-stu-id="a18e0-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="a18e0-172">Nas **proteções do EOP aplicadas à** página, identifique os destinatários internos aos quais as proteções [do EOP](#policies-in-preset-security-policies) se aplicam (condições de destinatário):</span><span class="sxs-lookup"><span data-stu-id="a18e0-172">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="a18e0-173">**Usuários**</span><span class="sxs-lookup"><span data-stu-id="a18e0-173">**Users**</span></span>
   - <span data-ttu-id="a18e0-174">**Grupos**</span><span class="sxs-lookup"><span data-stu-id="a18e0-174">**Groups**</span></span>
   - <span data-ttu-id="a18e0-175">**Domínios**</span><span class="sxs-lookup"><span data-stu-id="a18e0-175">**Domains**</span></span>

   <span data-ttu-id="a18e0-176">Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados.</span><span class="sxs-lookup"><span data-stu-id="a18e0-176">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a18e0-177">Repita esse processo quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="a18e0-177">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a18e0-178">Para remover uma entrada existente, clique em Remover</span><span class="sxs-lookup"><span data-stu-id="a18e0-178">To remove an existing value, click remove</span></span> ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a18e0-180">ao lado do valor.</span><span class="sxs-lookup"><span data-stu-id="a18e0-180">next to the value.</span></span>

   <span data-ttu-id="a18e0-181">Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados.</span><span class="sxs-lookup"><span data-stu-id="a18e0-181">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a18e0-182">Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a18e0-182">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="a18e0-183">**Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções.</span><span class="sxs-lookup"><span data-stu-id="a18e0-183">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a18e0-184">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="a18e0-184">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a18e0-185">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a18e0-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a18e0-186">No Microsoft Defender para Office 365, você é levado para **o Defender** para Office 365 proteções se aplicam à página para identificar os destinatários internos aos quais o Microsoft Defender para Office 365 [proteções](#policies-in-preset-security-policies) se aplicam (condições de destinatário).</span><span class="sxs-lookup"><span data-stu-id="a18e0-186">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="a18e0-187">As configurações e o comportamento são exatamente como as proteções **do EOP se aplicam à** página.</span><span class="sxs-lookup"><span data-stu-id="a18e0-187">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="a18e0-188">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a18e0-188">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a18e0-189">Na página **Revisar e confirmar suas alterações,** verifique suas seleções e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a18e0-189">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="a18e0-190">Usar o centro de segurança para modificar as atribuições de políticas de segurança predefinidas</span><span class="sxs-lookup"><span data-stu-id="a18e0-190">Use the security center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="a18e0-191">As etapas para modificar  a atribuição da política de segurança proteção padrão ou proteção estrita são as mesmas de quando você atribuiu inicialmente as políticas de segurança predefinidas [aos usuários](#use-the-security-center-to-assign-preset-security-policies-to-users). </span><span class="sxs-lookup"><span data-stu-id="a18e0-191">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="a18e0-192">Para desabilitar as  **políticas** de segurança de proteção padrão ou de proteção estrita enquanto ainda preserva as condições e exceções existentes, deslize a alternância para **Desabilitado** ![ Desativar a Alternância ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="a18e0-192">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="a18e0-193">Para habilitar as políticas, deslize a alternância **para Habilitado** ![ para ](../../media/scc-toggle-on.png) Ativar.</span><span class="sxs-lookup"><span data-stu-id="a18e0-193">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a18e0-194">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="a18e0-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="a18e0-195">Para verificar se você atribuiu  com êxito  a política de segurança proteção padrão ou proteção estrita a um usuário, use uma configuração de proteção em que o valor padrão é diferente da configuração **de** proteção Padrão, que é diferente da configuração **de** proteção estrita.</span><span class="sxs-lookup"><span data-stu-id="a18e0-195">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="a18e0-196">Por exemplo, para emails detectados como spam (não spam de alta confiança) verifique  se a mensagem é  entregue à pasta Lixo Eletrônico para usuários de proteção padrão e colocada em quarentena para usuários de proteção estrita.</span><span class="sxs-lookup"><span data-stu-id="a18e0-196">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="a18e0-197">Ou, para email em [massa,](bulk-complaint-level-values.md)verifique se o valor BCL 6  ou superior entrega a mensagem para a pasta Lixo  Eletrônico para usuários de proteção padrão, e o valor BCL 4 ou superior coloca em quarentena a mensagem para usuários de proteção estrita.</span><span class="sxs-lookup"><span data-stu-id="a18e0-197">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
