---
title: Política de nomeação de grupos do Microsoft 365
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
description: Saiba como criar uma política de nomeação para grupos do Microsoft 365.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759819"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="86c37-103">Política de nomeação de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86c37-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="86c37-104">Você pode usar uma política de nomeação de grupo para impor uma estratégia de nomeação consistente para grupos criados por usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="86c37-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="86c37-105">Uma política de nomeação pode ajudar você e seus usuários a identificar a função do grupo, associação, região geográfica ou quem criou o grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="86c37-106">A política de nomeação também pode ajudar a categorizar grupos no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="86c37-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="86c37-107">Você pode usar a política para impedir que palavras específicas são usadas em aliases e nomes de grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="86c37-108">A política de nomeação é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span><span class="sxs-lookup"><span data-stu-id="86c37-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="86c37-109">Ele é aplicado ao nome do grupo e ao alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="86c37-110">Ele também é aplicado quando um usuário cria um grupo e quando o nome do grupo, alias, descrição ou avatar é editado para um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="86c37-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="86c37-111">Uma política de nomeação de grupo do Microsoft 365 só se aplica a grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86c37-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="86c37-112">Não se aplica a grupos de distribuição criados no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="86c37-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="86c37-113">Para criar uma política de nomeação para grupos de distribuição, consulte [Criar uma política de nomeação de grupo de distribuição.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)</span><span class="sxs-lookup"><span data-stu-id="86c37-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="86c37-114">A política de nomeação de grupo consiste nos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="86c37-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="86c37-115">Política de **nomeação** de prefixo-sufixo: você pode usar prefixos ou sufixos para definir a convenção de nomen por grupos (por exemplo: "US \_ My Group \_ Engineering").</span><span class="sxs-lookup"><span data-stu-id="86c37-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="86c37-116">Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [Departamento] que serão substituídos com base no usuário que está criando o grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="86c37-117">**Palavras bloqueadas** personalizadas: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueadas em grupos criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="86c37-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="86c37-118">(Por exemplo: "CEO, Folha de Pagamento, RH").</span><span class="sxs-lookup"><span data-stu-id="86c37-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="86c37-119">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="86c37-119">Licensing requirements</span></span>

<span data-ttu-id="86c37-120">O uso da política de nomeação do Azure AD para Grupos do Microsoft 365 exige que você possua, mas não necessariamente atribua uma licença do Azure Active Directory Premium P1 ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86c37-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="86c37-121">Isso também é necessário para o administrador que cria a política de nomeação de grupos.</span><span class="sxs-lookup"><span data-stu-id="86c37-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="86c37-122">Prefix-Suffix nomeação de política</span><span class="sxs-lookup"><span data-stu-id="86c37-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="86c37-123">Prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos do usuário.</span><span class="sxs-lookup"><span data-stu-id="86c37-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="86c37-124">Cadeias de caracteres fixas</span><span class="sxs-lookup"><span data-stu-id="86c37-124">Fixed strings</span></span>

<span data-ttu-id="86c37-125">Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à esquerda da navegação das cargas de trabalho do grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="86c37-126">Alguns dos sufixos de prefixos comuns são palavras-chave como 'Grp \_ Name', ' \# Name', ' \_ Name'</span><span class="sxs-lookup"><span data-stu-id="86c37-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="86c37-127">Atributos</span><span class="sxs-lookup"><span data-stu-id="86c37-127">Attributes</span></span>

<span data-ttu-id="86c37-128">Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [Departamento] e onde ele foi criado a partir de [País].</span><span class="sxs-lookup"><span data-stu-id="86c37-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="86c37-129">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="86c37-129">Examples:</span></span>

- <span data-ttu-id="86c37-130">Policy = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="86c37-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="86c37-131">Departamento do usuário = Engenharia</span><span class="sxs-lookup"><span data-stu-id="86c37-131">User's department = Engineering</span></span>
- <span data-ttu-id="86c37-132">Nome do grupo criado = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="86c37-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="86c37-133">Os atributos com suporte do Azure Active Directory (Azure AD) são [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], e [Title].</span><span class="sxs-lookup"><span data-stu-id="86c37-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="86c37-134">Atributos de usuário sem suporte são considerados cadeias de caracteres fixas, por exemplo [postalCode].</span><span class="sxs-lookup"><span data-stu-id="86c37-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="86c37-135">Atributos de extensão e atributos personalizados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="86c37-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="86c37-136">É recomendável que você use atributos que tenham valores preenchidos para todos os usuários em sua organização e não use atributos com valores mais longos.</span><span class="sxs-lookup"><span data-stu-id="86c37-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="86c37-137">Coisas a se procurar</span><span class="sxs-lookup"><span data-stu-id="86c37-137">Things to look out for</span></span>

