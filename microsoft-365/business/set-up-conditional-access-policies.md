---
title: Configurar políticas de acesso condicional
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como configurar políticas de acesso condicional para o Microsoft 365 Business.
ms.openlocfilehash: 6ca3995113f090ccf2b119abde059a68ce562970
ms.sourcegitcommit: ab04fea2765a63489d70b506f0e14303a5be16a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2019
ms.locfileid: "34806808"
---
# <a name="set-up-conditional-access-policies-for-microsoft-365-business"></a><span data-ttu-id="053a0-103">Configurar políticas de acesso condicional para o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="053a0-103">Set up conditional access policies for Microsoft 365 Business</span></span>

<span data-ttu-id="053a0-104">As políticas de [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) adicionam substancial segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="053a0-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="053a0-105">A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base que são recomendadas para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="053a0-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="053a0-106">As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra vários ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="053a0-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="053a0-107">Esses ataques comuns podem incluir a irrigação de senha, a repetição e o phishing.</span><span class="sxs-lookup"><span data-stu-id="053a0-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="053a0-108">Essas políticas exigem que administradores e usuários insiram uma segunda forma de autenticação (chamada de autenticação multifator, ou MFA) quando determinadas condições são atendidas.</span><span class="sxs-lookup"><span data-stu-id="053a0-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="053a0-109">Por exemplo, se um usuário estiver entrando em um país diferente, o logon poderá ser considerado arriscado e o usuário deverá fornecer uma forma adicional de autenticação.</span><span class="sxs-lookup"><span data-stu-id="053a0-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="053a0-110">No momento, as políticas de linha de base incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="053a0-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="053a0-111">**Exigir MFA para administradores** — requer autenticação multifator para as funções de administrador mais privilegiadas, incluindo administrador global.</span><span class="sxs-lookup"><span data-stu-id="053a0-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="053a0-112">**Proteção do usuário final** — requer autenticação multifator para usuários somente quando uma entrada é arriscada.</span><span class="sxs-lookup"><span data-stu-id="053a0-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="053a0-113">**Bloquear autenticação herdada** — aplicativos cliente mais antigos e alguns aplicativos novos não usam protocolos de autenticação mais recentes, mais seguros.</span><span class="sxs-lookup"><span data-stu-id="053a0-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="053a0-114">Esses aplicativos antigos podem ignorar as políticas de acesso condicional e obter acesso não autorizado ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="053a0-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="053a0-115">Esta política bloqueia o acesso de clientes que não dão suporte ao acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="053a0-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="053a0-116">**Requer MFA para gerenciamento de serviços** — requer a autenticação multifator para acessar ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura as políticas de linha de base).</span><span class="sxs-lookup"><span data-stu-id="053a0-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="053a0-117">A Microsoft recomenda que você habilite todas essas políticas de linha de base.</span><span class="sxs-lookup"><span data-stu-id="053a0-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="053a0-118">Depois que essas políticas forem habilitadas, os administradores e os usuários serão solicitados a registrar a autenticação de fator de vários grupos do Azure.</span><span class="sxs-lookup"><span data-stu-id="053a0-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="053a0-119">Para obter mais informações sobre essas políticas, consulte [o que são políticas de linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="053a0-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="053a0-120">Configurar políticas de linha de base</span><span class="sxs-lookup"><span data-stu-id="053a0-120">Set up baseline policies</span></span>

1. <span data-ttu-id="053a0-121">Vá para [portal do Azure](https://portal.azure.com)e navegue até **acesso condicional** **do Azure Active Directory** \> .</span><span class="sxs-lookup"><span data-stu-id="053a0-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="053a0-122">As políticas de linha de base são listadas na página.</span><span class="sxs-lookup"><span data-stu-id="053a0-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="053a0-123">![Página que lista as políticas de linha de base para acesso condicional.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="053a0-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="053a0-124">Consulte as seguintes instruções específicas para cada política:</span><span class="sxs-lookup"><span data-stu-id="053a0-124">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="053a0-125">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="053a0-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

    -   [<span data-ttu-id="053a0-126">Exigir MFA para usuários</span><span class="sxs-lookup"><span data-stu-id="053a0-126">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="053a0-127">Bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="053a0-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)

<span data-ttu-id="053a0-128">Você pode configurar várias políticas adicionais, como exigir aplicativos cliente aprovados.</span><span class="sxs-lookup"><span data-stu-id="053a0-128">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="053a0-129">Consulte a [documentação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="053a0-129">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>