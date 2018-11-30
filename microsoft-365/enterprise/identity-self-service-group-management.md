---
title: 'Etapa 14: Permitir que usuários criem e gerenciem seus próprios grupos'
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
description: Entender e configurar o gerenciamento de grupos de autoatendimento do Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865008"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="ceeaa-103">Etapa 14: Permitir que usuários criem e gerenciem seus próprios grupos</span><span class="sxs-lookup"><span data-stu-id="ceeaa-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="ceeaa-104">*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ceeaa-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="ceeaa-p101">Nesta etapa, você vai identificar os grupos do Azure Active Directory (AD) que podem ser gerenciados por proprietários de grupos em vez de administradores de TI. Conhecido como *gerenciamento de grupos de autoatendimento*, esse recurso permite que os proprietários de grupos que não estejam atribuídos a uma função administrativa criem e gerenciem grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="ceeaa-p102">Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="ceeaa-p103">O gerenciamento de grupos de autoatendimento está disponível apenas para os grupos do Office 365 e de segurança do Azure AD. Não está disponível para grupos habilitados para email, listas de distribuição ou qualquer outro grupo que tenha sido sincronizado no Windows Server Active Directory (AD) local.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="ceeaa-111">Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="ceeaa-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="ceeaa-112">Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-self-service-groups) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="ceeaa-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ceeaa-113">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ceeaa-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="ceeaa-114">Configurar a associação de grupo dinâmica</span><span class="sxs-lookup"><span data-stu-id="ceeaa-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