- <span data-ttu-id="86c37-138">Durante a criação da política, o comprimento total de prefixos e sufixos é restrito a 53 caracteres.</span><span class="sxs-lookup"><span data-stu-id="86c37-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="86c37-139">Prefixos e sufixos podem conter caracteres especiais com suporte no nome do grupo e no alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="86c37-140">Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias de grupo, eles são aplicados apenas ao nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="86c37-141">Portanto, nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos aplicados ao alias de grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="86c37-142">Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="86c37-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="86c37-143">Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.</span><span class="sxs-lookup"><span data-stu-id="86c37-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="86c37-144">Se você estiver usando os grupos conectados do Yammer do Office 365, evite usar os seguintes caracteres em sua política de nomeação: @, \# , \[ , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="86c37-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="86c37-145">Se esses caracteres estão na política de nomeação, os usuários regulares do Yammer não poderão criar grupos.</span><span class="sxs-lookup"><span data-stu-id="86c37-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="86c37-146">Use cadeias de caracteres curtas como sufixo.</span><span class="sxs-lookup"><span data-stu-id="86c37-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="86c37-147">Use atributos com valores.</span><span class="sxs-lookup"><span data-stu-id="86c37-147">Use attributes with values.</span></span>
> - <span data-ttu-id="86c37-148">Não seja muito criativo, o comprimento total do nome tem no máximo 264 caracteres.</span><span class="sxs-lookup"><span data-stu-id="86c37-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="86c37-149">Carregue palavras bloqueadas específicas da sua organização para restringir o uso.</span><span class="sxs-lookup"><span data-stu-id="86c37-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="86c37-150">Palavras bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="86c37-150">Custom blocked words</span></span>

<span data-ttu-id="86c37-151">Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em aliases e nomes de grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="86c37-152">Nenhuma pesquisa de sub-cadeia de caracteres é realizada; especificamente, é necessária uma combinação exata entre o nome inserido pelo usuário e as palavras bloqueadas personalizadas para disparar uma falha.</span><span class="sxs-lookup"><span data-stu-id="86c37-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="86c37-153">**Coisas a se procurar:**</span><span class="sxs-lookup"><span data-stu-id="86c37-153">**Things to look out for**:</span></span>

- <span data-ttu-id="86c37-154">As palavras bloqueadas não fazem parte de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="86c37-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="86c37-155">Quando um usuário inserir uma palavra bloqueada, o cliente do grupo mostrará uma mensagem de erro com a palavra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="86c37-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="86c37-156">Não há restrições de caractere nas palavras bloqueadas usadas.</span><span class="sxs-lookup"><span data-stu-id="86c37-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="86c37-157">Há um limite de 5.000 palavras que podem ser definidas como palavras bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="86c37-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="86c37-158">Substituição de administrador</span><span class="sxs-lookup"><span data-stu-id="86c37-158">Admin override</span></span>

<span data-ttu-id="86c37-159">Alguns administradores estão isentos dessas políticas, em todas as cargas de trabalho e pontos de extremidade do grupo, para que possam criar grupos com essas palavras bloqueadas e com suas convenções de nomenais desejadas.</span><span class="sxs-lookup"><span data-stu-id="86c37-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="86c37-160">A seguir estão a lista de funções de administrador isentas da política de nomeação de grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="86c37-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="86c37-161">Global admin</span></span>

- <span data-ttu-id="86c37-162">Suporte ao Nível 1 do Parceiro</span><span class="sxs-lookup"><span data-stu-id="86c37-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="86c37-163">Suporte ao Nível 2 do Parceiro</span><span class="sxs-lookup"><span data-stu-id="86c37-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="86c37-164">Administrador de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="86c37-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="86c37-165">Como configurar a política de nomeação</span><span class="sxs-lookup"><span data-stu-id="86c37-165">How to set up the naming policy</span></span>

<span data-ttu-id="86c37-166">Para configurar uma política de nomeação:</span><span class="sxs-lookup"><span data-stu-id="86c37-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="86c37-167">No [Azure Active Directory,](https://aad.portal.azure.com)em **Gerenciar,** clique em **Grupos.**</span><span class="sxs-lookup"><span data-stu-id="86c37-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="86c37-168">Em **Configurações,** clique **em Política de Nomen por nomeação.**</span><span class="sxs-lookup"><span data-stu-id="86c37-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="86c37-169">Escolha a **guia Política de nomeação de** grupo.</span><span class="sxs-lookup"><span data-stu-id="86c37-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="86c37-170">Em **Política atual,** escolha se deseja exigir um prefixo ou sufixo ou ambos e marque as caixas de seleção apropriadas.</span><span class="sxs-lookup"><span data-stu-id="86c37-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="86c37-171">Escolha entre **Atributo** e **Cadeia de** Caracteres para cada linha e especifique o atributo ou a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="86c37-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="86c37-172">Quando tiver adicionado os prefixos e sufixos necessários, clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="86c37-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Captura de tela das configurações de política de nomeação de grupos no Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="86c37-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="86c37-174">Related topics</span></span>

[<span data-ttu-id="86c37-175">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="86c37-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="86c37-176">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="86c37-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="86c37-177">Cmdlets Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="86c37-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
