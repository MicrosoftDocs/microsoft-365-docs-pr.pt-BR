---
title: Política de nomeação de grupos
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Saiba como criar uma política de nomenclatura para os grupos do Microsoft 365.
ms.openlocfilehash: ae216d0d8f3319e9633d300d785b4a8c31702798
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702543"
---
# <a name="groups-naming-policy"></a><span data-ttu-id="ec8de-103">Política de nomeação de grupos</span><span class="sxs-lookup"><span data-stu-id="ec8de-103">Groups naming policy</span></span>

<span data-ttu-id="ec8de-104">Você usa uma política de nomeação de grupo para impor uma estratégia de nomenclatura consistente para grupos criados por usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ec8de-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="ec8de-105">Uma política de nomenclatura pode ajudar você e seus usuários a identificar a função do grupo, da associação, da região geográfica ou quem criou o grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="ec8de-106">A política de nomenclatura também pode ajudar a categorizar grupos no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="ec8de-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="ec8de-107">Você pode usar a política para bloquear a utilização de palavras específicas em nomes de grupo e aliases.</span><span class="sxs-lookup"><span data-stu-id="ec8de-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="ec8de-108">A política de nomenclatura é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span><span class="sxs-lookup"><span data-stu-id="ec8de-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="ec8de-109">Ela é aplicada ao nome do grupo e ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="ec8de-110">Ela é aplicada quando um usuário cria um grupo e quando o nome ou o alias do grupo é editado para um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="ec8de-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="ec8de-111">Uma política de nomenclatura de grupo do Microsoft 365 só se aplica aos grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec8de-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="ec8de-112">Ele não se aplica a grupos de distribuição criados no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec8de-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="ec8de-113">Para criar uma política de nomenclatura para grupos de distribuição, consulte [criar uma política de nomenclatura de grupo de distribuição](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="ec8de-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="ec8de-114">A política de nomeação de grupo consiste nos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="ec8de-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="ec8de-115">**Política de nomenclatura de sufixo de prefixo**: você pode usar prefixos ou sufixos para definir a Convenção de nomenclatura de grupos (por exemplo: " \_ minha engenharia de grupo dos EUA \_ ").</span><span class="sxs-lookup"><span data-stu-id="ec8de-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="ec8de-116">Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [departamento] que serão substituídos com base no usuário que está criando o grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="ec8de-117">**Palavras bloqueadas personalizadas**: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueados em grupos criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="ec8de-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="ec8de-118">(Por exemplo: "CEO, folha de pagamento, RH").</span><span class="sxs-lookup"><span data-stu-id="ec8de-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="ec8de-119">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="ec8de-119">Licensing requirements</span></span>

<span data-ttu-id="ec8de-120">O uso da política de nomenclatura do Azure AD para grupos do Microsoft 365 requer que você tenha, mas não necessariamente, atribua uma licença do Azure Active Directory Premium P1 ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec8de-120">Using Azure AD naming policy for Microsoft 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="ec8de-121">Isso também é necessário para o administrador que cria a política de nomenclatura de grupos.</span><span class="sxs-lookup"><span data-stu-id="ec8de-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="ec8de-122">Política de nomenclatura de sufixo de prefixo</span><span class="sxs-lookup"><span data-stu-id="ec8de-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="ec8de-123">Os prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário.</span><span class="sxs-lookup"><span data-stu-id="ec8de-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="ec8de-124">Cadeias de caracteres fixas</span><span class="sxs-lookup"><span data-stu-id="ec8de-124">Fixed strings</span></span>

<span data-ttu-id="ec8de-125">Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à navegação à esquerda das cargas de trabalho do grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="ec8de-126">Alguns dos sufixos de prefixos comuns são palavras-chave como "GRP \_ name", " \# name", " \_ name"</span><span class="sxs-lookup"><span data-stu-id="ec8de-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="ec8de-127">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec8de-127">Attributes</span></span>

<span data-ttu-id="ec8de-128">Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [departamento] e onde ele foi criado de como [país].</span><span class="sxs-lookup"><span data-stu-id="ec8de-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ec8de-129">**Exemplos**</span><span class="sxs-lookup"><span data-stu-id="ec8de-129">**Examples**</span></span>|<span data-ttu-id="ec8de-130">Policy = "GRP [Nome_do_grupo] [departamento]"</span><span class="sxs-lookup"><span data-stu-id="ec8de-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="ec8de-131">Departamento do usuário = engenharia</span><span class="sxs-lookup"><span data-stu-id="ec8de-131">User's department = Engineering</span></span>|
||<span data-ttu-id="ec8de-132">Nome do grupo criado = "engenharia de grupo meu GRP"</span><span class="sxs-lookup"><span data-stu-id="ec8de-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="ec8de-133">Os atributos do Azure Active Directory (Azure AD) com suporte são [departamento], [empresa], [Office], [StateOrProvince], [CountryOrRegion] e [título].</span><span class="sxs-lookup"><span data-stu-id="ec8de-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="ec8de-134">Atributos de usuário não suportados são considerados cadeias de caracteres fixas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-134">Unsupported user attributes are considered as fixed strings.</span></span> <span data-ttu-id="ec8de-135">Por exemplo</span><span class="sxs-lookup"><span data-stu-id="ec8de-135">E.g.</span></span> <span data-ttu-id="ec8de-136">"[CEP]"</span><span class="sxs-lookup"><span data-stu-id="ec8de-136">"[postalCode]"</span></span>

- <span data-ttu-id="ec8de-137">Não há suporte para atributos de extensão e atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ec8de-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="ec8de-138">É recomendável que você use atributos com valores preenchidos para todos os usuários em sua organização e não use atributos com valores mais longos.</span><span class="sxs-lookup"><span data-stu-id="ec8de-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="ec8de-139">Aspectos a serem verificados</span><span class="sxs-lookup"><span data-stu-id="ec8de-139">Things to look out for</span></span>

- <span data-ttu-id="ec8de-140">Durante a criação da política, o comprimento total de cadeias de caracteres e sufixos é restrito a 53 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ec8de-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="ec8de-141">Os prefixos e sufixos podem conter caracteres especiais compatíveis com o nome do grupo e o alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="ec8de-142">Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias do grupo, eles são aplicados apenas ao nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="ec8de-143">Portanto, nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos que foram aplicados ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ec8de-144">Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="ec8de-144">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="ec8de-145">Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="ec8de-145">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="ec8de-146">Se você estiver usando os grupos conectados do Yammer Microsoft 365, evite usar os seguintes caracteres em sua política de nomenclatura: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="ec8de-146">If you are using Yammer Microsoft 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="ec8de-147">Se esses caracteres estiverem na política de nomenclatura, os usuários normais do Yammer não poderão criar grupos.</span><span class="sxs-lookup"><span data-stu-id="ec8de-147">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="ec8de-148">Palavras bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="ec8de-148">Custom blocked words</span></span>

<span data-ttu-id="ec8de-149">Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em nomes de grupo e aliases.</span><span class="sxs-lookup"><span data-stu-id="ec8de-149">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="ec8de-150">Nenhuma pesquisa de subcadeias de caracteres é executada; especificamente, uma correspondência exata entre o nome digitado pelo usuário e as palavras bloqueadas personalizadas é necessária para acionar uma falha.</span><span class="sxs-lookup"><span data-stu-id="ec8de-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="ec8de-151">A pesquisa de subcadeia de caracteres não é feita para que os usuários possam usar algumas palavras comuns como ' classe ', mesmo se ' ass ' for uma palavra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="ec8de-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="ec8de-152">**Aspectos a serem verificados**:</span><span class="sxs-lookup"><span data-stu-id="ec8de-152">**Things to look out for**:</span></span>

- <span data-ttu-id="ec8de-153">As palavras bloqueadas não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="ec8de-154">Quando um usuário insere uma palavra bloqueada, o cliente do grupo mostrará uma mensagem de erro com a palavra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="ec8de-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="ec8de-155">Não há restrições de caracteres nas palavras bloqueadas usadas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="ec8de-156">Há um limite de 5000 palavras que podem ser definidas como palavras bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-156">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="ec8de-157">Substituição de administrador</span><span class="sxs-lookup"><span data-stu-id="ec8de-157">Admin override</span></span>

<span data-ttu-id="ec8de-158">Os administradores seletivos são isentos dessas políticas, em todas as cargas de trabalho de grupo e pontos de extremidade, para que eles possam criar grupos com essas palavras bloqueadas e com as convenções de nomenclatura desejadas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-158">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="ec8de-159">Veja a seguir a lista de funções de administrador isentas da política de nomeação de grupo.</span><span class="sxs-lookup"><span data-stu-id="ec8de-159">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="ec8de-160">Administrador global</span><span class="sxs-lookup"><span data-stu-id="ec8de-160">Global admin</span></span>

- <span data-ttu-id="ec8de-161">Suporte da camada 1 do parceiro</span><span class="sxs-lookup"><span data-stu-id="ec8de-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="ec8de-162">Suporte da camada 2 do parceiro</span><span class="sxs-lookup"><span data-stu-id="ec8de-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="ec8de-163">Administrador de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="ec8de-163">User account admin</span></span>

- <span data-ttu-id="ec8de-164">Gravadores de diretório</span><span class="sxs-lookup"><span data-stu-id="ec8de-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="ec8de-165">Como configurar a política de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ec8de-165">How to set up the naming policy</span></span>

<span data-ttu-id="ec8de-166">Para configurar uma política de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="ec8de-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="ec8de-167">No [Azure Active Directory](https://aad.portal.azure.com), em **gerenciar**, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="ec8de-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="ec8de-168">Em **configurações**, clique em **política de nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="ec8de-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="ec8de-169">Escolha a guia **política de nomeação de grupo** .</span><span class="sxs-lookup"><span data-stu-id="ec8de-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="ec8de-170">Em **política atual**, escolha se você deseja exigir um prefixo ou sufixo, ou ambos, e marque as caixas de seleção apropriadas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="ec8de-171">Escolha entre **atributo** e **cadeia de caracteres** para cada linha e, em seguida, especifique o atributo ou a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ec8de-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="ec8de-172">Após adicionar os prefixos e sufixos necessários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="ec8de-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Captura de tela das configurações de política de nomenclatura de grupos no Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="ec8de-174">As equipes do StaffHub não seguem a política de nomenclatura, mas o grupo base 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec8de-174">StaffHub teams do not follow the naming policy, but the underlying Microsoft 365 group does.</span></span> <span data-ttu-id="ec8de-175">O nome da equipe do StaffHub não aplica os prefixos e sufixos e não verifica as palavras bloqueadas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ec8de-175">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="ec8de-176">Mas o StaffHub aplica os prefixos e sufixos e remove as palavras bloqueadas do grupo subjacente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec8de-176">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Microsoft 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="ec8de-177">Mais artigos sobre política de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ec8de-177">More articles on naming policy</span></span>

[<span data-ttu-id="ec8de-178">Aplicar uma política de nomenclatura para grupos do Microsoft 365 no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ec8de-178">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="ec8de-179">Cmdlets do Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="ec8de-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
