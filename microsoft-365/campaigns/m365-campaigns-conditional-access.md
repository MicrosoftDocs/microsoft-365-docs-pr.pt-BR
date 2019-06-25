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
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como exigir a MFA e configurar as políticas de acesso condicional para o Microsoft 365 Business.
ms.openlocfilehash: 08e9365e8aad37e2412a6d739b41f2328c1aa277
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183208"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="f808f-103">Exigir autenticação multifator e configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="f808f-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="f808f-104">Você protege o acesso aos seus dados com a autenticação multifator e políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="f808f-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="f808f-105">Eles adicionam segurança adicional substancial.</span><span class="sxs-lookup"><span data-stu-id="f808f-105">These add substantial additional security.</span></span> <span data-ttu-id="f808f-106">A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base que são recomendadas para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="f808f-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="f808f-107">As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra vários ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="f808f-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="f808f-108">Esses ataques comuns podem incluir a irrigação de senha, a repetição e o phishing.</span><span class="sxs-lookup"><span data-stu-id="f808f-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="f808f-109">Essas políticas exigem que administradores e usuários insiram uma segunda forma de autenticação (chamada de autenticação multifator, ou MFA) quando determinadas condições são atendidas.</span><span class="sxs-lookup"><span data-stu-id="f808f-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="f808f-110">Por exemplo, se um usuário em sua organização tentar entrar no Microsoft 365 de um país diferente ou de um dispositivo desconhecido, o logon poderá ser considerado arriscado.</span><span class="sxs-lookup"><span data-stu-id="f808f-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="f808f-111">O usuário deve fornecer uma forma extra de autenticação (como uma impressão digital ou um código) para provar sua identidade.</span><span class="sxs-lookup"><span data-stu-id="f808f-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="f808f-112">No momento, as políticas de linha de base incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f808f-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="f808f-113">Configurado no centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f808f-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="f808f-114">**Exigir MFA para administradores** — requer autenticação multifator para as funções de administrador mais privilegiadas, incluindo administrador global.</span><span class="sxs-lookup"><span data-stu-id="f808f-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="f808f-115">**Proteção do usuário final** — requer autenticação multifator para usuários somente quando uma entrada é arriscada.</span><span class="sxs-lookup"><span data-stu-id="f808f-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="f808f-116">Configurado no portal do Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="f808f-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="f808f-117">**Bloquear autenticação herdada** — aplicativos cliente mais antigos e alguns aplicativos novos não usam protocolos de autenticação mais recentes, mais seguros.</span><span class="sxs-lookup"><span data-stu-id="f808f-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="f808f-118">Esses aplicativos antigos podem ignorar as políticas de acesso condicional e obter acesso não autorizado ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f808f-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="f808f-119">Esta política bloqueia o acesso de clientes que não dão suporte ao acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="f808f-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="f808f-120">**Requer MFA para gerenciamento de serviços** — requer a autenticação multifator para acessar ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura as políticas de linha de base).</span><span class="sxs-lookup"><span data-stu-id="f808f-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="f808f-121">A Microsoft recomenda que você habilite todas essas políticas de linha de base.</span><span class="sxs-lookup"><span data-stu-id="f808f-121">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="f808f-122">Após a habilitação dessas políticas, os administradores e os usuários serão solicitados a registrar a autenticação multifator do Azure.</span><span class="sxs-lookup"><span data-stu-id="f808f-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="f808f-123">Para obter mais informações sobre essas políticas, consulte [o que são políticas de linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="f808f-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="f808f-124">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="f808f-124">Require MFA</span></span>

<span data-ttu-id="f808f-125">Para exigir que todos os usuários entrem com uma segunda forma de ID:</span><span class="sxs-lookup"><span data-stu-id="f808f-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="f808f-126">Vá para o centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> em e escolha **configuração**.</span><span class="sxs-lookup"><span data-stu-id="f808f-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="f808f-127">Na página configuração, escolha **Exibir** no cartão de **entrada tornar login** .</span><span class="sxs-lookup"><span data-stu-id="f808f-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Crie um cartão de logon mais seguro.](media/setupmfa.png)
3. <span data-ttu-id="f808f-129">Na página tornar o login mais seguro, escolha **introdução**.</span><span class="sxs-lookup"><span data-stu-id="f808f-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="f808f-130">No painel de segurança reforçar a entrada, marque as caixas de seleção ao lado de **exigir autenticação multifator para administradores** e **exigir que os usuários se registrem para a autenticação multifator e bloquear o acesso se o risco for detectado**.</span><span class="sxs-lookup"><span data-stu-id="f808f-130">On the Strengthen sign-in security pane, check the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="f808f-131">Certifique-se de excluir a conta de administrador de [emergência](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) ou de "quebra-vidro" do requisito da MFA na caixa **localizar usuários** .</span><span class="sxs-lookup"><span data-stu-id="f808f-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Fortaleça a página de segurança de entrada.](media/requiremfa.png)

5. <span data-ttu-id="f808f-133">Escolha **criar política** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="f808f-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="f808f-134">Configurar políticas de linha de base</span><span class="sxs-lookup"><span data-stu-id="f808f-134">Set up baseline policies</span></span>

1. <span data-ttu-id="f808f-135">Vá para [portal do Azure](https://portal.azure.com)e navegue até **acesso condicional** **do Azure Active Directory** \> .</span><span class="sxs-lookup"><span data-stu-id="f808f-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="f808f-136">As políticas de linha de base estão listadas na página e você pode ver que exigir MFA para administradores e proteção do usuário final já está habilitada após a conclusão das etapas em [exigir MFA](#require-mfa).</span><span class="sxs-lookup"><span data-stu-id="f808f-136">The baseline policies are listed on the page, and you can see that Require MFA for admins and End user protection are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![Página que lista as políticas de linha de base para acesso condicional.](media/casettings.png)
2. <span data-ttu-id="f808f-138">Consulte as seguintes instruções específicas para cada política:</span><span class="sxs-lookup"><span data-stu-id="f808f-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="f808f-139">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="f808f-139">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

       
    -   [<span data-ttu-id="f808f-140">Exigir MFA para usuários</span><span class="sxs-lookup"><span data-stu-id="f808f-140">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="f808f-141">Bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="f808f-141">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="f808f-142">Exigir MFA para gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="f808f-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="f808f-143">Você pode configurar políticas adicionais, como exigir aplicativos cliente aprovados.</span><span class="sxs-lookup"><span data-stu-id="f808f-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="f808f-144">Consulte a [documentação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f808f-144">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>
