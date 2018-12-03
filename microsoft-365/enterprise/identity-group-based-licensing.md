---
title: 'Etapa 12: Configurar o licenciamento automático'
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
description: Entender e configurar o licenciamento baseado em grupo para grupos do Azure AD.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864661"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="124cc-103">Etapa 12: Configurar o licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="124cc-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="124cc-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="124cc-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="124cc-p101">Nesta etapa, você vai configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo. Essa ação é conhecida como *licenciamento baseado em grupo*. Se uma conta de usuário for adicionada ou removida do grupo, as licenças para as assinaturas do grupo serão automaticamente atribuídas ou removidas da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="124cc-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="124cc-108">No Microsoft 365 Enterprise, você configura grupos de segurança do Azure AD para atribuir estas duas licenças:</span><span class="sxs-lookup"><span data-stu-id="124cc-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="124cc-109">Office 365 Enterprise E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="124cc-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="124cc-110">Enterprise Mobility + Security (EMS) E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="124cc-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="124cc-p102">Usando os grupos que foram identificados na Etapa 2, procure aqueles com uma lista de contas em que todos os usuários precisem ter as licenças do Office 365 e do EMS. Verifique se você tem licenças suficientes para todos os membros do grupo. Se não houver licenças para todos, os novos usuários não receberão licenças até que estas estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="124cc-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="124cc-114">Você não deve configurar o *licenciamento baseado em grupo* para grupos que contenham contas do Azure para empresas (B2B).</span><span class="sxs-lookup"><span data-stu-id="124cc-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="124cc-115">Consulte as [noções básicas sobre o licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="124cc-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="124cc-116">Consulte as [etapas para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="124cc-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="124cc-117">Os resultados desta etapa são:</span><span class="sxs-lookup"><span data-stu-id="124cc-117">The results of this step are:</span></span>

- <span data-ttu-id="124cc-118">Você identificou quais grupos de segurança são adequados para o licenciamento baseado em grupo.</span><span class="sxs-lookup"><span data-stu-id="124cc-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="124cc-119">Você configurou esses grupos para o licenciamento baseado em grupo.</span><span class="sxs-lookup"><span data-stu-id="124cc-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="124cc-121">Guia do Laboratório de Teste: automatizar licenças e associação a grupos</span><span class="sxs-lookup"><span data-stu-id="124cc-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="124cc-122">Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-group-license) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="124cc-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="124cc-123">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="124cc-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="124cc-124">Monitorar a atividade de entrada e do locatário</span><span class="sxs-lookup"><span data-stu-id="124cc-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

