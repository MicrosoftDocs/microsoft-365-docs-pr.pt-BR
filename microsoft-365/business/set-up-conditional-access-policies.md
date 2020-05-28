---
title: Configurar políticas de acesso condicional para campanhas do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como configurar políticas de acesso condicional para o Microsoft 365 Campaigns para adicionar mais segurança substancial.
ms.openlocfilehash: d7c9cfee2ef00e4ebe231a28ccca185c10f53c6b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403009"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="92cad-103">Configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="92cad-103">Set up conditional access policies</span></span>

<span data-ttu-id="92cad-104">As políticas de [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) adicionam mais segurança substancial.</span><span class="sxs-lookup"><span data-stu-id="92cad-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="92cad-105">A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base que são recomendadas para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="92cad-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="92cad-106">As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra vários ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="92cad-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="92cad-107">Esses ataques comuns podem incluir a irrigação de senha, a repetição e o phishing.</span><span class="sxs-lookup"><span data-stu-id="92cad-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="92cad-108">Essas políticas exigem que administradores e usuários insiram uma segunda forma de autenticação (chamada de autenticação multifator, ou MFA) quando determinadas condições são atendidas.</span><span class="sxs-lookup"><span data-stu-id="92cad-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="92cad-109">Por exemplo, se um usuário estiver entrando em um país diferente, o logon poderá ser considerado arriscado e o usuário deverá fornecer uma forma adicional de autenticação.</span><span class="sxs-lookup"><span data-stu-id="92cad-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="92cad-110">No momento, as políticas de linha de base incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="92cad-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="92cad-111">**Exigir MFA para administradores** &ndash; Requer autenticação multifator para as funções de administrador mais privilegiadas, incluindo administrador global.</span><span class="sxs-lookup"><span data-stu-id="92cad-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="92cad-112">Proteção do usuário **final** &ndash; Requer autenticação multifator para usuários somente quando um logon é arriscado.</span><span class="sxs-lookup"><span data-stu-id="92cad-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="92cad-113">**Bloquear autenticação** &ndash; herdada Aplicativos cliente mais antigos e alguns aplicativos novos não usam protocolos de autenticação mais recentes e mais seguros.</span><span class="sxs-lookup"><span data-stu-id="92cad-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="92cad-114">Esses aplicativos antigos podem ignorar as políticas de acesso condicional e obter acesso não autorizado ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="92cad-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="92cad-115">Esta política bloqueia o acesso de clientes que não dão suporte ao acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="92cad-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="92cad-116">**Exigir MFA para gerenciamento** &ndash; de serviços Requer autenticação multifator para acessar ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura as políticas de linha de base).</span><span class="sxs-lookup"><span data-stu-id="92cad-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="92cad-117">A Microsoft recomenda que você habilite todas essas políticas de linha de base.</span><span class="sxs-lookup"><span data-stu-id="92cad-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="92cad-118">Depois que essas políticas forem habilitadas, os administradores e os usuários serão solicitados a registrar a autenticação de fator de vários grupos do Azure.</span><span class="sxs-lookup"><span data-stu-id="92cad-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="92cad-119">Para obter mais informações sobre essas políticas, consulte [o que são políticas de linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="92cad-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="92cad-120">Configurar políticas de linha de base</span><span class="sxs-lookup"><span data-stu-id="92cad-120">Set up baseline policies</span></span>

1. <span data-ttu-id="92cad-121">Vá para [portal do Azure](https://portal.azure.com)e navegue até acesso **condicional do Azure Active Directory** \> **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="92cad-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="92cad-122">As políticas de linha de base são listadas na página.</span><span class="sxs-lookup"><span data-stu-id="92cad-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="92cad-123">![Página que lista as políticas de linha de base para acesso condicional.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="92cad-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="92cad-124">Consulte as seguintes instruções específicas para cada política:</span><span class="sxs-lookup"><span data-stu-id="92cad-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="92cad-125">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="92cad-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="92cad-126">Exigir MFA para usuários</span><span class="sxs-lookup"><span data-stu-id="92cad-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="92cad-127">Bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="92cad-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="92cad-128">Exigir MFA para gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="92cad-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="92cad-129">Você pode configurar várias políticas adicionais, como exigir aplicativos cliente aprovados.</span><span class="sxs-lookup"><span data-stu-id="92cad-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="92cad-130">Para obter mais informações, consulte a [documentação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="92cad-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
