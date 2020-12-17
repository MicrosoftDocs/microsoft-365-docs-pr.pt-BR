---
title: Política de nomenclatura de grupos do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Saiba como criar uma política de nomenclatura para os grupos do Microsoft 365.
ms.openlocfilehash: 9bc0a4c7e1ae6ad532c97b442a2bc50880a942fc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698670"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="5a6ad-103">Política de nomenclatura de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a6ad-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="5a6ad-104">Você pode usar uma política de nomeação de grupo para impor uma estratégia de nomenclatura consistente para grupos criados por usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="5a6ad-105">Uma política de nomenclatura pode ajudar você e seus usuários a identificar a função do grupo, da associação, da região geográfica ou quem criou o grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="5a6ad-106">A política de nomenclatura também pode ajudar a categorizar grupos no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="5a6ad-107">Você pode usar a política para bloquear a utilização de palavras específicas em nomes de grupo e aliases.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="5a6ad-108">A política de nomenclatura é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span><span class="sxs-lookup"><span data-stu-id="5a6ad-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="5a6ad-109">Ela é aplicada ao nome do grupo e ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="5a6ad-110">Ela é aplicada quando um usuário cria um grupo e quando o nome ou o alias do grupo é editado para um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="5a6ad-111">Uma política de nomenclatura de grupo do Microsoft 365 só se aplica aos grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="5a6ad-112">Ele não se aplica a grupos de distribuição criados no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="5a6ad-113">Para criar uma política de nomenclatura para grupos de distribuição, consulte [criar uma política de nomenclatura de grupo de distribuição](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="5a6ad-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="5a6ad-114">A política de nomeação de grupo consiste nos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="5a6ad-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="5a6ad-115">**Política de nomenclatura de sufixo de prefixo**: você pode usar prefixos ou sufixos para definir a Convenção de nomenclatura de grupos (por exemplo: " \_ minha engenharia de grupo dos EUA \_ ").</span><span class="sxs-lookup"><span data-stu-id="5a6ad-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="5a6ad-116">Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [departamento] que serão substituídos com base no usuário que está criando o grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="5a6ad-117">**Palavras bloqueadas personalizadas**: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueados em grupos criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="5a6ad-118">(Por exemplo: "CEO, folha de pagamento, RH").</span><span class="sxs-lookup"><span data-stu-id="5a6ad-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5a6ad-119">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="5a6ad-119">Licensing requirements</span></span>

<span data-ttu-id="5a6ad-120">O uso da política de nomenclatura do Azure AD para grupos do Microsoft 365 requer que você tenha, mas não necessariamente, atribua uma licença do Azure Active Directory Premium P1 ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="5a6ad-121">Isso também é necessário para o administrador que cria a política de nomenclatura de grupos.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="5a6ad-122">Política de nomenclatura Prefix-Suffix</span><span class="sxs-lookup"><span data-stu-id="5a6ad-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="5a6ad-123">Os prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="5a6ad-124">Cadeias de caracteres fixas</span><span class="sxs-lookup"><span data-stu-id="5a6ad-124">Fixed strings</span></span>

<span data-ttu-id="5a6ad-125">Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à navegação à esquerda das cargas de trabalho do grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="5a6ad-126">Alguns dos sufixos de prefixos comuns são palavras-chave como "GRP \_ name", " \# name", " \_ name"</span><span class="sxs-lookup"><span data-stu-id="5a6ad-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="5a6ad-127">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a6ad-127">Attributes</span></span>

<span data-ttu-id="5a6ad-128">Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [departamento] e onde ele foi criado de como [país].</span><span class="sxs-lookup"><span data-stu-id="5a6ad-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="5a6ad-129">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="5a6ad-129">Examples:</span></span>

- <span data-ttu-id="5a6ad-130">Policy = "GRP [Nome_do_grupo] [departamento]"</span><span class="sxs-lookup"><span data-stu-id="5a6ad-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="5a6ad-131">Departamento do usuário = engenharia</span><span class="sxs-lookup"><span data-stu-id="5a6ad-131">User's department = Engineering</span></span>
- <span data-ttu-id="5a6ad-132">Nome do grupo criado = "engenharia de grupo meu GRP"</span><span class="sxs-lookup"><span data-stu-id="5a6ad-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="5a6ad-133">Os atributos do Azure Active Directory (Azure AD) com suporte são [departamento], [empresa], [Office], [StateOrProvince], [CountryOrRegion] e [título].</span><span class="sxs-lookup"><span data-stu-id="5a6ad-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="5a6ad-134">Atributos de usuário não suportados são considerados cadeias de caracteres fixas, por exemplo, [postalCode].</span><span class="sxs-lookup"><span data-stu-id="5a6ad-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="5a6ad-135">Não há suporte para atributos de extensão e atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="5a6ad-136">É recomendável que você use atributos com valores preenchidos para todos os usuários em sua organização e não use atributos com valores mais longos.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="5a6ad-137">Aspectos a serem verificados</span><span class="sxs-lookup"><span data-stu-id="5a6ad-137">Things to look out for</span></span>

- <span data-ttu-id="5a6ad-138">Durante a criação da política, o comprimento total de cadeias de caracteres e sufixos é restrito a 53 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="5a6ad-139">Os prefixos e sufixos podem conter caracteres especiais compatíveis com o nome do grupo e o alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="5a6ad-140">Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias do grupo, eles são aplicados apenas ao nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="5a6ad-141">Portanto, nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos que foram aplicados ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5a6ad-142">Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="5a6ad-143">Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="5a6ad-144">Se você estiver usando os grupos conectados do Yammer Office 365, evite usar os seguintes caracteres em sua política de nomenclatura: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="5a6ad-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="5a6ad-145">Se esses caracteres estiverem na política de nomenclatura, os usuários normais do Yammer não poderão criar grupos.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="5a6ad-146">Usar cadeias de caracteres curtas como sufixo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="5a6ad-147">Use atributos com valores.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-147">Use attributes with values.</span></span>
> - <span data-ttu-id="5a6ad-148">Não seja muito criativo, o comprimento total do nome tem um máximo de 264 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="5a6ad-149">Carregue suas palavras bloqueadas específicas da organização para restringir o uso.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="5a6ad-150">Palavras bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="5a6ad-150">Custom blocked words</span></span>

<span data-ttu-id="5a6ad-151">Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em nomes de grupo e aliases.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="5a6ad-152">Nenhuma pesquisa de subcadeias de caracteres é executada; especificamente, uma correspondência exata entre o nome digitado pelo usuário e as palavras bloqueadas personalizadas é necessária para acionar uma falha.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="5a6ad-153">**Aspectos a serem verificados**:</span><span class="sxs-lookup"><span data-stu-id="5a6ad-153">**Things to look out for**:</span></span>

- <span data-ttu-id="5a6ad-154">As palavras bloqueadas não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="5a6ad-155">Quando um usuário insere uma palavra bloqueada, o cliente do grupo mostrará uma mensagem de erro com a palavra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="5a6ad-156">Não há restrições de caracteres nas palavras bloqueadas usadas.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="5a6ad-157">Há um limite de 5000 palavras que podem ser definidas como palavras bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="5a6ad-158">Substituição de administrador</span><span class="sxs-lookup"><span data-stu-id="5a6ad-158">Admin override</span></span>

<span data-ttu-id="5a6ad-159">Alguns administradores são isentos dessas políticas, em todas as cargas de trabalho de grupo e pontos de extremidade, para que eles possam criar grupos com essas palavras bloqueadas e com as convenções de nomenclatura desejadas.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="5a6ad-160">Veja a seguir a lista de funções de administrador isentas da política de nomeação de grupo.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="5a6ad-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5a6ad-161">Global admin</span></span>

- <span data-ttu-id="5a6ad-162">Suporte da camada 1 do parceiro</span><span class="sxs-lookup"><span data-stu-id="5a6ad-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="5a6ad-163">Suporte da camada 2 do parceiro</span><span class="sxs-lookup"><span data-stu-id="5a6ad-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="5a6ad-164">Administrador de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="5a6ad-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="5a6ad-165">Como configurar a política de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5a6ad-165">How to set up the naming policy</span></span>

<span data-ttu-id="5a6ad-166">Para configurar uma política de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="5a6ad-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="5a6ad-167">No [Azure Active Directory](https://aad.portal.azure.com), em **gerenciar**, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="5a6ad-168">Em **configurações**, clique em **política de nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="5a6ad-169">Escolha a guia **política de nomeação de grupo** .</span><span class="sxs-lookup"><span data-stu-id="5a6ad-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="5a6ad-170">Em **política atual**, escolha se você deseja exigir um prefixo ou sufixo, ou ambos, e marque as caixas de seleção apropriadas.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="5a6ad-171">Escolha entre **atributo** e **cadeia de caracteres** para cada linha e, em seguida, especifique o atributo ou a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="5a6ad-172">Após adicionar os prefixos e sufixos necessários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="5a6ad-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Captura de tela das configurações de política de nomenclatura de grupos no Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="5a6ad-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5a6ad-174">Related topics</span></span>

[<span data-ttu-id="5a6ad-175">Passo a passo de planejamento de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="5a6ad-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="5a6ad-176">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="5a6ad-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="5a6ad-177">Cmdlets do Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="5a6ad-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
