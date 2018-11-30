---
title: 'Etapa 15: Configurar associação de grupo dinâmica'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a associação de grupo automática com base nos atributos de conta.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865195"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="31a44-103">Etapa 15: Configurar associação de grupo dinâmica</span><span class="sxs-lookup"><span data-stu-id="31a44-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="31a44-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="31a44-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="31a44-p101">Nesta etapa, você vai criar uma série de regras que adicionam ou removem automaticamente contas de usuários como membros de um grupo no Azure AD, o que é conhecido como *associação de grupo dinâmica*. As regras são baseadas nos atributos de conta de usuário, como o departamento ou o país.</span><span class="sxs-lookup"><span data-stu-id="31a44-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="31a44-108">Veja aqui como as regras são aplicadas:</span><span class="sxs-lookup"><span data-stu-id="31a44-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="31a44-109">Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.</span><span class="sxs-lookup"><span data-stu-id="31a44-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="31a44-110">Se a conta de usuário não for um membro do grupo, mas seus atributos forem alterados de modo que ela passa a atender a todas as regras do grupo, ela se tornará membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="31a44-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="31a44-111">Se a conta de usuário não atender a toda as regras do grupo, ela não será incluída no grupo.</span><span class="sxs-lookup"><span data-stu-id="31a44-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="31a44-112">Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.</span><span class="sxs-lookup"><span data-stu-id="31a44-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="31a44-p102">Para usar a associação dinâmica, primeiro você precisa determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta de usuário. Por exemplo, todos os membros do departamento de vendas devem estar no grupo de vendas no Azure AD, com base em no atributo de conta de usuário por departamento definido como "Vendas".</span><span class="sxs-lookup"><span data-stu-id="31a44-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="31a44-115">Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="31a44-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="31a44-116">Os resultados desta etapa são:</span><span class="sxs-lookup"><span data-stu-id="31a44-116">The results of this step are:</span></span>

- <span data-ttu-id="31a44-117">um conjunto de grupos do Azure AD que pode ser configurado quanto à associação dinâmica;</span><span class="sxs-lookup"><span data-stu-id="31a44-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="31a44-118">um conjunto de regras em cada grupo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="31a44-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="31a44-120">Guia do Laboratório de Teste: automatizar licenças e associação a grupos</span><span class="sxs-lookup"><span data-stu-id="31a44-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="31a44-121">Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-dyn-groups) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="31a44-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="31a44-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="31a44-122">Next step</span></span>

[<span data-ttu-id="31a44-123">Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="31a44-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
