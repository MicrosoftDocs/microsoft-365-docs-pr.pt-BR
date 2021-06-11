---
title: Microsoft 365 de nomeação de grupos
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
recommendations: false
description: Saiba como criar uma política de nomen por Microsoft 365 grupos.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538166"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="fda6d-103">Microsoft 365 de nomeação de grupos</span><span class="sxs-lookup"><span data-stu-id="fda6d-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="fda6d-104">Você pode usar uma política de nomenis de grupo para impor uma estratégia de nomenisão consistente para grupos criados pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fda6d-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="fda6d-105">Uma política de nomenrção pode ajudar você e seus usuários a identificar a função do grupo, associação, região geográfica ou quem criou o grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="fda6d-106">A política de nomenrção também pode ajudar a categorizar grupos no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="fda6d-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="fda6d-107">Você pode usar a política para impedir que palavras específicas são usadas em nomes de grupo e aliases.</span><span class="sxs-lookup"><span data-stu-id="fda6d-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="fda6d-108">A política de nomenisagem é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer etc.).</span><span class="sxs-lookup"><span data-stu-id="fda6d-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="fda6d-109">Ele é aplicado ao nome do grupo e ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="fda6d-110">Ele também é aplicado quando um usuário cria um grupo e quando o nome do grupo, alias, descrição ou avatar é editado para um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="fda6d-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="fda6d-111">Uma Microsoft 365 de nomenis de grupo só se aplica a Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="fda6d-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="fda6d-112">Ele não se aplica a grupos de distribuição criados em Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fda6d-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="fda6d-113">Para criar uma política de nomenisão para grupos de distribuição, consulte [Create a distribution group noming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="fda6d-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="fda6d-114">A política de nomenisagem de grupo consiste nos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="fda6d-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="fda6d-115">**Política de** nomenis de prefixo-sufixo : você pode usar prefixos ou sufixos para definir a convenção de nomenis de grupos (por exemplo: "US \_ My Group \_ Engineering").</span><span class="sxs-lookup"><span data-stu-id="fda6d-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="fda6d-116">Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [Departamento] que serão substituídos com base no usuário que está criando o grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="fda6d-117">**Palavras bloqueadas** personalizadas: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueadas em grupos criados pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="fda6d-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="fda6d-118">(Por exemplo: "CEO, Folha de Pagamento, RH").</span><span class="sxs-lookup"><span data-stu-id="fda6d-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="fda6d-119">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="fda6d-119">Licensing requirements</span></span>

<span data-ttu-id="fda6d-120">O uso da política de nomenização do Azure AD para grupos do Microsoft 365 exige que você possua, mas não necessariamente atribua uma licença P1 do Azure Active Directory Premium ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fda6d-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="fda6d-121">Isso também é necessário para o administrador que cria a política de nomenrção de grupos.</span><span class="sxs-lookup"><span data-stu-id="fda6d-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="fda6d-122">Prefix-Suffix de nomenis</span><span class="sxs-lookup"><span data-stu-id="fda6d-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="fda6d-123">Prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário.</span><span class="sxs-lookup"><span data-stu-id="fda6d-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="fda6d-124">Cadeias de caracteres fixas</span><span class="sxs-lookup"><span data-stu-id="fda6d-124">Fixed strings</span></span>

<span data-ttu-id="fda6d-125">Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à esquerda da navegação das cargas de trabalho do grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="fda6d-126">Alguns dos sufixos de prefixos comuns são palavras-chave como 'Grp \_ Name' , ' \# Name', ' \_ Name'</span><span class="sxs-lookup"><span data-stu-id="fda6d-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="fda6d-127">Atributos</span><span class="sxs-lookup"><span data-stu-id="fda6d-127">Attributes</span></span>

<span data-ttu-id="fda6d-128">Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [Departamento] e onde ele foi criado a partir de como [País].</span><span class="sxs-lookup"><span data-stu-id="fda6d-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="fda6d-129">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="fda6d-129">Examples:</span></span>

- <span data-ttu-id="fda6d-130">Política = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="fda6d-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="fda6d-131">Departamento do usuário = Engenharia</span><span class="sxs-lookup"><span data-stu-id="fda6d-131">User's department = Engineering</span></span>
- <span data-ttu-id="fda6d-132">Nome do grupo criado = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="fda6d-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="fda6d-133">Os atributos Azure Active Directory (Azure AD) são [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], e [Title].</span><span class="sxs-lookup"><span data-stu-id="fda6d-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="fda6d-134">Atributos de usuário sem suporte são considerados como cadeias de caracteres fixas, por exemplo [postalCode].</span><span class="sxs-lookup"><span data-stu-id="fda6d-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="fda6d-135">Atributos de extensão e atributos personalizados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="fda6d-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="fda6d-136">É recomendável que você use atributos que tenham valores preenchidos para todos os usuários em sua organização e não use atributos que tenham valores mais longos.</span><span class="sxs-lookup"><span data-stu-id="fda6d-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="fda6d-137">Coisas para se ter em atenção</span><span class="sxs-lookup"><span data-stu-id="fda6d-137">Things to look out for</span></span>

- <span data-ttu-id="fda6d-138">Durante a criação de política, o comprimento da cadeia de caracteres de prefixos e sufixos totais é restrito a 53 caracteres.</span><span class="sxs-lookup"><span data-stu-id="fda6d-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="fda6d-139">Prefixos e sufixos podem conter caracteres especiais com suporte no nome do grupo e no alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="fda6d-140">Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias do grupo, eles são aplicados apenas ao nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="fda6d-141">Nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos aplicados ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fda6d-142">Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="fda6d-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="fda6d-143">Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="fda6d-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="fda6d-144">Se você estiver usando Yammer Office 365 grupos conectados, evite usar os seguintes caracteres em sua política de nomenisagem: @, \# \[ , , , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="fda6d-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="fda6d-145">Se esses caracteres estão na política de nomenisagem, Yammer usuários regulares não poderão criar grupos.</span><span class="sxs-lookup"><span data-stu-id="fda6d-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="fda6d-146">Use cadeias de caracteres curtas como sufixo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="fda6d-147">Use atributos com valores.</span><span class="sxs-lookup"><span data-stu-id="fda6d-147">Use attributes with values.</span></span>
> - <span data-ttu-id="fda6d-148">Não seja muito criativo, o comprimento total do nome tem no máximo 264 caracteres.</span><span class="sxs-lookup"><span data-stu-id="fda6d-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="fda6d-149">Upload palavras bloqueadas específicas da sua organização para restringir o uso.</span><span class="sxs-lookup"><span data-stu-id="fda6d-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="fda6d-150">Palavras bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="fda6d-150">Custom blocked words</span></span>

<span data-ttu-id="fda6d-151">Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em nomes de grupo e aliases.</span><span class="sxs-lookup"><span data-stu-id="fda6d-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="fda6d-152">Nenhuma pesquisa de sub-cadeia de caracteres é realizada; especificamente, uma combinação exata entre o nome inserido pelo usuário e as palavras bloqueadas personalizadas é necessária para disparar uma falha.</span><span class="sxs-lookup"><span data-stu-id="fda6d-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="fda6d-153">**Coisas a se ter em atenção:**</span><span class="sxs-lookup"><span data-stu-id="fda6d-153">**Things to look out for**:</span></span>

- <span data-ttu-id="fda6d-154">As palavras bloqueadas não têm maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fda6d-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="fda6d-155">Quando um usuário inserir uma palavra bloqueada, o cliente de grupo mostrará uma mensagem de erro com a palavra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="fda6d-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="fda6d-156">Não há restrições de caractere nas palavras bloqueadas usadas.</span><span class="sxs-lookup"><span data-stu-id="fda6d-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="fda6d-157">Há um limite de 5.000 palavras que podem ser definidas como palavras bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="fda6d-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="fda6d-158">Substituição de administrador</span><span class="sxs-lookup"><span data-stu-id="fda6d-158">Admin override</span></span>

<span data-ttu-id="fda6d-159">Alguns administradores são isentos dessas políticas, em todas as cargas de trabalho de grupo e pontos de extremidade, para que eles possam criar grupos com essas palavras bloqueadas e com suas convenções de nomenais desejadas.</span><span class="sxs-lookup"><span data-stu-id="fda6d-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="fda6d-160">Veja a seguir a lista de funções de administrador isentas da política de nomenis de grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="fda6d-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="fda6d-161">Global admin</span></span>

- <span data-ttu-id="fda6d-162">Suporte ao Partner Tier 1</span><span class="sxs-lookup"><span data-stu-id="fda6d-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="fda6d-163">Suporte ao Partner Tier 2</span><span class="sxs-lookup"><span data-stu-id="fda6d-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="fda6d-164">Administrador de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="fda6d-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="fda6d-165">Como configurar a política de nomen</span><span class="sxs-lookup"><span data-stu-id="fda6d-165">How to set up the naming policy</span></span>

<span data-ttu-id="fda6d-166">Para configurar uma política de nomenrção:</span><span class="sxs-lookup"><span data-stu-id="fda6d-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="fda6d-167">Em [Azure Active Directory](https://aad.portal.azure.com), em **Gerenciar,** clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="fda6d-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="fda6d-168">Em **Configurações,** clique **em Política de Nomenis.**</span><span class="sxs-lookup"><span data-stu-id="fda6d-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="fda6d-169">Escolha a **guia Política de nomenis de** grupo.</span><span class="sxs-lookup"><span data-stu-id="fda6d-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="fda6d-170">Em **Política atual,** escolha se deseja exigir um prefixo ou sufixo ou ambos e selecione as caixas de seleção apropriadas.</span><span class="sxs-lookup"><span data-stu-id="fda6d-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="fda6d-171">Escolha entre **Atributo** e **Cadeia de** Caracteres para cada linha e especifique o atributo ou a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fda6d-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="fda6d-172">Quando tiver adicionado os prefixos e sufixos necessários, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fda6d-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Captura de tela das configurações de política de nomeação de grupos no Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="fda6d-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fda6d-174">Related topics</span></span>

[<span data-ttu-id="fda6d-175">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="fda6d-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="fda6d-176">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="fda6d-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="fda6d-177">Cmdlets Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="fda6d-177">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/enterprise-users/groups-settings-cmdlets)